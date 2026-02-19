# Chemical Entities Data Structures Review

Living **scoping review (PRISMA-ScR oriented)** on the management of **chemical entities** in databases, with a specific focus on:

- Data structures and representations for chemical structures (e.g., SMILES, InChI, Molfile, fingerprints)
- Exact, substructure, and similarity search in **relational DBMS**
- **PostgreSQL** and **SQLite** extensions/cartridges enabling efficient indexing and search
- Current research outcomes, gaps, and future directions

This repo is intentionally **Markdown-first** and keeps the review workflow reproducible via logs and structured extraction tables (CSV).

## Workflow (how to use this repo)
1. **Search**: run bibliographic searches and log them in `data/search_logs/search_runs.csv`
2. **Screen**: apply inclusion/exclusion and tagging in `data/screening/records.csv`
3. **Extract**: fill structured tables in `data/extraction/` (extensions + studies)
4. **Synthesize**: write narrative synthesis in `docs/` following `docs/05_synthesis_plan.md`
5. **Benchmark (optional)**: reserve space for reproducible benchmarking in `benchmarks/`

## Quick links
- Protocol: `docs/00_protocol.md`
- Research questions: `docs/01_research_questions.md`
- Search strategy (templates included): `docs/02_search_strategy.md`
- Screening guide: `docs/03_screening.md`
- Extraction guide + schemas: `docs/04_data_extraction.md`
- Synthesis plan: `docs/05_synthesis_plan.md`
- Postgres extensions overview: `docs/06_postgres_extensions.md`
- SQLite extensions overview: `docs/07_sqlite_extensions.md`
- Future directions prompts: `docs/08_future_directions.md`
- Glossary: `docs/glossary.md`

## Data tables (source of truth)
- Extensions inventory: `data/extraction/extensions.csv`
- Evidence/studies table: `data/extraction/studies.csv`
- Search logs: `data/search_logs/search_runs.csv`
- Screening decisions: `data/screening/records.csv`

## LLM prompt kit (OpenAI/Anthropic)
Prompts are in `prompts/` and are designed to produce **structured JSON + CSV row blocks** aligned with the extraction tables:
- Deep review prompts: `prompts/deep_review_openai.md`, `prompts/deep_review_anthropic.md`
- Paper extraction: `prompts/paper_extraction.md`
- Extension profiling: `prompts/extension_profile.md`
- Query building: `prompts/query_builder.md`

## Directory map
- `docs/`: protocol, search strategy, screening, extraction schema, synthesis plan, topic notes
- `data/`: CSV tables (extraction, screening, search logs) + optional raw exports (ignored)
- `prompts/`: copy/paste prompts for deep review and structured extraction
- `benchmarks/`: placeholder scaffolding for future reproducible benchmarking

## Notes on sources
This review **includes both open-source and commercial tools**. Commercial/vendor documentation is allowed but should be tagged as **non-peer-reviewed** in `source_type` and handled carefully in synthesis.
