---
date: 2026-06-26
topic: arena-interview-prep-setup
---

# ARENA Interview Prep Setup — Requirements

## Summary

Build a lightweight, in-repo, doc-driven prep system organized by *pattern* and sized for ~30 minutes/day. It centers on a dead-simple daily session protocol that rotates learn / re-drill / review by day-type, backed by a small core pattern catalog (~8–12 families) with the six ARENA seed problems as anchors, and a plain-text review log that captures misses and recall cues. Flashcards, a timed simulator, and a reusable skill are designed-for but deferred until the daily habit exists and real failure modes are visible.

## Problem Frame

The user is applying to ARENA (9.0 listed for Oct 5–Nov 6 2026; application includes a one-hour, six-question coding test) and has **never done LeetCode prep before**. The binding constraint is time: ~30 min/day against roughly 100 days, so total practice is on the order of ~50 hours. At that budget, volume grinding is off the table — curation and retention are the levers.

The six problems recovered from the August 2024 ARENA Slack thread (`prep/arena-interview-prep/`) are strong evidence of the test's *style*, but they are **not** a guaranteed question set; treating them as the syllabus risks memorizing the wrong six. The real skill being trained is recognizing, under time pressure, which pattern a fresh problem maps to — and then producing (not just recognizing) the solution.

A secondary risk is over-building: the opening brief enumerated repo structure, flashcards, timed-drill tooling, and a skill. For a beginner on a tight daily budget, the failure mode is spending the prep window building prep infrastructure instead of practicing.

## Key Decisions

**Pattern is the unit of organization; the six problems are anchors, not the syllabus.** The catalog is structured by transferable pattern family (e.g., stack simulation, greedy/math, prefix-suffix parity, two-pointer/sliding window, hashing, DP/LIS, game theory). The six ARENA problems are mapped onto those families as worked anchors. This is what makes the system durable past ARENA and robust to the actual question set differing.

**The daily session selector is the keystone deliverable, not the content.** Because the user is a beginner with no prep habit and (by choice) no scheduling tooling, the highest-risk point is daily friction: "what do I do in today's 30 minutes?" The system must answer that in seconds. Catalog breadth is secondary; a thin catalog with a frictionless protocol beats a rich catalog the user stalls in front of.

**Mixed day-types over a single practice mode.** Sessions rotate between learning a new pattern, re-drilling a known problem for speed, and review/recall — a schedule, not one mode. This balances acquisition (a beginner needs new patterns) against retention and production speed.

**In-repo plain-text retention first; external spaced repetition deferred.** Retention lives in a markdown/text review log inside the repo. The Convex flashcard app (available via the `flashcard` skill) is a documented *future promotion step*, triggered once recurring misses show what's actually worth spaced repetition — not built now.

**Review is recency/flag-based, not true SRS.** Without the Convex app, "review day" cannot compute SM-2 intervals by hand. The v1 review mechanism is a simple pull of the least-recently-reviewed and explicitly-flagged-shaky items from the log. This was confirmed as acceptable for v1.

**The existing `prep/arena-interview-prep/` materials stay raw.** Archived Slack screenshots, OCR, manifest, README, and `problem-map.json` remain as evidence/source-of-truth and are not restructured. The prep *system* is a thin new layer that references them, not a rewrite of them.

## Requirements

**Pattern catalog**
- R1. A core catalog of ~8–12 fundamental pattern families covering at least the patterns the six seed problems already touch (stack simulation, greedy/math, prefix-suffix parity, two-pointer/sliding window, hashing, DP/LIS, game theory).
- R2. Each pattern family records its core idea, the invariant/cue that signals "this is the pattern," and 1–3 representative problems. The six ARENA problems appear as anchors under their families (reusing the existing `problem-map.json` pattern/invariant/drill-target fields where possible).
- R3. The catalog grows reactively: a session that exposes a gap adds a pattern or problem, rather than the catalog being fully enumerated up front.

**Daily session protocol**
- R4. A single, skimmable protocol answers "what do I do in today's ~30 minutes?" in seconds, with no per-day planning required from the user.
- R5. The protocol defines the three day-types (learn / re-drill / review), what each consists of, and a default rotation or rule for choosing today's type.
- R6. Each day-type fits inside ~30 minutes for a beginner, including the expectation that a single new Medium may span more than one session.
- R7. The protocol names where a session's outcome gets recorded (the review log) so practice and retention are linked, not separate habits.

**Review log**
- R8. A plain-text (markdown/JSON) log in the repo captures, per practiced problem: the pattern it belongs to, what was missed or slow, a recall cue, and a confidence/shaky flag.
- R9. The "review" day-type pulls items from the log by least-recently-reviewed and explicitly-flagged-shaky, not by computed spaced-repetition intervals.
- R10. The log is structured enough that recurring misses are visible at a glance, since recurrence is the trigger for promoting items into the Convex flashcard app later.

