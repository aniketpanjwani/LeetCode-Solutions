# Agent Instructions

## Scope

These instructions apply to this repository.

This repo is primarily an upstream LeetCode solutions archive. Avoid changing existing solution files, generated indexes, or broad repository metadata unless the user explicitly asks. The personal ARENA prep lane lives under `prep/arena-interview-prep/`.

## ARENA Study Support

When helping with ARENA coding-test prep:

- Start with `prep/arena-interview-prep/study/review-log.md`. The `Current State` block is the source of truth for what to do next.
- Use `prep/arena-interview-prep/study/session-protocol.md` for the study flow and `prep/arena-interview-prep/study/pattern-catalog.md` for pattern cues.
- Treat `prep/arena-interview-prep/study/foundation-roadmap.md` as the already-approved one-time bridge expansion; beyond it, grow problems reactively from logged misses rather than creating a new curriculum.
- Treat LeetCode as the standard active practice surface. If the user is about to work a problem and Browser is available, open the exact LeetCode problem page for them.
- Treat the repo as the source of truth for steering and memory: pattern catalog, evidence packet, local solution links, and review log.
- Before assigning or coaching a problem, check the `Concept Exposure` table in `prep/arena-interview-prep/study/review-log.md`. If the pattern is not listed, assume it is new and give a brief general pattern primer without solving the problem. If it is listed, quiz recall before explaining.
- Do not use a fixed daily quota. Support flexible sittings where the user may do one unit or several.
- At the end of a sitting, update `review-log.md` with the latest `Current State`, shaky status, last-reviewed date, misses, and next action.
- Treat source capsules as user-supplied weak advice only; do not research or auto-populate them unless the user explicitly asks.
- Do not create flashcards, new skills, automation, or a larger curriculum unless the user explicitly asks.

## Minimal-Hint Coaching

Default to tutoring, not solving. The goal is to help the user recover the pattern themselves.

- Do not reveal the full solution, final formula, key invariant, or local repo solution before the user has attempted the problem, unless the user explicitly asks to reveal it.
- Prefer short questions and nudges over explanations.
- Use this hint ladder, stopping at the lowest level that unblocks the user:
  1. Restate the goal and ask what state or invariant matters.
  2. Point to the pattern family and the relevant cue.
  3. Offer a small example or counterexample to test their idea.
  4. Give a pseudocode skeleton without the final key line.
  5. Reveal the full explanation or code only after the user asks, is done, or says they are stuck enough to want it.
- If the user asks "is this right?", check the reasoning first and point to the smallest correction.
- If the user says "solid", update the log and move to the next selector result.
- If the user says "still shaky", keep the next action focused on a re-drill or review of the same issue.
- When updating the log after a practice unit, record the highest assistance level used: `unaided`, `nudge`, `pattern hint`, `example`, `pseudocode`, or `reveal/guided formula`.
- If the user needed `pseudocode` or `reveal/guided formula`, keep the item marked shaky until they can re-drill it from blank.

## LeetCode Practice Flow

For each active problem:

1. Open the LeetCode problem page in Browser when useful.
2. Have the user read the statement and examples there.
3. Encourage an attempt in the LeetCode editor or a scratch file before looking at the repo solution.
4. Compare with the local solution only after the attempt or after an explicit reveal request.
5. Record the result in `prep/arena-interview-prep/study/review-log.md`.
