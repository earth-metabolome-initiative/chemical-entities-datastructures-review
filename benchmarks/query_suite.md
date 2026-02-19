# Query suite definition (canonical workload)

This document defines a reproducible query workload. Keep it stable so benchmark results are comparable over time.

## Data model (minimal)
At minimum, store:
- `molecule_id` (internal ID)
- `structure` (format depends on extension: SMILES, Molfile, or binary)
- optional: precomputed fingerprints (if the extension expects it)

## Query types
### 1) Exact match
Examples:
- canonical SMILES equality
- InChIKey equality
- extension-specific molecule equality operator

Record:
- number of hits
- latency distribution (p50/p95)

### 2) Substructure search
Define:
- a set of substructure patterns (SMARTS or extension-specific)
- a mix of easy and hard patterns (varying specificity)

Record:
- candidate count (screening stage) if exposed
- verified hit count
- latency distribution (p50/p95)

### 3) Similarity search (top-k)
Define:
- fingerprint type (Morgan/ECFP-like, etc.) if configurable
- similarity metric (e.g., Tanimoto)
- k values (e.g., 10, 50, 100)

Record:
- top-k latency
- whether results are exact or approximate (if applicable)

## Metrics to record (minimum)
- dataset size (molecules)
- index build time
- index size on disk
- query latency (p50, p95) for each query family
- hardware/environment notes (CPU, RAM, storage; Docker/native)

