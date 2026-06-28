# Session Protocol

## Do This Now

1. Open [review-log.md](review-log.md) and read the **Current State** block.
2. If `Next action` or `Carryover` names a problem, start there.
3. Else, if any log row has `Shaky? = yes` and has not been reviewed recently, do a **REVIEW**.
4. Else, if the last completed unit was **LEARN**, do a **RE-DRILL**.
5. Else, do **LEARN** with the next pattern or anchor in [pattern-catalog.md](pattern-catalog.md).
6. When you finish a unit, update [review-log.md](review-log.md). If you want to keep studying, run this selector again.

This choice should take less than a minute. Do not re-plan the curriculum in the middle of a study sitting.

## Study Units

A unit is one coherent action:

- learn one pattern and attempt its anchor problem,
- re-drill one problem from memory,
- review one or more shaky rows,
- continue one unfinished problem to the next meaningful checkpoint.

A sitting can contain any number of units. Stop when your attention, schedule, or energy says to stop. The only required closing move is to update the log so the next restart is clear.

## Practice Surface

Use LeetCode as the active surface for each problem:

1. Open the problem page in Browser.
2. Read the statement and examples there.
3. Attempt the solution in the LeetCode editor or a scratch file.
4. Run or submit on LeetCode if useful.
5. Compare with the local repo solution only after an attempt or an explicit reveal.
6. Update [review-log.md](review-log.md).

The repo decides what to work on next; LeetCode is where the attempt happens.

## Hint Levels

When asking Codex for help mid-problem, use the smallest hint that might unblock you:

| Ask for | What Codex should give |
| --- | --- |
| `nudge` | A short question or recall cue, no formula. |
| `pattern hint` | The relevant pattern family and invariant direction. |
| `example` | A small test case or counterexample to reason through. |
| `pseudocode` | A scaffold without the final key line if possible. |
| `reveal` | Full explanation or code, best used after an attempt. |

Record the highest help level used in [review-log.md](review-log.md). If a solve needed `pseudocode` or `reveal`, keep it marked shaky until you can re-drill it from blank.

## Rotation Rule

Use this priority order:

1. **Carryover first.** An unfinished Medium or Hard from the last sitting becomes the next re-drill or continuation.
2. **Shaky review second.** If something is marked `Shaky? = yes` and has not been reviewed recently, review it before learning new material.
3. **Alternate learn/re-drill otherwise.** If the previous completed unit was learn, re-drill; otherwise learn.

The point is to remove choice. The protocol may feel almost too small when it is working.

## LEARN

Goal: acquire one pattern cue and try one anchor problem.

One unit:

| Step | Action |
| --- | --- |
| 1 | Read one family in [pattern-catalog.md](pattern-catalog.md): core idea, cue, and anchor. |
| 2 | Attempt the anchor problem in Python from memory. Keep the local solution closed unless you are fully stuck. |
| 3 | Compare with the local solution if needed and write one row in [review-log.md](review-log.md). |

If you do not finish, write the carryover in the log. That is normal, especially for a first Medium or for the mountain-array Hard.

## RE-DRILL

Goal: produce a cleaner implementation from memory.

One unit:

| Step | Action |
| --- | --- |
| 1 | Pick the carryover problem, a recently learned anchor, or a shaky row from the log. |
| 2 | Re-solve without reading the solution. Prefer a boring correct Python implementation. |
| 3 | Check against the solution, note what was slow or missing, and update [review-log.md](review-log.md). |

If the problem was a carryover and still does not fit in the sitting, keep it marked shaky and write the exact next move. Do not interpret that as falling behind.

## REVIEW

Goal: recover pattern cues before solving.

One unit:

| Step | Action |
| --- | --- |
| 1 | Pull `Shaky? = yes` rows first, then the least-recently-reviewed rows in [review-log.md](review-log.md). |
| 2 | For each item, hide the answer and recall the pattern family, cue, invariant, and first implementation move. |
| 3 | Re-solve or sketch selected items as far as useful. |
| 4 | Update `Last reviewed`, set `Shaky?` to `ok` only if recall was solid, and mark promotion candidates if the same miss has recurred 3+ times. |

This is not computed spaced repetition. It is a lightweight recency-and-shaky pull until the log proves that Convex flashcards are worth adding.

## Where Outcomes Go

Every sitting ends in [review-log.md](review-log.md). Record:

- the current resume state,
- the problem or pattern touched,
- what was missed or slow,
- the recall cue,
- the highest help level used,
- whether it is still shaky,
- the latest review date.

## Longer Sittings

If you have extra time, keep going by completing another unit:

1. Update the log for the unit you just finished.
2. Re-run the selector at the top of this file.
3. Start the next unit.

This lets a long sitting naturally cover learn, re-drill, and review without turning the plan into a fixed quota.

## Beginner Sizing

A single new Medium can span more than one sitting. The LIS/mountain-array Hard can span several. The successful behavior is to pause at a clear checkpoint, log the exact next move, and let the carryover rule pick up from there.
