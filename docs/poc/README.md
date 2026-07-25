---
part: poc-overview
title: Proof of concept — overview
status: not-started
last_updated: 2026-07-25
---

# Proof of concept

*Goal: find out whether the core loop is fun before building anything expensive.*

## The hypothesis

> **Given a small gene pool and an underspecified goal, is deciding which crosses to run absorbing on its own — with no 3D, no art, no village, no building, no story?**

If that's true, everything else in the design document is amplification. If it's false, no amount of cottagecore polish will rescue it, and you'll have found out in three weeks instead of two years.

## What this POC deliberately does not test

Write these down and refuse to be tempted:

- whether the game is pretty or cozy
- whether co-op works
- whether the economy balances
- whether players like the village, the house, or the utilities
- long-term retention
- anything about 3D

**Especially: do not build in 3D for the POC.** The fun you're testing lives entirely in numbers and decisions. Building it in 3D adds weeks and tests nothing you need to know yet. If the loop is fun in a spreadsheet, it will be more fun in a valley. The reverse is never true.

## Phases

| Phase | Duration | Gate | Doc |
|---|---|---|---|
| Phase 0 | 1–2 days | Crossing feels earned, not random | [phase-0-spreadsheet.md](phase-0-spreadsheet.md) |
| Phase 1 | 1–2 weeks | Testers keep playing past the stop point | [phase-1-ugly-playable.md](phase-1-ugly-playable.md) |
| Phase 2 | 2–3 weeks | 3D adds something a button doesn't | [phase-2-3d-space.md](phase-2-3d-space.md) |
| Phase 3 | 1–2 weeks | Procedural plants are pretty and varied | [phase-3-feel.md](phase-3-feel.md) |

**Under six weeks to know whether you have a game.**

Success is measured behaviourally — see [success-criteria.md](success-criteria.md).

## Scope guard

Pin this above the desk:

1. **No 3D until Phase 2.**
2. **No art until Phase 3.**
3. **If you want to add a system, first check whether more parallel state would fix the same problem.** It usually will, and it's free.
4. **Do not fix balance during the POC.** You're testing whether the shape is fun, not whether the numbers are right.
5. **Three weeks, then decide.** If Phase 1 is still limping after three weeks, the loop probably needs rethinking rather than more work.

## Implementation status

_Not started._
