# SQLite benchmarks (scaffold)

## Candidate extensions to evaluate (to verify)
- Bingo (Indigo) for SQLite
- Chemicalite (SQLite extension integrating a cheminformatics toolkit)

## Suggested approach
1) Create a clean SQLite database file per run (avoid cross-run contamination).
2) Load the extension and record platform + build details.
3) Load dataset + build indexes as recommended by the extension.
4) Run `benchmarks/query_suite.md` query families and record latency.
5) Store curated results under `benchmarks/results/`.

## Notes to capture
- How to load/enable the extension (loadable extension vs compiled-in)
- Data representation (TEXT/BLOB) and constraints
- Indexing strategy used (built-in B-tree, R-tree, custom)

