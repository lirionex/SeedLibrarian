---
part: poc-phase-1
title: Phase 1 — Ugly playable
status: not-started
duration: 1–2 weeks
gate: Testers keep playing past the stop point
last_updated: 2026-07-25
---

# Phase 1 — Ugly playable (1–2 weeks)

A text or minimal-2D prototype. Placeholder everything. This is the real test.

**In scope:**

| System | Minimum viable version |
|---|---|
| Genome | The 6 traits from Phase 0 |
| Beds | 3 slots. Sow → wait → harvest |
| Time | 1 "day" = 20–30 real seconds. Compressed deliberately |
| Growth | Staggered: 2–8 days depending on plant |
| Notebook | Save a specimen, name it, see traits + lineage, mother seed reserved |
| Seeds | Finite counts. Crossing consumes one from each parent |
| Standing order | One buyer: pays for scent, scaled to intensity |
| Requests | Three, hand-written. One precise, one interpretive, one with a deadline |
| Wild collection | A button: "go to the ridge" → returns a random ridge-typed plant, with its drawback |
| Money | A single number. Enough to feel the choice, no shop |

**Explicitly cut:** processing, building, greenhouses, utilities, garden, seasons, NPCs, decoration, sound, 3D, co-op, saving.

**Rendering:** a list of beds with a countdown, a list of notebook pages, a list of requests. Buttons. That's it. Godot, a web page, or a Python CLI — whichever you can build fastest. Speed of iteration matters more than anything else at this stage.

**The one thing to get right:** staggered growth times. If all three beds finish together, you'll feel the waiting and wrongly conclude the loop is boring. Offsetting them is what creates the "always something in flight" feeling that the whole design depends on.

## Gate

> Testers keep playing past the stop point. See [success-criteria.md](success-criteria.md).

## Related design parts

[core-loop](../design/03-core-loop.md) · [genetics](../design/04-genetics.md) · [notebook](../design/05-notebook.md) · [requests](../design/06-requests-and-standing-orders.md) · [wild-valley](../design/07-wild-valley.md)

## Implementation status

_Not started._
