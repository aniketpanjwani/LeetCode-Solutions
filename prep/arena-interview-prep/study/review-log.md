# Review Log

Use **Current State** to restart cleanly, then append rows as you practice. Do not delete old rows; recurrence is useful evidence. It is fine to update `Shaky?` and `Last reviewed` as review units happen.

## Current State

Update this block at the end of every study sitting.

| Field | Value |
| --- | --- |
| Last study date | 2026-06-28 |
| Last completed unit | Sum Game (LC1927) LeetCode attempt marked after guided solve |
| Carryover | none |
| Next action | RE-DRILL Sum Game from blank; focus signed `qdiff` offset and exact-cancel condition |
| Notes | Assistance used: guided formula/sign help. Keep marked shaky until the compact condition can be recovered unaided. |

## Legend

- `Shaky?`: use `yes` when recall or implementation is not reliable; use `ok` when you can recover the cue and first move without reading.
- `Last reviewed`: the most recent date this row was touched during a review unit. Use `not yet` until then.
- `Pattern family`: match a family name in [pattern-catalog.md](pattern-catalog.md) so recurring misses cluster visually.
- `Carryover`: an unfinished problem or exact next move that should be resumed before new material.
- `Assistance`: the highest level of help used: `unaided`, `nudge`, `pattern hint`, `example`, `pseudocode`, or `reveal/guided formula`.

## Log

| Date | Problem (LC#) | Unit / outcome | Assistance | Pattern family | What was missed / slow | Recall cue | Shaky? | Last reviewed |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 2026-06-26 | Sum Game (LC1927) | Initial miss logged | n/a | Game Theory: Digit-Sum Imbalance | Forgot the odd-question-mark imbalance condition. | Who can offset the half-sum difference? | yes | not yet |
| 2026-06-28 | Sum Game (LC1927) | LeetCode attempt marked after guided solve | reveal/guided formula | Game Theory: Digit-Sum Imbalance | Needed help with opposite-half vs same-half pairing, exact-cancel condition, and sign of `qdiff`. | Bob wins only on exact signed offset; Alice wins otherwise. | yes | 2026-06-28 |

## How REVIEW Pulls From This Log

During a **REVIEW** unit:

1. Pull rows with `Shaky? = yes` first.
2. Then pull rows with the oldest `Last reviewed` date.
3. For each row, hide the answer and recover the pattern family, cue, invariant, first implementation move, and compact condition if one exists.
4. Update `Last reviewed` and change `Shaky?` to `ok` only if recall was solid.

This is not computed spaced repetition. It is the lightweight v1 review mechanism.

## Spotting Promotion Candidates

Scan the `Pattern family` and `What was missed / slow` columns. If the same invariant or mistake appears 3+ times across rows, mark it as a future flashcard-promotion candidate in the miss text.

Deferred target: promote only those recurring, log-proven misses through the `flashcard` skill later. Do not create Convex flashcards as part of v1.
