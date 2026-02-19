# PostgreSQL extensions/cartridges (inventory)

The source of truth is `data/extraction/extensions.csv` filtered where `dbms=postgres`.

## Starter table (copy rows from the CSV)
Use this as a human-readable view; keep authoritative data in the CSV.

| tool_id | name | query_types | index_support | license | source_type | primary_citations |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## Seed list (to verify / fill)
These are candidates to investigate; do not treat as confirmed until profiled in `extensions.csv`:
- RDKit PostgreSQL cartridge / extension (structure + fingerprint search)
- Bingo (Indigo) PostgreSQL cartridge (substructure/similarity)
- JChem PostgreSQL cartridge (ChemAxon; commercial)

## Notes to capture during profiling
- Molecule data type(s) exposed (text vs binary)
- Supported query operators (exact/substructure/similarity) and how they are implemented
- Index types and recommended indexing patterns (GiST/GIN/B-tree/…)
- Fingerprint types + similarity metrics
- Installation complexity and operational constraints (Docker availability, dependencies)

