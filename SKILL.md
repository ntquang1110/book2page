---
name: book2page
version: 1.0.1
input: one book (title + author + optional file/TOC/excerpt)
output: one self-contained HTML file
design_hook: DESIGN.md
lang: vi
---

# BOOK2PAGE

Convert a book into one Vietnamese, screen-first HTML learning artifact. This is not a generic summary or emotional review. Do not invent claims or cases.

## Hard rules
1. Label claims `[sách]`, `[suy luận]`, or `[ngoài sách]`.
2. Every case must have a traceable source. Otherwise mark `chưa xác minh`.
3. Tier C (title only): no case bank; provide hypotheses/questions to verify against the original.
4. Four explanation levels describe the same mechanism at different resolutions: Trẻ, Teen, ĐH, NCS.
5. Applications require a measurable metric and a prediction made in advance.
6. Keep content data separate from presentation template.
7. All user-facing UI is Vietnamese.
8. Read `DESIGN.md` from this skill's source folder. Do not paste it into the generation prompt.
9. Output one HTML file, with JSON embedded. No CDN, remote fonts, or external runtime dependencies.

## Input tiers
- A: source file/text/PDF/EPUB available — full pipeline.
- B: TOC plus excerpt/notes — full pipeline with source-limited cases.
- C: title only — no case bank; explicitly identify unknowns.

## Pipeline
S0 intake: tier, purpose, 3–5 questions.
S1 outline and choose 2–3 core chapters.
S2 fill nine fields per core chapter: C, P, E, M, A, O, L, I, Q.
S3 trace “why” through phenomenon → mechanism → root.
S4 explain 3–5 key claims at four levels.
S5 case bank with eight fields and one counter-case, subject to tier.
S6 adversarial review: three objections, one counterexample, boundary conditions.
S7 application: one idea → 7-day action → metric → prediction.
S8 render JSON into `template.html`, applying `DESIGN.md`.
S9 run QA gates; if a gate fails, return to the relevant stage.

## Selection filter
Keep: core definitions; claims and premises; mechanisms; hidden assumptions; boundary conditions; typical and counter cases; procedures/checklists.
Drop: long anecdotes; duplicate examples; biography/history unless necessary; raw reference lists; extensions unrelated to user questions.

## QA gates
- Every case has a source or is marked unverified.
- Tier C has no case bank.
- At least 2 hidden assumptions and 3 objections.
- At least one counter-case or counterexample.
- “True when / false when” boundary conditions are explicit.
- Four explanation levels preserve the same mechanism.
- Application includes metric and prediction.
- HTML works offline.
- Confidence matches tier.
- UI is Vietnamese.
- `DESIGN.md` is applied in the three designated template regions.
