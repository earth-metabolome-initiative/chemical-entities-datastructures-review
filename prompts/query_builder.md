# Query builder prompt (bibliographic search strings)

## What to paste in
Paste:
1) Current research questions (from `docs/01_research_questions.md`)
2) Any seed terms (tools, extensions, authors, venues) you already have
3) Any constraints (language, date ranges, must-include DBMS, etc.)

## Prompt
Create bibliographic search queries for a scoping review on management of chemical entities in databases, with focus on PostgreSQL and SQLite extensions for chemical structure indexing/search.

REQUIREMENTS
- Produce database-specific query strings for: PubMed, Scopus, Web of Science, Google Scholar.
- Use reusable term blocks (DBMS / chemistry / indexing) and then assemble final queries.
- Include 2–3 variants per database: broad, Postgres-focused, SQLite-focused.
- Provide a short rationale for each query and what it is expected to capture.
- Keep Google Scholar queries short and iterative (multiple small queries).

OUTPUT FORMAT
1) Term blocks (bulleted)
2) Queries by database:
   - PubMed: ...
   - Scopus: ...
   - Web of Science: ...
   - Google Scholar: ...
3) Logging checklist: what to copy into `data/search_logs/search_runs.csv` for each run.

