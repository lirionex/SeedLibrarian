---
part: 04-genetics
title: Genetics
status: not-started
poc_phase: [0, 1]
implementation: []
owner:
last_updated: 2026-07-25
---

# Genetics

**Split the genome two ways.**

*Discrete alleles* — petal form, leaf shape, thorns, growth habit. Mendelian, predictable, plannable. This is the half that makes players feel clever, and it's where recessives hide (your own library keeps secrets from you).

*Continuous values* — colour (HSV), height, scent intensity, hardiness, bloom duration. These blend and drift. This is the half that never fully resolves *within a pool*: a slightly bluer blue is always possible until you have stacked the best alleles you hold — and then a fresh wild allele is what pushes the ceiling higher. Standing orders stay long-lived because that climb is slow and because the wild keeps refilling it.

## The genetic model

Settled during the 2026-07-25 design pass (see [decisions log](decisions-log.md)). The whole model is **diploid**: every gene is carried as two copies, and a plant can carry values it doesn't show. That single choice is what lets your own library keep secrets — and it's the spine the rest hangs off.

**Every gene is a hidden pair.** You see the expressed plant; underneath, each gene holds two alleles. What surfaces depends on the gene type below. What *doesn't* surface is still there to be passed on — the recessive your best rose has been carrying for ten generations is real, and it can walk back into the light in the right cross.

**Continuous traits are polygenic.** A smooth trait like colour or hardiness is not one gene — it's the **sum of several small hidden gene-pairs**. Because it's a sum of many small contributions, offspring land on a natural bell curve, and — crucially — combining the high alleles from *both* parents can produce a child **beyond either parent** (real transgressive breeding). This is what lets you push a trait *past any individual parent* through **skill** rather than luck — you stack the highs, you don't wait for a lucky roll.

**But refinement is bounded, and the wild is the only refill.** There is **no mutation** (decided 2026-07-25): an allele's *value* is never created, only inherited, so a gene pool has a **hard ceiling** — the all-best-alleles-fixed plant. Stacking climbs you toward that ceiling; it cannot pass it. Going further means collecting a *new* allele from the wild (see [wild-valley](07-wild-valley.md)), which is what makes expeditions matter and keeps the valley economically alive. So "a slightly bluer blue is always possible" is true *until you have exhausted your pool's blue*, and the wild is how you raise the roof.

**Wild stock is pure lines — variation lives in the F2.** The wild plants are homozygous (both copies of each gene equal), so they breed true and a first cross of two of them is a *uniform* F1 — every seed alike. That is not a bug, it is real F1 uniformity, and it means the "select the best of a handful" pillar only bites from the **F2** onward: cross two of those hybrids (or self one) and the alleles reshuffle into a scattered handful worth choosing between. True-breeding is where the wild *starts*; the player's job is to break it open by hybridising, then re-stabilise a new line.

**Variation is emergent, not sprinkled on.** There is no artificial drift RNG on continuous traits. Each cross, every gene passes **one of its two alleles at random** to each gamete (Mendel); the child gets one allele per gene from each parent. All the wobble a player sees comes from those alleles reshuffling — nothing else. The consequences are the point:

- Two plants whose alleles are **fixed** (homozygous — the same value on both copies) breed **true**, every time. That is how a stabilised library line holds.
- Plants that are **heterozygous** throw **variable** offspring — *even if the two parents look identical*, because the hidden values still segregate. Look-alikes can surprise you; that's a feature, and it's why legibility instruments matter (below).

**Traits do not decay on their own — neglected lines do.** Because no new allele values appear, a pool's *diversity* can only shrink over time: alleles are lost when they aren't passed on. Under **selection** a trait climbs and holds (you keep the carriers); a **stabilised (homozygous) line breeds true forever** and cannot drift. The one way a hard-won trait regresses is genetic drift — leaving a line heterozygous, unselected, and bred in small numbers until its best alleles are lost by chance. Two mechanics already answer this: **stabilise** the line so it breeds true, and **archive a mother seed** (mother seeds are not finite — see [decisions log](decisions-log.md)) so a banked genotype can always be regrown and is never permanently lost. Maintenance *is* the librarian's craft; drift is the cost of neglect, not an inevitability.

