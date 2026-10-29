# BOOK2PAGE — generation prompt

## Before generation
1. Read `SKILL.md`, `schema.json`, `template.html`, and `DESIGN.md` from the source folder.
2. Parse `DESIGN.md` into:
   - TOKENS → replace contents of `<style id="design-tokens">`.
   - COMPONENT OVERRIDES → replace contents of `<style id="design-overrides">`.
   - FORBIDDEN RULES → validate all tokens and overrides; reject conflicting rules.
3. If `DESIGN.md` is missing/empty, use `design.default.css`.
4. Never claim to have read files that are not accessible in the current environment.

## Determine tier first
- Tier A: full book/source file available.
- Tier B: TOC plus excerpts/notes available.
- Tier C: only title and author available. Do not create a case bank; create questions and gaps only.

## Required pipeline
S0 Intake: state tier, purpose, and 3–5 questions. If purpose/questions were not provided, infer cautiously and mark as inference, or ask the user if essential.
S1 Outline and choose 2–3 core chapters.
S2 For each core chapter fill C, P, E, M, A, O, L, I, Q.
S3 Explain phenomenon → mechanism → root cause.
S4 Explain 3–5 claims at four levels (Trẻ / Teen / ĐH / NCS) while preserving one mechanism.
S5 Build case bank (eight fields) plus a counter-case, only when source tier permits it.
S6 Adversarial review: at least 3 objections, one counterexample, boundary conditions.
S7 Application: one idea, 7-day action, metric, advance prediction.
S8 Validate JSON against schema, render into HTML template, inject design system.
S9 Run all QA gates. Fix failed gates before exporting.

## Evidence discipline
- Label claims `[sách]`, `[suy luận]`, `[ngoài sách]`.
- Cite chapter/page/section when available. Do not fabricate page numbers or cases.
- Unverified cases must say `chưa xác minh`.
- Clearly distinguish source-derived statements from inference and external knowledge.
- Tier C must not contain a case bank. If asked for one, explain why source evidence is insufficient.

## Output
Write exactly one final `book-<slug>.html` artifact for the book. Embed the validated data in `<script type="application/json" id="BOOK_DATA">`.
The HTML must work offline, be screen-first, support print, include Vietnamese UI, dark mode, responsive layout, search/filter, tabs, accordions, and persisted checklists when localStorage is available.
