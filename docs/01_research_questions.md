# Research Questions

## Primary research questions
**RQ1 — Representation.** How are chemical structures/entities represented and normalized for database storage (e.g., SMILES/InChI/Molfile; canonicalization; salts/tautomers/stereochemistry)?

**RQ2 — Data structures & indexing.** What data structures and indexing strategies enable efficient:
- exact matching,
- substructure search, and
- similarity search
for chemical structures in relational databases?

**RQ3 — Postgres/SQLite tooling.** What **PostgreSQL** and **SQLite** extensions/cartridges exist to support chemical structure indexing and search? What are their features, installation patterns, and limitations?

**RQ4 — Evidence.** What published evidence exists (benchmarks, evaluations, case studies) on correctness, performance, and scalability? What datasets, query workloads, and metrics are used?

**RQ5 — Gaps & future directions.** What are the main open problems and promising directions (standardization, hybrid search, performance engineering, provenance/curation, interoperability)?

## Secondary questions (optional lenses)
- Entity resolution: registry design, deduplication, cross-references (CAS, PubChem, ChEMBL, InChIKey, internal IDs)
- Standardization choices and their impact (charge normalization, stereochemistry handling, tautomer rules, salt stripping)
- Provenance and auditability (who changed what; reproducibility of transformations)
- Governance and validation (constraints, triggers, controlled vocabularies, schema design)
- Storage formats (text vs binary; compressed formats; on-the-fly vs precomputed fingerprints)
- Integration patterns (ETL, streaming ingestion, batch updates, incremental index maintenance)

