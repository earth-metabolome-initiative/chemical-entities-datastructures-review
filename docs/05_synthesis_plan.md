# Synthesis Plan

This document defines how extracted data will be turned into narrative synthesis and tables.

## Outputs
- Extensions inventory tables (Postgres / SQLite)
- Evidence table summarizing key studies and benchmarks
- Narrative synthesis structured by representation, indexing strategy, and query type
- “Gaps and future directions” section grounded in extracted limitations and future work

## Grouping strategy
### 1) By DBMS
- PostgreSQL
- SQLite

### 2) By representation
- Textual: SMILES, InChI, SMARTS (query language)
- File-like: Molfile/SDF
- Binary/internal molecule formats
- Fingerprints: hashed bit vectors, count vectors, etc.

### 3) By query type
- Exact match (canonical forms, InChIKey equality, etc.)
- Substructure search (screening + verification, SMARTS-like patterns)
- Similarity search (fingerprints + similarity metrics, top-k behavior)

### 4) By indexing strategy (examples)
- Precomputed fingerprints + B-tree indexes on hashes/segments
- GIN/GiST-based indexing (or analogous index types)
- R-tree / spatial analogies (when used for fingerprints/embeddings)
- Hybrid approaches (fingerprint screening + expensive verification)

## Evidence handling
- Prefer peer-reviewed evidence for performance claims.
- Vendor/GitHub evidence is allowed but must be labeled and not over-interpreted.
- Track “what was measured” (datasets, workload, metrics) to avoid apples-to-oranges comparisons.

## Draft synthesis outline (suggested headings)
1. Background and definitions (chemical entities; structure search)
2. Data modeling and normalization (canonicalization, salts/tautomers, identifiers)
3. Representations and storage formats
4. Substructure search pipelines (screening + verification)
5. Similarity search pipelines (fingerprints, metrics, top-k)
6. PostgreSQL ecosystem (extensions, index types, operational considerations)
7. SQLite ecosystem (extensions, constraints, operational considerations)
8. Benchmarks and comparative evidence (what exists; what’s missing)
9. Gaps and future directions

