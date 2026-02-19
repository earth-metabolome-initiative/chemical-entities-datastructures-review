# Deep review prompt (OpenAI)

Use this prompt to draft a structured synthesis and an auditable “claims ledger” from your extracted tables and selected sources.

## What to paste in
1) Your current research questions (from `docs/01_research_questions.md`)  
2) The current contents (or relevant rows) of:
- `data/extraction/extensions.csv`
- `data/extraction/studies.csv`
3) Any key excerpts you want the model to cite (short excerpts only; include bibkeys)

## Prompt
You are assisting with a PRISMA-ScR oriented scoping review on management of chemical entities in databases, with focus on PostgreSQL and SQLite.

TASKS
1) Produce a synthesis outline that matches the structure in `docs/05_synthesis_plan.md`.
2) Produce a “claims ledger” of factual claims you want to make in the review, each grounded in the provided sources.
3) Identify gaps in the extracted tables and propose targeted follow-up searches (queries + rationale).

CONSTRAINTS (strict)
- Use ONLY the content provided in this chat. Do not rely on outside knowledge.
- Every claim must be supported by at least one bibkey from the provided material.
- For each claim, include a verbatim quote (<= 25 words) from the provided excerpts. If no quote is available, do not make the claim.
- Do not invent tool capabilities, versions, or performance numbers.

OUTPUT FORMAT
A) Synthesis outline (bulleted; use headings)

B) Claims ledger (Markdown table):
| claim_id | claim | supporting_bibkeys | quote (<=25 words) | confidence (high/med/low) | notes |

C) Gaps & follow-up searches:
- Missing data fields to fill (list exact CSV columns)
- 5–10 proposed bibliographic queries, with target database (PubMed/Scopus/WoS/Scholar) and rationale

