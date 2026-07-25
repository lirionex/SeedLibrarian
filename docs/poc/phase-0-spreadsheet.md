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

> **Ready-made sheet:** [`phase-0-genetics-sandbox.xlsx`](phase-0-genetics-sandbox.xlsx) implements the model below — 8 wild plants, a live cross function (pick two parents, press F9 to roll a fresh handful of 5 seeds), Mendelian discrete + polygenic continuous + the linked hardiness/flower-size pair with crossover, and a `carrying ?` flag. Opens in Excel, Google Sheets, or LibreOffice. Start on its "How to use" tab.

**Build** (the model decided on 2026-07-25 — see [genetics](../design/04-genetics.md)):
- **Diploid throughout** — every gene has two allele columns. A plant carries what it doesn't show.
- 6 traits:
  - `colour_hue` (continuous 0–360) — **polygenic:** keep it small for the sheet, ~2–3 loci, each a diploid pair; expressed hue = the loci summed and mapped to range
  - `colour_sat` (continuous, polygenic, same shape)
  - `hardiness` (continuous, polygenic)
  - `scent` (continuous, polygenic)
  - `petal_form` (discrete, 3 alleles, ranked dominance — highest rank present is expressed)
  - `thorns` (discrete, dominant/recessive)
- **One linked pair:** `hardiness` and `flower_size` sit adjacent on a chromosome and are inherited together; a small per-cross crossover probability can split them (up hardiness ↔ down flower size until then).
- A cross function: for every gene, each parent passes **one of its two alleles at random** (Mendel); the child gets one from each. Discrete = highest-ranked allele wins. Continuous = sum the child's loci. **No separate drift term** — variation emerges from the reshuffle; add only a tiny non-heritable wobble to the displayed value. Homozygous parents should breed true; check that they do.
- Keep **genotype → expressed value as its own column/step** (near-identity here) so Phase 1 environment can slot in.
- Show a `carrying: ?` flag when a plant is heterozygous, to rehearse the start-legibility rule.
- 8 starting "wild" plants, each strong in one trait and poor in others. They are **pure lines** (homozygous), so a first wild×wild cross is a **uniform F1** — variation (and real selection among the handful) appears in the **F2**, when you cross two of the hybrids. This is expected, not a modelling error.
- Each cross yields **3–5 offspring seeds** that segregate differently; grow them and select the best (rehearses roguing).

**Do by hand:** try to reach a specific target — say, saturated blue with no thorns — and count the generations.

**You're checking:** does the maths produce results that feel *earned* rather than random? Can you form a plan and see it partly work? If crossing feels like rolling dice, fix the model here. This is the single cheapest place to fix it.

## Gate

> Crossing feels earned, not random.

## Implementation status

_Not started. This validates the [genetics](../design/04-genetics.md) model before any code is written._
