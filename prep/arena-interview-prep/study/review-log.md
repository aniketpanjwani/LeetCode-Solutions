# Review Log

Use **Current State** to restart cleanly, then append rows as you practice. Do not delete old rows; recurrence is useful evidence. It is fine to update `Shaky?` and `Last reviewed` as review units happen.

## Current State

Update this block at the end of every study sitting.

| Field | Value |
| --- | --- |
| Last study date | 2026-06-26 |
| Last completed unit | Logged Sum Game (LC1927) miss |
| Carryover | none |
| Next action | REVIEW Sum Game odd-question-mark imbalance condition |
| Notes | Amount per sitting is flexible; update this block before stopping. |

## Legend

- `Shaky?`: use `yes` when recall or implementation is not reliable; use `ok` when you can recover the cue and first move without reading.
- `Last reviewed`: the most recent date this row was touched during a review unit. Use `not yet` until then.
- `Pattern family`: match a family name in [pattern-catalog.md](pattern-catalog.md) so recurring misses cluster visually.
- `Carryover`: an unfinished problem or exact next move that should be resumed before new material.

## Log

| Date | Problem (LC#) | Pattern family | What was missed / slow | Recall cue | Shaky? | Last reviewed |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-06-26 | Sum Game (LC1927) | Game Theory: Digit-Sum Imbalance | Forgot the odd-question-mark imbalance condition. | Who can offset the half-sum difference? | yes | not yet |

## How REVIEW Pulls From This Log

During a **REVIEW** unit:

1. Pull rows with `Shaky? = yes` first.
2. Then pull rows with the oldest `Last reviewed` date.
3. For each row, hide the answer and recover the pattern family, cue, invariant, and first implementation move.
4. Update `Last reviewed` and change `Shaky?` to `ok` only if recall was solid.

This is not computed spaced repetition. It is the lightweight v1 review mechanism.

## Spotting Promotion Candidates

Scan the `Pattern family` and `What was missed / slow` columns. If the same invariant or mistake appears 3+ times across rows, mark it as a future flashcard-promotion candidate in the miss text.

Deferred target: promote only those recurring, log-proven misses through the `flashcard` skill later. Do not create Convex flashcards as part of v1.
