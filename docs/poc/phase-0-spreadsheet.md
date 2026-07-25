---
part: poc-phase-0
title: Phase 0 — Spreadsheet
status: not-started
duration: 1–2 days
gate: Crossing feels earned, not random
last_updated: 2026-07-25
---

# Phase 0 — Spreadsheet (1–2 days)

Before any code. A sheet where you manually cross two rows and read the child.

**Build:**
- 6 traits: `colour_hue` (continuous 0–360), `colour_sat` (continuous), `petal_form` (discrete, 3 alleles), `hardiness` (continuous), `scent` (continuous), `thorns` (discrete, dominant/recessive)
- One linked pair: `hardiness` up pushes `flower_size` down
- A cross function: discrete = Mendelian, continuous = midpoint of parents ± small random drift
- 8 starting "wild" plants, each strong in one trait and poor in others

**Do by hand:** try to reach a specific target — say, saturated blue with no thorns — and count the generations.

**You're checking:** does the maths produce results that feel *earned* rather than random? Can you form a plan and see it partly work? If crossing feels like rolling dice, fix the model here. This is the single cheapest place to fix it.

## Gate

> Crossing feels earned, not random.

## Implementation status

_Not started. This validates the [genetics](../design/04-genetics.md) model before any code is written._
