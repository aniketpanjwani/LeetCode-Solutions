---
date: 2026-06-28
topic: arena-leetcode-prep-strategy
---

# ARENA LeetCode Prep Strategy — Requirements

## Summary

Evolve the ARENA prep system into two tiers. Tier 1 is a small, easy-first **bridge**: a few genuinely-Easy LeetCode problems on the foundational patterns that underlie the six ARENA seeds, laddering up so each seed becomes a benchmark rather than the starting line. Tier 2 is a documented, opt-in growth path backed by a compact, repo-owned **pattern→problem candidate pool** with provenance and scope fields — ARENA-first now, re-sliceable to other roles later. A separate empty **source-capsule template** lets weak external advice be tracked without driving the curriculum.

---

## Problem Frame

The current study system is deliberately minimal and grows reactively (`AGENTS.md`, `prep/arena-interview-prep/study/README.md`). Its on-ramp, however, is too steep for a complete beginner: `prep/arena-interview-prep/study/starter-sequence.md` opens directly on the six ARENA seeds and labels a Medium (LC2390) the "easiest anchor," and there are no genuinely-Easy LeetCode problems anywhere in the sequence. The seeds are mostly Medium with one Hard, and one (LC1927 Sum Game) is conceptually slippery.

The cost is visible in the log. `prep/arena-interview-prep/study/review-log.md` shows the only two practiced rows are both Sum Game, both still shaky, the second solved only with `reveal/guided formula` help. The system asks a beginner to climb game theory before they have a reliable easy-pattern base.

Two further pressures shape the work. The six seeds were recovered from August 2024 Slack screenshots; there is no guarantee ARENA 9.0 reuses them, so they must be benchmarks, not the curriculum. And the user's target roles beyond ARENA are not yet settled, so the prep should optimize for ARENA now while staying adaptable to whatever roles come later.

---

## Key Decisions

- **Two-tier, not a full foundation now.** Ship the minimal bridge as the active curriculum and *document* (not build) the expansion path. This keeps the repo's reactive-growth ethos intact while removing the day-one cliff.

- **One-time foundation seeding is a bounded exception to reactive growth.** Pre-seeding even a small easy-first bridge contradicts `AGENTS.md`'s "do not create a larger curriculum" and the catalog's reactive-growth rule. The system treats this as a single deliberate expansion; after the bridge is seeded, reactive growth resumes as the default for everything beyond it. The doc must state this explicitly so the two rules do not read as contradictory.

- **Bridge is keyed to foundational patterns under the seeds, not 1:1 to each ARENA micro-pattern.** Several seeds (game-theory digit-sum, prefix/suffix parity) have no honest Easy rung. Each seed is reached through the foundational pattern(s) it rests on (arrays/hashing, two-pointer, sliding window, stack, prefix sums, plus general-staple binary search and BFS/DFS basics), so the bridge ladders by transferable skill rather than by seed.

- **Candidate pool is repo-owned, in our voice, with provenance — not Sean's list cloned.** Sean Prashad's repo is a strong source of *structure and candidate problems*. We build our own compact pattern→problem model and write our own cues; we use factual fields (slug, difficulty, company-frequency) freely and credit Sean's roadmap as curation inspiration. We do not bulk-import his 68/179 entries or copy his hint notes.

- **Role-adaptivity is modeled now as tags, not role tracks.** Because target roles are unresolved, each candidate-pool entry carries a `scope` tag and a general-interview-value signal (e.g. company-frequency facts) so the pool can be re-sliced later — without committing to any specific role list today.

- **External advice is a weak, opt-in signal.** A source-capsule mechanism exists as an empty template only. It is not seeded, not researched, and does not influence the curriculum unless the user explicitly incorporates a capsule.

---

## Requirements

### Bridge curriculum (Tier 1)

- R1. Define a small set of genuinely-Easy LeetCode problems (target 1–2 per high-value foundational pattern, roughly 8–12 total) that each have an existing local solution in the repo.
- R2. Map each bridge problem to the foundational pattern it trains and to the ARENA seed(s) that pattern supports, so the ladder from Easy bridge → seed benchmark is explicit.
- R3. Prioritize foundational patterns by ARENA relevance plus general-interview value: arrays/hashing, two-pointer, sliding window, stack, prefix sums, with binary search and BFS/DFS basics included as general staples. Defer deep DP, graph, and tree coverage unless evidence shows ARENA tests them.
- R4. Treat the six ARENA seeds as benchmark/seed problems reached after their bridge rungs, not as the first problems attempted.
- R5. Preserve the existing session mechanics: the bridge adds earlier LEARN targets only. The `session-protocol.md` selector, flexible sittings, minimal-hint hint ladder, and review-log-as-state-of-truth stay unchanged, and no mid-sitting curriculum re-planning is introduced.

### Candidate pool and growth path (Tier 2)