On top of that sits only a **tiny, non-heritable environmental wobble** at grow-time — small enough that it never masks the genetic signal. (It is a placeholder seam for the deferred environment system, not a game knob.)

**Discrete genes have multiple alleles and a dominance ranking.** A discrete gene can carry more than two variants (e.g. `petal_form` = 3 alleles), each with a rank. The expressed form is the **highest-ranked allele present**; lower-ranked alleles ride along hidden and resurface later. `thorns` is the simple case (dominant/recessive, two alleles). This is textbook Mendelian and fully plannable — the plannable half of the game.

### Model at a glance

| Aspect | Decision |
|---|---|
| Ploidy | Diploid — two alleles per gene, everywhere |
| Continuous traits | Polygenic (several loci summed); transgressive breeding possible |
| Continuous inheritance | Mendelian segregation of alleles; **no** added drift RNG |
| Continuous variation source | Emergent from allele reshuffling + tiny non-heritable environmental wobble |
| True-breeding | Homozygous lines breed true; heterozygous lines segregate |
| Discrete genes | Multiple alleles, ranked dominance; recessives hide and resurface |
| Trade-offs | Genetic linkage + rare crossover (see below) |
| Offspring per cross | 3–5 seeds; grow and select the best (see F1/F2 note) |
| Wild stock | Pure (homozygous) lines — first wild cross is a uniform F1; variation emerges in the F2 |
| Environment → expression | **Deferred to POC Phase 1** — Phase 0 is pure genetics |
| Start legibility | Expressed traits + a "carrying: ?" flag; instruments reveal the hidden alleles |

## Linked traits are the late-game engine

Traits antagonise each other **in the genome**, not just on the canvas:

- hardiness suppresses flower size
- glow requires damp tissue, which fights drought tolerance
- intense scent shortens bloom life
- vigour reduces uniformity

**How the link works (decided):** an antagonistic pair sits **adjacent on the same chromosome**, so the two genes are almost always inherited together as a unit. When a gamete forms, there is a **small per-cross probability of a crossover** between them that splits the pair. The trade-off is therefore **real, but breakable** — not a cosmetic penalty subtracted at draw-time, and not a permanent shared gene you can only rebalance.

Once the player has climbed every mountain, rarity is exhausted — but "can I break this trade-off?" has no floor. A late-game goal like *a glowing plant that survives on the ridge* is a twenty-generation research programme: you are breeding, generation after generation, toward the rare recombination that finally uncouples glow from damp tissue. Not a shopping trip.

## Legibility instruments

Pure RNG breeding is miserable; so is a genome you can't read. **At the start, the player sees the expressed plant plus a flag that it is carrying something hidden — `carrying: ?` — without being told what.** Discovery stays alive, but early breeding is never blind gambling.

From there, **instruments make skill beat luck by mid-game**: a lens that reveals part of a genotype, reference books that decode one trait family at a time, and observation notes that accumulate on a page (see [notebook](05-notebook.md)). The arc is legibility earned, not given — which is exactly why full genotype visibility from the start was rejected.

## Expression ≠ genotype *(deferred to Phase 1)*

The same seed grown in shade, poor soil, or a cold frame produces a different plant. This is what makes environment a system rather than a backdrop (see [between-generations](08-between-generations.md), [greenhouses](09-greenhouses.md), and [utilities](10-utilities-and-self-sufficiency.md)).

**This layer is intentionally deferred.** POC Phase 0 models pure genetics only, so the crossing loop can be validated in isolation. To keep the door open, the engine keeps **genotype → expressed plant as a distinct step**: Phase 0 uses a near-identity expression function (genotype straight through, plus the tiny environmental wobble), and Phase 1 slots the real environment reaction-norm into that same seam without a rewrite.

## Implementation status

_Not started. The cross function is the first thing to prototype — see `../poc/phase-0-spreadsheet.md`. The model to build is the one above: diploid genes; polygenic continuous traits summed from a few loci each; Mendelian segregation with **no** added continuous-drift term; multiple-allele ranked dominance on discrete genes; and at least one linked antagonistic pair with a small crossover probability. Keep genotype → expression as its own step so Phase 1 environment drops in cleanly. Record the model that actually shipped here, including the final trait list, loci-per-trait counts, dominance ranks, and linkage/crossover rates._
