# Deep review prompt (Anthropic)

Use this prompt to draft a structured synthesis and an auditable “claims ledger” from your extracted tables and selected sources.

## What to paste in
1) Research questions (`docs/01_research_questions.md`)  
2) Relevant rows from:
- `data/extraction/extensions.csv`
- `data/extraction/studies.csv`
3) Key excerpts to quote (include bibkeys next to each excerpt)

## Prompt
Role: You are a meticulous research assistant supporting a PRISMA-ScR oriented scoping review on chemical entity management in databases (PostgreSQL/SQLite emphasis).

Objectives:
1) Create a synthesis outline consistent with `docs/05_synthesis_plan.md`.
2) Create an auditable claims ledger for the review.
3) Propose follow-up searches to fill evidence gaps.

Rules (non-negotiable):
- Use only the text and tables provided here.
- Do not infer or guess missing facts.
- Every claim must cite at least one bibkey and include a direct quote (<=25 words).
- If you cannot quote support for a claim, omit it and list it under “Unsupported candidate claims”.

Deliverables:
1) Synthesis outline (headings + bullets)
2) Claims ledger table:
   | claim_id | claim | supporting_bibkeys | quote (<=25 words) | confidence | notes |
3) Unsupported candidate claims (bullets; explain what’s missing)
4) Follow-up search plan:
   - Missing CSV fields to fill (exact column names)
   - 5–10 concrete database-specific query strings + rationale