- R6. Provide a compact, repo-owned pattern→problem candidate pool, authored in the repo's own voice, not a bulk import of any external dataset.
- R7. Each candidate-pool entry carries at minimum: pattern, problem slug, difficulty, local solution path (when one exists), LeetCode URL, a `source`/provenance field, and a `scope` tag (e.g. `arena-core`, `foundation-bridge`, `general-interview`, `role-future`).
- R8. Each entry carries a general-interview-value signal (e.g. company-frequency drawn from factual data) so the pool can be re-sliced toward other roles later without role-specific lists existing now.
- R9. Document the opt-in expansion path: how the pool grows from the minimal bridge toward a fuller foundation (and, if wanted later, a Sean-curated or role-specific slice), and what log signal would trigger expanding it.
- R10. Credit Sean Prashad's roadmap as curation inspiration in a single sources/attribution note. Use only factual fields from his data; do not reproduce his hint-note prose.

### Source-capsule mechanism

- R11. Provide a source-capsule schema/template with fields: source, date, claim, confidence, applicability, conflicts, action.
- R12. Ship the template empty, with instructions, no seeded entries.
- R13. Specify that capsules are not researched or auto-populated by the agent; the user supplies sources/examples, and capsules remain weak, provenance-tagged signals that do not change the curriculum unless explicitly incorporated.

### Consistency with existing system

- R14. Reconcile the bridge with `AGENTS.md` and `study/README.md`: state the one-time-seeding exception and that reactive growth (catalog rule, 1–3 representative problems per gap) resumes afterward.
- R15. Keep already-deferred items deferred and unchanged: Convex flashcards, the timed six-in-sixty simulator, and a reusable `ce`-style prep skill.

---

## Acceptance Examples

- AE1. **Covers R1, R2.** A beginner opening the prep system sees, before any ARENA seed, an Easy problem for a foundational pattern (e.g. a stack Easy before LC2390, an arrays/hashing Easy before the harder seeds) with its local solution and a one-line cue, and can see which seed it ladders toward.
- AE2. **Covers R3, R4.** When the user reaches LC1927 Sum Game or LC1671 (the slippery/Hard seeds), they arrive after the relevant foundational rungs, and these seeds are presented as benchmarks rather than as the next "easiest" thing.
- AE3. **Covers R7, R8.** A candidate-pool entry for a problem shows its pattern, difficulty, provenance, scope tag, and a general-value signal — enough that the pool could later be filtered to a different role focus without rewriting it.
- AE4. **Covers R12, R13.** The source-capsule file exists with the schema and instructions but zero entries, and nothing in the active roadmap depends on a capsule.

---

## Scope Boundaries

### Deferred for later (eventually, not in v1)

- A fuller foundation (3–5 problems per pattern) or a Sean-curated 30–40 problem slice — reachable through the documented growth path, not built now.
- Role-specific candidate tracks — unlocked once target roles are known.
- Seeding the source capsules and any external-advice research — happens only when the user provides sources.
- Convex flashcards, timed six-in-sixty simulator, reusable prep skill — already deferred in `study/README.md`, unchanged here.

### Outside this effort's identity

- Not a NeetCode-150-style or all-179 generic curriculum, and not Sean's list with local edits. The pool is small, ARENA-shaped, and repo-owned.
- Not a change to the session selector, hint ladder, or review-log mechanics. The on-ramp is widened; the machinery is not redesigned.
- This artifact is requirements-only. It does not modify `review-log.md`, `pattern-catalog.md`, `starter-sequence.md`, or any solution files; those edits belong to a later planning/execution pass.

---

## Dependencies / Assumptions

- Assumes the observation that all bridge-candidate Easy problems already have local Python solutions holds; any chosen bridge problem without a local solution should be flagged during planning rather than silently added.
- Assumes ARENA 9.0's test resembles the recovered signal (one hour, six questions, Medium-weighted). If new evidence contradicts this, the pattern priorities in R3 should be revisited.
- Sean Prashad's material is CC BY-NC 4.0; the non-commercial personal-prep use and factual-field reuse with attribution stay within that, but this is a usage assumption, not the design's motivation.

---

## Outstanding Questions

### Resolve before planning

- Which specific Easy problems fill each foundational-pattern bridge rung, and confirm each has a local solution (the concrete R1/R2 selection).

### Deferred to planning

- Exact file shape of the candidate pool (e.g. extend `problem-map.json` vs a new roadmap/pool file) and where the bridge and source-capsule template live within `prep/arena-interview-prep/study/`.
- Whether the bridge is expressed as an extension of `starter-sequence.md` or as a new foundation-roadmap doc that precedes it.

---

## Sources / Research

- `prep/arena-interview-prep/study/` — existing study system: `README.md`, `session-protocol.md`, `pattern-catalog.md`, `review-log.md`, `starter-sequence.md`.
- `prep/arena-interview-prep/problem-map.json` — the six recovered ARENA seeds and the adjacent LC845.
- `AGENTS.md` — minimal-hint coaching rules, reactive-growth constraint, LeetCode-as-practice-surface.
- Sean Prashad `leetcode-patterns` repo (`src/data/roadmaps.ts` beginner roadmap of 68 problems; `src/data/questions.json` 179 problems with company-frequency facts) — structural and candidate-problem source, CC BY-NC 4.0, used for facts with attribution, not note reuse.
- Grounding dossier for this brainstorm: `/tmp/compound-engineering/ce-brainstorm/20260628-202647-ad3f6b/grounding.md` (scratch, non-repo).