**Boundaries / posture**
- R11. The system is documentation and lightweight structured files only — no scripts, no automation engine, no external service integration in v1.
- R12. The existing `prep/arena-interview-prep/` evidence materials are referenced, not modified or restructured.

## Acceptance Examples

- AE1. **Covers R4, R5.** It's a "learn" day. The user opens the protocol, sees today is a learn day, and within ~1 minute knows which pattern to study and which anchor problem to read — without deciding anything themselves.
- AE2. **Covers R6.** The user starts ARENA problem 6 (Hard, LIS from both sides) on a learn day, runs out of time at 30 minutes mid-solution, and the protocol's expectation is that finishing it is tomorrow's re-drill — not a failure.
- AE3. **Covers R8, R9.** After attempting "Sum Game," the user logs: pattern = game theory, miss = forgot the odd-question-mark imbalance condition, cue = "who can offset the half-sum difference?", flag = shaky. On the next review day, that entry surfaces because it's flagged shaky.
- AE4. **Covers R10.** The same invariant has been missed on three different problems across two weeks; scanning the log makes that cluster obvious, which signals it's time to promote it to a flashcard.

## Scope Boundaries

**Deferred for later (build once the habit and failure modes are real):**
- Convex flashcard app integration — promote recurring, log-proven misses into spaced repetition via the `flashcard` skill.
- Timed full-simulation tooling (six questions in sixty minutes) — an endgame/taper activity for roughly the last 2–3 weeks before the test, not a daily-session concern.
- A reusable `ce`-style prep skill — an extraction of the workflow *after* it has run for a few weeks and proven its shape; premature to encode now because there is no validated workflow to capture.
- A full standard curriculum (e.g., NeetCode-150 style) — incompatible with the 30-min/day budget and against YAGNI.

**Outside this setup's identity:**
- Any automated scheduler, SRS engine, or progress-tracking script in the repo — the system is doc-driven on purpose; tooling is only justified if manual practice proves a specific bottleneck.
- Restructuring or "cleaning up" the archived `prep/arena-interview-prep/` evidence — it is source material, kept as-is.

## Dependencies / Assumptions

- The `flashcard` skill and its Convex-backed app remain available as the future spaced-repetition target. (Verified present in this environment.)
- The six Python anchor solutions exist under `Python/` and the pattern/invariant/drill-target metadata in `prep/arena-interview-prep/problem-map.json` is reusable as catalog seed content. (Verified.)
- The repo currently has no `scripts/`, `CONCEPTS.md`, or `STRATEGY.md` at root; the prep system introduces no automation and does not depend on them. (Verified.)
- **Assumption:** ~30 min/day for ~100 days is the working budget; the protocol is sized to it. If the real cadence differs materially (e.g., a few long weekend blocks instead of daily), the day-type rotation would need re-sizing.
- **Assumption:** recurrence of a miss in the review log is a sufficient trigger to promote it to a flashcard. If recurrence proves a poor signal in practice, the promotion rule is the thing to revisit.

## Outstanding Questions

**Resolve before planning:**
- Where should the prep system live relative to the raw materials — a sibling like `prep/arena-interview-prep/study/` versus a top-level `study/` area — given the materials should stay raw? (A layout choice, but it affects how the catalog references evidence.)

**Deferred to planning:**
- Exact file format and shape of the review log (markdown table vs JSON vs one-file-per-entry) — a planning/implementation decision constrained by R8–R10.
- The default day-type rotation rule (fixed weekly pattern vs simple "if anything is flagged shaky, review; else learn/re-drill") — pin during planning against how the first week actually feels.
- Initial pattern list beyond the seven the six seeds touch — which 1–5 additional fundamentals (if any) earn a slot in the starting catalog.

## Sources / Research

- `prep/arena-interview-prep/README.md` — ARENA 9.0 signal (Oct 5–Nov 6 2026), six-question/one-hour format, the six-problem table, and the existing "start with timed implementations, promote misses to flashcards later" note.
- `prep/arena-interview-prep/problem-map.json` — per-problem pattern, invariant, and drill-target metadata; direct seed for the catalog (R2).
- `prep/arena-interview-prep/evidence/slack-2024-08/` — archived screenshots + OCR; primary evidence that the six are style indicators, with the noted Q6-is-Hard correction and the `longest-mountain-in-array` vs LeetCode 1671 discrepancy.
- The `flashcard` skill (Convex-backed personal flashcard app) — the deferred spaced-repetition target.
