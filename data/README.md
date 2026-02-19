# Data layout

This repo tracks **structured review artifacts** in `data/`:

- `data/extraction/`: curated extraction tables (tracked)
  - `extensions.csv`: inventory of Postgres/SQLite extensions/cartridges
  - `studies.csv`: extracted evidence from papers/reports/docs
- `data/search_logs/`: search run logs (tracked)
- `data/screening/`: screening decisions (tracked)
- `data/raw/`: raw exports (RIS/CSV/BibTeX) from bibliographic databases (**ignored by default**)

## Naming conventions
### Search exports
Store exports under `data/raw/` using a date-based name, e.g.:
- `data/raw/pubmed_2026-02-19_query01.ris`
- `data/raw/scopus_2026-02-19_query02.csv`

Record each export path in `data/search_logs/search_runs.csv`.

### IDs
- `run_id` suggestion: `<db>_<YYYY-MM-DD>_<NN>`
- `tool_id` suggestion: stable `snake_case` identifier

