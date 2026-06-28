# ARENA Interview Prep

This folder is the repo-local materials packet for ARENA coding-test prep.

Current public ARENA signal, checked on 2026-06-26: ARENA 9.0 applications are open, the programme is listed for Oct 5-Nov 6 2026, and the application process includes a coding test with six questions in a one-hour limit.

## Evidence

The Slack screenshots from Desktop were archived in:

`prep/arena-interview-prep/evidence/slack-2024-08/`

The OCR says the 2024 Slack thread shared six ARENA coding questions, with a note that future applicants could use them to understand the style. A follow-up mapped the screenshots to LeetCode links. Another comment said "6 mediums in 1 hour"; a later correction notes the sixth is actually Hard.

## Six-Question Set

| Order | LeetCode | Difficulty | Pattern | Local Python |
| --- | --- | --- | --- | --- |
| 1 | 2452 Words Within Two Edits of Dictionary | Medium | bounded Hamming distance | `Python/words-within-two-edits-of-dictionary.py` |
| 2 | 2390 Removing Stars From a String | Medium | stack simulation | `Python/removing-stars-from-a-string.py` |
| 3 | 1753 Maximum Score From Removing Stones | Medium | greedy/math | `Python/maximum-score-from-removing-stones.py` |
| 4 | 1664 Ways to Make a Fair Array | Medium | parity prefix/suffix sums | `Python/ways-to-make-a-fair-array.py` |
| 5 | 1927 Sum Game | Medium | game theory plus imbalance | `Python/sum-game.py` |
| 6 | 1671 Minimum Number of Removals to Make Mountain Array | Hard | LIS from both sides | `Python/minimum-number-of-removals-to-make-mountain-array.py` |

`longest-mountain-in-array` appeared in the Slack link message, but the screenshot statement asks for minimum removals, so the prep target is LeetCode 1671.

## Initial Prep Notes

The current evidence suggests prep should probably start with timed Python implementations of these six questions, then only later turn recurring misses into flashcards or a reusable repo skill. No flashcards have been persisted.
