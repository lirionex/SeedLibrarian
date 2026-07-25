---
part: decisions-log
title: Decisions log
status: living
poc_phase: []
implementation: []
owner:
last_updated: 2026-07-25
---

# Decisions log

A living record of settled design decisions. When a decision is made — here or in any design part — add it to this list with a date so the reasoning isn't lost. When a decision is reversed, don't delete it; strike it through and note why.

## Decisions already made

- Requests expire only for occasions; everything else waits.
- Failing a request keeps the plant.
- Seeds are finite; mother seeds are not.
- Wild traits always carry a drawback.
- Greenhouses cost money to run.
- Utilities affect expression, not just cost.
- No failure states anywhere. Consequences are botanical or temporal.
- Restoration/rebuilding-a-ruin framing is explicitly out.

## New decisions

_Append here as they are made, newest first. Format: `YYYY-MM-DD — decision — (affected part)`._

- 2026-07-25 — No mutation: allele *values* are never created, only inherited, so each gene pool has a hard ceiling (the all-best-alleles-fixed plant). Refinement by stacking climbs toward that ceiling but cannot pass it; collecting a new allele from the wild is the only way to raise it. Rejected adding rare "sports"/mutation — keeps "the wild is the only source of new genes" pure and makes expeditions matter. Consequence: traits don't decay under selection or once stabilised, but an un-maintained heterozygous line can lose its best alleles to drift; stabilising and archiving mother seeds are the safeguards. — *(04-genetics, wild-valley)*
- 2026-07-25 — Wild stock is pure (homozygous) lines. Consequence: a first cross of two wild plants is a uniform F1 — real F1 uniformity — and heritable variation (so "select the best of 5") emerges in the F2, when two hybrids are crossed. True-breeding is the wild starting state; the player generates novelty by crossing hybrids, then re-stabilises it. The alternative (genetically diverse wild stock, so a first cross already varies) was considered and rejected in favour of realism and a calmer early game. — *(04-genetics, poc-phase-0)*
- 2026-07-25 — A cross yields a small handful of offspring seeds (3–5), which segregate differently; the player grows and selects the best. Selection is a skill, mirroring real roguing. Single-child (too swingy) and large batches (too luck-free) were rejected. Resolves the offspring-count open question. — *(04-genetics, core-loop)*
- 2026-07-25 — Start legibility: the player sees expressed traits plus a `carrying: ?` flag (something hidden, but not what); instruments reveal the actual hidden alleles over time. Full genotype visibility from the start is rejected. Resolves the "how legible at the start" open question. — *(04-genetics)*
- 2026-07-25 — Environment → expression is deferred to POC Phase 1. Phase 0 is pure genetics. The engine keeps genotype → expressed plant as a distinct step (near-identity in Phase 0) so the environment reaction-norm slots into that seam later without a rewrite. — *(04-genetics, poc-phase-0)*
- 2026-07-25 — Discrete genes have multiple alleles with a ranked dominance order (e.g. `petal_form` = 3 alleles); the highest-ranked allele present is expressed, lower ones ride along hidden and resurface later. — *(04-genetics)*
- 2026-07-25 — Continuous traits are polygenic: each is the sum of several hidden gene-pairs, so offspring form a bell curve and stacking high alleles from both parents can exceed either parent (transgressive breeding). This is what keeps standing orders inexhaustible through skill rather than luck. — *(04-genetics)*
- 2026-07-25 — Continuous variation is emergent, not sprinkled on: no artificial drift RNG. Wobble comes from Mendelian allele segregation each cross, plus a tiny non-heritable environmental term. Consequently homozygous lines breed true and heterozygous look-alikes can still surprise you. — *(04-genetics)*
- 2026-07-25 — Antagonistic trade-offs are genetic linkage, not cosmetic penalties: the paired genes sit adjacent on a chromosome and are almost always inherited together, with a small per-cross crossover probability that can split them. Trade-offs are therefore real but breakable — the twenty-generation late-game engine. — *(04-genetics)*
- 2026-07-25 — The genome is diploid throughout: every gene (continuous and discrete) is carried as two alleles, so a plant can carry values it doesn't express. This is the spine that lets the library keep secrets. — *(04-genetics)*
