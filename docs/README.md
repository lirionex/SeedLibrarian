# Seed Library — documentation

This is the home for the game's design and planning documents. It's structured so that each part is **standalone and independently workable**, and so that **implementation progress can be tracked directly against the design**.

- **[`design/`](design/)** — the design document, split into standalone parts. One concern per file.
- **[`poc/`](poc/)** — the proof-of-concept plan, split by phase. Validates the design before expensive building.

## How this stays in sync with the code

The goal is that when we start implementing, changes and progress reflect **directly onto the design docs** rather than drifting apart. Three lightweight conventions make that work:

1. **Frontmatter on every part.** Each design file starts with a YAML block carrying a `status` and an `implementation` list. Statuses:

   | status | meaning |
   |---|---|
   | `not-started` | nothing built yet |
   | `in-progress` | actively being implemented |
   | `implemented` | shipped and matches the design |
   | `deferred` | intentionally postponed (e.g. post-POC) |
   | `living` | an ongoing log, never "done" (decisions, open questions) |

2. **An "Implementation status" section** at the bottom of each part. As code lands, update it here — link the commit/PR, note what actually shipped, and record any deviation from the design. If the implementation changes the design, edit the design prose in the same PR so the doc never lies.

3. **The status dashboard below.** Update the row when a part's `status` changes. This table is the at-a-glance view of where the whole project stands.

**Rule of thumb:** a PR that touches a system also touches that system's design part. Design and code move together or not at all.

## Status dashboard — design

| Part | Status | POC phase |
|---|---|---|
| [01 · Pitch](design/01-pitch.md) | not-started | — |
| [02 · Design pillars](design/02-design-pillars.md) | not-started | — |
| [03 · Core loop](design/03-core-loop.md) | not-started | 1 |
| [04 · Genetics](design/04-genetics.md) | not-started | 0, 1 |
| [05 · The notebook](design/05-notebook.md) | not-started | 1 |
| [06 · Requests and standing orders](design/06-requests-and-standing-orders.md) | not-started | 1 |
| [07 · The wild valley](design/07-wild-valley.md) | not-started | 1, 2 |
| [08 · Between generations](design/08-between-generations.md) | not-started | — |
| [09 · Greenhouses](design/09-greenhouses.md) | not-started | — |
| [10 · Utilities and self-sufficiency](design/10-utilities-and-self-sufficiency.md) | not-started | — |
| [11 · The garden and the late game](design/11-garden-and-late-game.md) | not-started | — |
| [12 · Co-op](design/12-co-op.md) | not-started | — |
| [13 · Art and asset strategy](design/13-art-and-asset-strategy.md) | not-started | 3 |
| [Decisions log](design/decisions-log.md) | living | — |
| [Open questions](design/open-questions.md) | living | — |

## Status dashboard — POC

| Phase | Status | Gate |
|---|---|---|
| [Phase 0 · Spreadsheet](poc/phase-0-spreadsheet.md) | not-started | Crossing feels earned, not random |
| [Phase 1 · Ugly playable](poc/phase-1-ugly-playable.md) | not-started | Testers keep playing past the stop point |
| [Phase 2 · 3D space](poc/phase-2-3d-space.md) | not-started | 3D adds something a button doesn't |
| [Phase 3 · Feel](poc/phase-3-feel.md) | not-started | Procedural plants are pretty and varied |

_Keep this dashboard in step with the `status` frontmatter of each file._
