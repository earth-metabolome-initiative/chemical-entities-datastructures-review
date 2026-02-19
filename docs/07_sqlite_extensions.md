# SQLite extensions (inventory)

The source of truth is `data/extraction/extensions.csv` filtered where `dbms=sqlite`.

## Starter table (copy rows from the CSV)
| tool_id | name | query_types | index_support | license | source_type | primary_citations |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## Seed list (to verify / fill)
These are candidates to investigate; do not treat as confirmed until profiled in `extensions.csv`:
- Bingo (Indigo) for SQLite (cartridge/extension; structure search)
- Chemicalite (SQLite extension integrating cheminformatics toolkit)

## Notes to capture during profiling
- How molecules are stored (text/blob) and whether fingerprints are stored/computed
- Query support and performance constraints typical for embedded DB use
- Installation/build constraints across platforms

