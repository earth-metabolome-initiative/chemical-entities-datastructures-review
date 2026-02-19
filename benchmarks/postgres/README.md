# PostgreSQL benchmarks (scaffold)

## Candidate extensions to evaluate (to verify)
- RDKit PostgreSQL cartridge / extension
- Bingo (Indigo) PostgreSQL cartridge
- JChem PostgreSQL cartridge (commercial)

## Suggested approach
1) Set up a reproducible Postgres environment (often easiest via Docker).
2) Install the extension and record exact versions and build flags.
3) Load a standardized dataset (SMILES/SDF) and record ingestion time.
4) Build recommended indexes and record build time + index size.
5) Run the canonical workload from `benchmarks/query_suite.md`.
6) Store curated results under `benchmarks/results/` with a short README describing the environment.

## Notes to capture
- Extension install instructions and dependencies
- SQL schema required (types/operators)
- Index recommendations (GiST/GIN/B-tree/other)
- Any limitations (e.g., no similarity search, no top-k, no incremental index updates)

