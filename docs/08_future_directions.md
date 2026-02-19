# Future Directions (prompting guide)

Use this page as a checklist when writing the “gaps and future directions” synthesis.

## Standardization and identity
- Common, reproducible standardization pipelines (salts/tautomers/stereo) and their impact on equality/substructure search
- Transparent provenance of transformations (audit trails)
- Interoperability of identifiers and registry design patterns

## Indexing and performance engineering
- More reproducible benchmark suites (datasets + query workloads + metrics)
- Better characterizations of index build/maintenance cost vs query latency
- Incremental updates and reindexing strategies for large registries

## Correctness and evaluation
- Ground-truthing substructure/similarity recall/precision across toolchains
- Handling tricky chemistry (aromaticity models, stereochemistry, tautomers)
- Test sets for “hard cases”

## Hybrid search and modern approaches
- Combining classical fingerprints with learned embeddings or vector indexes
- Hybrid candidate generation (fingerprint) + verification (exact matcher)
- Query planning/optimization for structure search workloads inside SQL engines

## Usability and deployment
- Packaging and distribution (containers, extensions, cross-platform builds)
- Operational reliability, observability, and resource utilization
- Security considerations for user-submitted query structures

