# Pattern Catalog

This catalog starts with eight families: six directly touched by the ARENA seed problems, plus two adjacent fundamentals. Add new families only when a study unit exposes a real gap.

Each anchor uses the metadata in [problem-map.json](../problem-map.json). Local solution links are for review after an attempt, not for first-pass reading.

## Stack Simulation

**Core idea:** Maintain the live prefix of the answer in a stack-like list. Each operation affects the most recent live item.

**Cue / invariant:** If a symbol deletes, cancels, or resolves the nearest previous live element, the current live state is the stack.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC2390 Removing Stars From a String | ARENA anchor | Write the stack solution without overthinking string deletion. | [Python](../../../Python/removing-stars-from-a-string.py) | [screenshot](../evidence/slack-2024-08/03-question-2-removing-stars.png) |

## Greedy / Math Pile Pairing

**Core idea:** Convert repeated optimal choices into a limiting formula. The answer is bounded both by total available pairs and by the material outside the largest pile.

**Cue / invariant:** If each move consumes two different piles, the score cannot exceed `total // 2` or `total - max_pile`.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC1753 Maximum Score From Removing Stones | ARENA anchor | Derive and implement `min(total // 2, total - max_pile)`. | [Python](../../../Python/maximum-score-from-removing-stones.py) | [screenshot](../evidence/slack-2024-08/04-question-3-removing-stones.png) |

## Prefix / Suffix Parity

**Core idea:** Keep enough prefix and suffix summary state to evaluate every deletion in one pass.

**Cue / invariant:** After deleting index `i`, the prefix keeps parity and the suffix shifts left, swapping even and odd positions.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC1664 Ways to Make a Fair Array | ARENA anchor | Track prefix even/odd and suffix even/odd in one pass. | [Python](../../../Python/ways-to-make-a-fair-array.py) | [screenshot](../evidence/slack-2024-08/05-question-4-fair-array.png) |

## Bounded Hamming Distance

**Core idea:** Compare equal-length strings by counting differing positions, stopping once the allowed edit budget is exceeded.

**Cue / invariant:** A query qualifies if any dictionary word differs in at most two positions.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC2452 Words Within Two Edits of Dictionary | ARENA anchor | Implement simple `O(q*n*l)` first; discuss hash/trie only after correctness. | [Python](../../../Python/words-within-two-edits-of-dictionary.py) | [screenshot](../evidence/slack-2024-08/02-question-1-two-edit-words.png) |

## Game Theory: Digit-Sum Imbalance

**Core idea:** Avoid game-tree search by compressing the game into half-sum difference and question-mark imbalance.

**Cue / invariant:** Bob can force equality only when the remaining question marks can exactly offset the current half-sum difference; odd imbalance favors Alice.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC1927 Sum Game | ARENA anchor | Memorize the compact condition, then explain why odd question-mark imbalance favors Alice. | [Python](../../../Python/sum-game.py) | [screenshot](../evidence/slack-2024-08/06-question-5-sum-game.png) |

## LIS From Both Sides

**Core idea:** Compute increasing subsequence support from the left and from the right, then choose a valid peak.

**Cue / invariant:** A valid mountain peak needs a nonempty increasing arm on the left and a nonempty decreasing arm on the right.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC1671 Minimum Number of Removals to Make Mountain Array | ARENA anchor | Compute LIS lengths left-to-right and right-to-left, then subtract the best mountain length from `n`. | [Python](../../../Python/minimum-number-of-removals-to-make-mountain-array.py) | [screenshot](../evidence/slack-2024-08/07-question-6-mountain-array.png) |
| LC845 Longest Mountain in Array | Adjacent reference | Distinguish longest contiguous mountain from minimum removals to form a subsequence mountain. | [Python](../../../Python/longest-mountain-in-array.py) | [link note](../evidence/slack-2024-08/08-leetcode-links-and-comments.png) |

**Discrepancy note:** `longest-mountain-in-array` appeared in the Slack link message, but the question 6 screenshot asks for minimum removals to make a mountain array. The prep anchor is LC1671, currently marked Hard in [problem-map.json](../problem-map.json).

## Two-Pointer / Sliding Window

**Core idea:** Use one or two moving boundaries to maintain a valid interval, run, or local shape without restarting work.

**Cue / invariant:** When the answer depends on a contiguous window or run and you can update validity as boundaries move, avoid nested scans.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC845 Longest Mountain in Array | Foundational adjacent | Scan rising and falling runs without confusing contiguous mountains with subsequence mountains. | [Python](../../../Python/longest-mountain-in-array.py) | [Slack link screenshot](../evidence/slack-2024-08/08-leetcode-links-and-comments.png) |

## Hashing

**Core idea:** Precompute the lookup shape that turns repeated comparisons into membership checks.

**Cue / invariant:** If the brute-force check repeats the same equality or difference question many times, ask what key would make the target state searchable.

**Representative problems:**

| Problem | Role | Drill focus | Local solution | Evidence |
| --- | --- | --- | --- | --- |
| LC1 Two Sum | Foundational adjacent | Store complements or seen values so each element is processed once. | [Python](../../../Python/two-sum.py) | general repo anchor |
| LC2452 Words Within Two Edits of Dictionary | ARENA anchor, optional optimization | Recognize why the simple mismatch count is enough first, then how masked/hash variants could reduce repeated comparison. | [Python](../../../Python/words-within-two-edits-of-dictionary.py) | [screenshot](../evidence/slack-2024-08/02-question-1-two-edit-words.png) |

## Growing This Catalog Reactively

Add a family or representative problem only after a study unit exposes a concrete gap:

1. Record the miss in [review-log.md](review-log.md).
2. If the miss does not fit an existing family, add the smallest new family section here.
3. Add 1-3 representative problems, not a full curriculum.
4. Keep the session selector in [session-protocol.md](session-protocol.md) unchanged unless the protocol itself caused the miss.

Named candidates, not seeded yet:

- **Binary search:** add when a study unit shows uncertainty about monotonic predicates or sorted-search variants. Local candidate: [LC704 Binary Search](../../../Python/binary-search.py).
- **BFS / DFS:** add when a study unit shows graph/tree traversal uncertainty. Local candidates: [Binary Tree Level Order Traversal](../../../Python/binary-tree-level-order-traversal.py), [Number of Islands](../../../Python/number-of-islands.py).
