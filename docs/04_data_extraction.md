# Data Extraction Guide

This review uses CSV tables as the source of truth. Keep values consistent and avoid guessing.

## General conventions
- Use empty field for **unknown/unreported**.
- Use `NA` for **not applicable**.
- Use `|` to separate multiple values in a single cell (e.g., `exact|substructure|similarity`).
- Use BibTeX keys from `references.bib` in citation fields (separate with `;`).

## 1) Extensions inventory: `data/extraction/extensions.csv`
Purpose: catalog Postgres/SQLite extensions/cartridges and their capabilities.

Columns:
- `tool_id`: stable internal ID (snake_case), e.g. `rdkit_pg`, `bingo_sqlite`
- `name`: human name, e.g. `RDKit PostgreSQL cartridge`
- `dbms`: `postgres` or `sqlite` (use `other` only if you intentionally include background tools)
- `extension_type`: e.g. `cartridge`, `extension`, `module`, `udf`, `library_integration`
- `license`: SPDX-like string if known (e.g., `BSD-3-Clause`), else empty
- `source_type`: one of `peer_reviewed`, `vendor_doc`, `github`, `other`
- `repo_url`, `docs_url`: URLs if known (optional)
- `maintained`: `yes`, `no`, or empty (unknown)
- `latest_version`: explicit version string if known, else empty
- `chemical_representation`: e.g. `SMILES|Molfile|binary` (what the extension expects/stores)
- `query_types`: e.g. `exact|substructure|similarity`
- `index_support`: text description (e.g., `GiST on fingerprints`, `B-tree on hashed fingerprint`)
- `fingerprint_support`: e.g. `Morgan|RDKit|substructure_screening` (or empty)
- `similarity_metric`: e.g. `Tanimoto` (or empty)
- `substructure_language`: e.g. `SMARTS` (or empty)
- `install_notes`: short practical notes (build/install deps)
- `benchmark_evidence`: brief pointer to evidence (bibkeys or notes)
- `primary_citations`: BibTeX keys separated by `;`
- `notes`: free text

## 2) Studies/evidence: `data/extraction/studies.csv`
Purpose: extract what the literature claims and measures.

Columns:
- `bibkey`: key from `references.bib`
- `year`, `title`, `venue`, `doi`
- `dbms`: `postgres|sqlite|other|mixed`
- `tool_id`: link to `extensions.csv` where applicable
- `study_type`: e.g. `benchmark|method|case_study|survey`
- `dataset`: what they used (name/size)
- `queries`: what was tested (substructure/similarity/exact)
- `metrics`: e.g. `latency|throughput|index_build_time|recall`
- `results_summary`: 3–6 lines, factual
- `limitations`: explicit limitations noted by authors
- `future_work`: explicit future work noted by authors
- `source_type`: one of `peer_reviewed`, `vendor_doc`, `github`, `other`
- `notes`: free text

## 3) Search logs: `data/search_logs/search_runs.csv`
Purpose: make searches reproducible and auditable.

Columns:
- `run_id`: internal ID, e.g. `pubmed_2026-02-19_01`
- `date`: `YYYY-MM-DD`
- `database`: `PubMed|Scopus|WebOfScience|GoogleScholar|...`
- `query`: exact query string used
- `filters`: date ranges, language, doc type, etc.
- `results_count`: integer if known
- `export_path`: where you saved exports (typically under `data/raw/`)
- `notes`: free text

## 4) Screening records: `data/screening/records.csv`
Purpose: track inclusion/exclusion decisions (optional but recommended).

Columns:
- `record_id`: stable ID (can be a hash or your own counter)
- `source_db`: where it came from (PubMed/Scopus/…)
- `title`, `year`, `doi`, `url`
- `screen_stage`: `title_abstract|full_text`
- `decision`: `include|exclude|maybe`
- `reason_excluded`: standardized reason (see `docs/03_screening.md`)
- `bibkey`: if added to `references.bib`
- `tags`: `|`-separated tags (see `docs/03_screening.md`)
- `notes`: free text

