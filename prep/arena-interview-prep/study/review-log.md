# Review Log

Use **Current State** to restart cleanly, then append rows as you practice. Do not delete old rows; recurrence is useful evidence. It is fine to update `Shaky?` and `Last reviewed` as review units happen.

## Current State

Update this block at the end of every study sitting.

| Field | Value |
| --- | --- |
| Last study date | 2026-06-28 |
| Last completed unit | Valid Palindrome (LC125) accepted on LeetCode |
| Carryover | none |
| Next action | LEARN foundation bridge: LC977 Squares of a Sorted Array |
| Notes | LC125 accepted after switching to clearer positive two-pointer indices. Sum Game remains shaky and intentionally parked while continuing the Easy bridge. |

## Legend

- `Shaky?`: use `yes` when recall or implementation is not reliable; use `ok` when you can recover the cue and first move without reading.
- `Last reviewed`: the most recent date this row was touched during a review unit. Use `not yet` until then.
- `Pattern family`: match a family name in [pattern-catalog.md](pattern-catalog.md) so recurring misses cluster visually.
- `Carryover`: an unfinished problem or exact next move that should be resumed before new material.
- `Assistance`: the highest level of help used: `unaided`, `nudge`, `pattern hint`, `example`, `pseudocode`, or `reveal/guided formula`.

## Concept Exposure

Use this table before assigning or coaching a problem. If the relevant pattern is not listed here, assume it is new and give a short pattern primer without solving the problem. If it is listed, quiz for recall first instead of automatically explaining the pattern.

| Pattern family | First introduced | Intro problem | Core cue | Next coaching default |
| --- | --- | --- | --- | --- |
| Game Theory: Digit-Sum Imbalance | 2026-06-28 | Sum Game (LC1927) | Bob wins only on exact signed offset; Alice wins otherwise. | Quiz gently; still shaky. |
| Stack Simulation | 2026-06-28 | Valid Parentheses (LC20) | Latest opener must close first. | Quiz first. |
| Hashing | 2026-06-28 | Two Sum (LC1) | Store seen values so each item can find its complement. | Quiz first. |
| Two Pointers | 2026-06-28 | Valid Palindrome (LC125) | Compare endpoints, then move inward. | Quiz first after this primer. |

## Log

| Date | Problem (LC#) | Unit / outcome | Assistance | Pattern family | What was missed / slow | Recall cue | Shaky? | Last reviewed |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 2026-06-26 | Sum Game (LC1927) | Initial miss logged | n/a | Game Theory: Digit-Sum Imbalance | Forgot the odd-question-mark imbalance condition. | Who can offset the half-sum difference? | yes | not yet |
| 2026-06-28 | Sum Game (LC1927) | LeetCode attempt marked after guided solve | reveal/guided formula | Game Theory: Digit-Sum Imbalance | Needed help with opposite-half vs same-half pairing, exact-cancel condition, and sign of `qdiff`. | Bob wins only on exact signed offset; Alice wins otherwise. | yes | not yet |
| 2026-06-28 | Valid Parentheses (LC20) | Accepted on LeetCode | example | Stack Simulation | Needed small edge-case fixes: empty stack before peeking, leftover openers at the end, and Python set literal syntax. | Latest opener must close first. | ok | not yet |
| 2026-06-28 | Two Sum (LC1) | Accepted on LeetCode | nudge | Hashing | Initially stored needed future complements instead of actual seen numbers; also used string keys unnecessarily. | Store seen values, then check whether the current complement has appeared. | ok | not yet |
| 2026-06-28 | Valid Anagram (LC242) | Accepted on LeetCode | example | Hashing | First correct version used list membership and removal, which was slow; faster version needed frequency counts and dict initialization with `.get()`. | Compare character frequency counts, not character positions. | ok | not yet |
| 2026-06-28 | Valid Palindrome (LC125) | Accepted on LeetCode | nudge | Two Pointers | Started with filtering/reversing halves, then moved to two pointers; negative right index worked but was harder to reason about than positive `j = len(s) - 1`. | Compare endpoints, skip non-alphanumeric chars, then move inward. | ok | not yet |

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
