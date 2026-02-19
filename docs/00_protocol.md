# Protocol (Scoping Review; PRISMA-ScR oriented)

## Objectives
Map and synthesize existing approaches for **managing chemical entities in databases**, focusing on:
- Data structures/representations used to store chemical structures and related metadata
- Indexing and query mechanisms enabling **exact**, **substructure**, and **similarity** search
- Practical tooling, especially **PostgreSQL** and **SQLite** extensions/cartridges
- Evidence of performance, limitations, and reported gaps/future work

## Audience / stakeholders
- Database/cheminformatics researchers
- Engineers building chemical registries, metabolomics resources, or structure search services
- Practitioners evaluating Postgres/SQLite extensions for chemical indexing

## Scope and definitions
This review uses:
- **Chemical entity**: a representation of a chemical structure (often a “molecule”), plus identifiers, relationships (salts/tautomers/stereoisomers), and provenance.
- **Management in databases**: storage representations, canonicalization/standardization, indexing, search, and integrity/curation workflows.

Primary focus: **small-molecule** structures and structure-based search in relational DBMS.

## Evidence types included
We include (and label):
- `peer_reviewed`: journal/conference papers, peer-reviewed reports
- `github`: open-source repositories and READMEs
- `vendor_doc`: commercial vendor documentation / marketing pages (allowed but treated as non-peer-reviewed)
- `other`: theses, preprints, standards/specs, technical reports

## Eligibility criteria (high-level)
Include sources that:
- Address storing and/or searching chemical structures in databases, OR
- Describe extensions/cartridges/indices supporting chemical queries, OR
- Evaluate/benchmark chemical search approaches in a DB context, OR
- Discuss data models for chemical registries and entity resolution (salts/tautomers, identifiers, normalization)

Exclude sources that:
- Only discuss chemistry algorithms without a database/data-management component, OR
- Only cover non-structure chemical data (e.g., spectra) without entity management, OR
- Are unrelated to chemical entities (false positives from search terms)

## Commercial/vendor sources policy
Commercial tools are in-scope, but:
- Must be tagged as `vendor_doc` unless there is a corresponding peer-reviewed publication.
- Claims from vendor docs should be reported with clear provenance and not treated as established evidence unless independently supported.

## Workflow overview
1. Define/maintain research questions: `docs/01_research_questions.md`
2. Run and log searches: `docs/02_search_strategy.md` → `data/search_logs/search_runs.csv`
3. Screen and tag: `docs/03_screening.md` → `data/screening/records.csv`
4. Extract structured data:
   - Extensions: `data/extraction/extensions.csv`
   - Studies: `data/extraction/studies.csv`
5. Synthesize results: `docs/05_synthesis_plan.md` + topic docs
6. (Optional) Run benchmarks / collect reproducible measurements: `benchmarks/`

## Versioning and updates
This is a living review. Each major update cycle should:
- Add new search runs with date + query strings
- Record screening decisions and reasons
- Update extraction tables
- Update synthesis narratives and “future directions”

