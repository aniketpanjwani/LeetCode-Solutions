# Foundation Roadmap

Start here if you are new to LeetCode or coming back cold. This bridge gives you ten genuinely Easy rungs before the ARENA seed benchmarks in [starter-sequence.md](starter-sequence.md).

This is the one approved pre-seeded expansion of the ARENA prep lane. After this bridge, new problems should grow reactively from [review-log.md](review-log.md) and [pattern-catalog.md](pattern-catalog.md), not from a fixed daily quota or a generic curriculum.

## Bridge Ladder

| Pattern | Easy rung | Cue | Local solution | Ladders toward |
| --- | --- | --- | --- | --- |
| Stack | LC20 Valid Parentheses | Treat each opening bracket as unfinished work; a closing bracket must match the latest unfinished opener. | [Python](../../../Python/valid-parentheses.py) | LC2390 Removing Stars |
| Arrays / hashing | LC1 Two Sum | Ask what number would complete the target, then make that complement searchable. | [Python](../../../Python/two-sum.py) | LC2452 Words Within Two Edits |
| Arrays / hashing | LC242 Valid Anagram | Reduce both strings to the same frequency signature before comparing. | [Python](../../../Python/valid-anagram.py) | LC2452 Words Within Two Edits |
| Two pointers | LC125 Valid Palindrome | Move inward from both ends, skipping characters that cannot affect symmetry. | [Python](../../../Python/valid-palindrome.py) | LC845 / LC1671 mountain scans |
| Two pointers | LC977 Squares of a Sorted Array | The largest square is at one of the sorted array's ends; fill the output from the back. | [Python](../../../Python/squares-of-a-sorted-array.py) | LC845 / LC1671 mountain scans |
| Sliding window | LC121 Best Time to Buy and Sell Stock | Track the cheapest price so far and ask what profit selling today would give. | [Python](../../../Python/best-time-to-buy-and-sell-stock.py) | LC1664 Ways to Make a Fair Array |
| Sliding window | LC643 Maximum Average Subarray I | Maintain a fixed-size window sum; slide by adding the new item and dropping the old one. | [Python](../../../Python/maximum-average-subarray-i.py) | LC1664 Ways to Make a Fair Array |
| Prefix sums | LC303 Range Sum Query Immutable | Precompute running totals so each range query is one subtraction. | [Python](../../../Python/range-sum-query-immutable.py) | LC1664 Ways to Make a Fair Array |
| Binary search | LC704 Binary Search | Keep a sorted search interval and discard the half that cannot contain the target. | [Python](../../../Python/binary-search.py) | General interview staple |
| BFS / DFS | LC104 Maximum Depth of Binary Tree | Ask each subtree for its depth; the current depth is one plus the deeper child. | [Python](../../../Python/maximum-depth-of-binary-tree.py) | General interview staple |

LC1753, LC1927, and LC1671 are still ARENA benchmarks, but there is no honest Easy clone for greedy pile-pairing, Sum Game's digit-sum game theory, or LIS-from-both-sides. Reach them through transferable habits: derive bounds, compress state, and scan support from both directions.

## Growth Path

The durable pool is [candidate-pool.json](candidate-pool.json). Use it to filter the existing lane by `foundation-bridge`, `arena-core`, or later `general-interview` and role-specific scopes.

Do not expand the pool just because a list exists. Add 1-3 representative problems only when [review-log.md](review-log.md) shows a concrete signal: the same pattern family has 3+ shaky rows, recurring misses, or a repeated "I do not know where to start" moment. A fuller 3-5-problem foundation per pattern, a Sean-curated slice, or a role-specific slice can happen later, but only as an explicit follow-up.

Source capsules are optional weak signals and start empty in [source-capsule-template.md](source-capsule-template.md). They do not change the roadmap unless you explicitly decide to incorporate one.

After these rungs, stop using this file as a schedule. Open [starter-sequence.md](starter-sequence.md) for seed benchmarks, then [session-protocol.md](session-protocol.md) for the ongoing selector.
