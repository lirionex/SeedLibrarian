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

*Continuous values* — colour (HSV), height, scent intensity, hardiness, bloom duration. These blend and drift. This is the half that never fully resolves, which is what makes standing orders inexhaustible: a slightly bluer blue is always possible.

**Linked traits are the late-game engine.** Traits should antagonise each other in the genome:

- hardiness suppresses flower size
- glow requires damp tissue, which fights drought tolerance
- intense scent shortens bloom life
- vigour reduces uniformity

Once the player has climbed every mountain, rarity is exhausted — but "can I break this trade-off?" has no floor. A late-game goal like *a glowing plant that survives on the ridge* is a twenty-generation research programme, not a shopping trip.

**Legibility instruments.** Pure RNG breeding is miserable. Give the player tools that make skill beat luck by mid-game: a lens revealing part of a genotype, reference books that decode one trait family at a time, and observation notes that accumulate on a page.

**Expression ≠ genotype.** The same seed grown in shade, poor soil, or a cold frame produces a different plant. This is what makes environment a system rather than a backdrop (see [between-generations](08-between-generations.md), [greenhouses](09-greenhouses.md), and [utilities](10-utilities-and-self-sufficiency.md)).

## Implementation status

_Not started. The cross function (Mendelian discrete + midpoint-with-drift continuous) and at least one linked antagonistic pair are the first things to prototype — see `../poc/phase-0-spreadsheet.md`. Record the model that shipped here, including trait list and linkage rules._
