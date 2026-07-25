---
part: 05-notebook
title: The notebook
status: not-started
poc_phase: [1]
implementation: []
owner:
last_updated: 2026-07-25
---

# The notebook

The central UI object and the real progression system. **The player writes their own tech tree.** No two libraries look alike, and every saved page is a tool for future work.

Each page holds:

- a procedurally drawn specimen illustration (pressed-flower aesthetic — the page *is* the art)
- player-authored name and handwritten notes
- trait readout, including known unknowns ("carrying: ?")
- full breeding lineage
- a seed count

**The mother seed.** One seed per page is reserved in the page itself and can never be spent on a cross. It can only be used to regrow that exact plant. This makes specimens unlosable — running dry means dedicating a bed and a season to rebuilding stock. **A detour, not a disaster.** (Real seed banks work exactly this way; lean into it thematically.)

**Cuttings.** A *living* plant can be propagated vegetatively — exact clone, no genetics, available only while the plant is in the ground. The tactical move is: clone before you gamble.

**Guided recreation.** Because the recipe is written down, re-running a known cross gets better odds than the original blind discovery. Knowledge compounds — but it's a cheaper second attempt, not a substitute for the mother seed.

**Empty pages are the to-do list, and the player wrote it.** If you have no yellow, you feel the gap. Nobody assigned it.

## Implementation status

_Not started. Minimum viable version for the POC: save a specimen, name it, see traits + lineage, reserve a mother seed. The pressed-flower illustration comes from the same genome that grows the plant (see [art-and-asset-strategy](13-art-and-asset-strategy.md)) and is out of scope until Phase 3._
