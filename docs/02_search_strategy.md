# Search Strategy (Classical Bibliographic Search)

This file provides reusable query blocks and **ready-to-run templates** for major bibliographic databases. Log every run in `data/search_logs/search_runs.csv`.

## Databases to search
- PubMed
- Scopus
- Web of Science
- Google Scholar
- Optional: Lens, Dimensions, Semantic Scholar (document any differences in export/coverage)

## Query term blocks (mix-and-match)
### DBMS / systems
- PostgreSQL OR Postgres OR SQLite OR "relational database" OR RDBMS

### Chemistry / structure search
- "chemical structure" OR SMILES OR InChI OR InChIKey OR substructure OR similarity OR fingerprint OR SMARTS

### Implementation / indexing
- extension OR cartridge OR index OR indexing OR GiST OR GIN OR "R-tree" OR "structure search" OR "chemical database"

## PubMed templates (Title/Abstract)
### Broad
```
(PostgreSQL[Title/Abstract] OR Postgres[Title/Abstract] OR SQLite[Title/Abstract] OR "relational database"[Title/Abstract])
AND
("chemical structure"[Title/Abstract] OR SMILES[Title/Abstract] OR InChI[Title/Abstract] OR substructure[Title/Abstract] OR similarity[Title/Abstract] OR fingerprint[Title/Abstract] OR SMARTS[Title/Abstract])
AND
(extension[Title/Abstract] OR cartridge[Title/Abstract] OR index[Title/Abstract] OR indexing[Title/Abstract] OR GiST[Title/Abstract] OR GIN[Title/Abstract] OR "R-tree"[Title/Abstract])
```

### Postgres-specific
```
(PostgreSQL[Title/Abstract] OR Postgres[Title/Abstract])
AND
(RDKit[Title/Abstract] OR cartridge[Title/Abstract] OR extension[Title/Abstract] OR "chemical search"[Title/Abstract])
```

## Scopus template (TITLE-ABS-KEY)
```
TITLE-ABS-KEY ( (postgresql OR postgres OR sqlite OR "relational database")
AND ("chemical structure" OR smiles OR inchi OR substructure OR similarity OR fingerprint OR smarts)
AND (extension OR cartridge OR index OR indexing OR gist OR gin OR "r-tree") )
```

## Web of Science template (TS=)
```
TS=((postgresql OR postgres OR sqlite OR "relational database")
AND ("chemical structure" OR smiles OR inchi OR substructure OR similarity OR fingerprint OR smarts)
AND (extension OR cartridge OR index OR indexing OR gist OR gin OR "r-tree"))
```

## Google Scholar (shorter, iterative)
Google Scholar works best with short queries. Run multiple variants and log each run separately.

Examples:
- `PostgreSQL RDKit cartridge substructure search`
- `SQLite chemical cartridge extension substructure`
- `"chemical structure" indexing GiST PostgreSQL`

## Record keeping (required)
For each run, record:
- date (YYYY-MM-DD)
- database (PubMed/Scopus/WoS/Scholar/…)
- exact query string (copy/paste)
- filters (date range, language, document type, etc.)
- number of results returned
- export path (if you save an RIS/CSV export under `data/raw/`)

See `data/search_logs/search_runs.csv` for the required fields.

## Deduplication guidance (recommended)
- Export from each database in a consistent format (RIS/BibTeX/CSV).
- Deduplicate by DOI where possible, else by title + year.
- Track deduplication decisions in `data/screening/records.csv` notes if needed.

