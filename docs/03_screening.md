# Screening Guide

Screening is done in two stages and recorded in `data/screening/records.csv`.

## Stage 1: Title/abstract screening
**Goal:** quickly identify potentially relevant sources.

Include if the record mentions at least one of:
- chemical structure storage in a database
- substructure/similarity/exact structure search in a DBMS
- extensions/cartridges/indices for chemical queries (especially Postgres/SQLite)
- chemical registry schema/design decisions (standardization, salts/tautomers, identifiers) with a DB implementation angle

Exclude if:
- no clear database/data-management context
- not about chemical structures/entities (false positives)
- purely about unrelated indexing/search domains

## Stage 2: Full-text screening
**Goal:** confirm eligibility and determine what to extract.

Include if the full text (or authoritative documentation) supports extraction into:
- `data/extraction/studies.csv` (evidence, benchmark, method paper), and/or
- `data/extraction/extensions.csv` (a tool/extension/cartridge that can be profiled)

## Decision values
Use the `decision` column consistently:
- `include`
- `exclude`
- `maybe` (needs full text / clarification)

## Reasons for exclusion (common)
- `not_db_related`
- `not_structure_related`
- `not_postgres_sqlite` (keep as background only; optionally still include if conceptually important)
- `insufficient_detail`
- `duplicate`

## Tagging scheme (suggested controlled vocabulary)
Tags go in `tags` as a `|`-separated list, e.g. `pg-extension|substructure|benchmark`.

Core tags:
- DBMS: `pg`, `sqlite`, `other-dbms`
- Artifact: `pg-extension`, `sqlite-extension`, `cartridge`, `schema`, `benchmark`, `dataset`
- Query type: `exact`, `substructure`, `similarity`
- Technique: `fingerprint`, `gins`, `gist`, `rtree`, `bloom`, `vector`, `ml`
- Entity management: `standardization`, `tautomer`, `salt`, `stereo`, `identifier`, `provenance`

## Edge cases
- **Vendor docs**: allowed, but tag as `vendor` and set `source_type=vendor_doc` at extraction time.
- **GitHub-only tools**: allowed, but mark `source_type=github` and capture maintenance signals (recent commits/releases).
- **Non-Postgres/SQLite work**: can be kept for background if it informs data structures and indexing concepts; tag `other-dbms`.

