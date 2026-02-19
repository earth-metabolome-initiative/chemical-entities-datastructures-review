# Benchmarks (scaffold)

This folder is a placeholder for **reproducible benchmarks** of Postgres/SQLite extensions supporting chemical structure search.

Benchmarking is optional for the literature-focused phase, but the scaffold helps keep future evaluation organized.

## What to benchmark (suggested)
- Installation effort (dependencies, build time, portability)
- Data loading time (SDF/SMILES ingestion)
- Index build time and index size
- Query latency and throughput for:
  - exact match
  - substructure search
  - similarity search (top-k)
- Operational constraints (RAM, parallelism, incremental updates)

## Datasets (suggested categories)
- Toy datasets (hundreds–thousands of molecules) for smoke tests
- Medium public datasets (if licensing permits) for reproducible comparisons
- Your real-world dataset (if available), with a shareable subset if possible

## Where to store outputs
- Put curated benchmark outputs under `benchmarks/results/` (tracked).
- Put temporary runtime artifacts under `benchmarks/**/tmp/` (ignored by default).

## Next step
Define the query workload in `benchmarks/query_suite.md` and then implement per-DBMS harnesses under:
- `benchmarks/postgres/`
- `benchmarks/sqlite/`

