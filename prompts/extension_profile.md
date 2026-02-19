# Extension profiling prompt (to fill `data/extraction/extensions.csv`)

## What to paste in
Paste (in order):
1) The tool name and DBMS (Postgres or SQLite)
2) The extension README / official docs text / vendor documentation text
3) Any installation notes you encountered

## Prompt
You are extracting a structured profile of a database extension/cartridge for chemical structure indexing and search.

CONSTRAINTS (strict)
- Use ONLY the provided text.
- Do not guess supported query types, index types, license, or latest version.
- If a field is not explicitly stated, set it to `null` in JSON and leave it empty in the CSV row.

OUTPUT
1) JSON object with EXACT keys matching the `extensions.csv` header:
{
  "tool_id": "...",
  "name": "...",
  "dbms": "postgres|sqlite|other",
  "extension_type": "...",
  "license": "...",
  "source_type": "peer_reviewed|vendor_doc|github|other",
  "repo_url": "...",
  "docs_url": "...",
  "maintained": "yes|no|null",
  "latest_version": "...",
  "chemical_representation": "...",
  "query_types": "...",
  "index_support": "...",
  "fingerprint_support": "...",
  "similarity_metric": "...",
  "substructure_language": "...",
  "install_notes": "...",
  "benchmark_evidence": "...",
  "primary_citations": "...",
  "notes": "..."
}

2) One CSV row in the same column order as `data/extraction/extensions.csv`:
tool_id,name,dbms,extension_type,license,source_type,repo_url,docs_url,maintained,latest_version,chemical_representation,query_types,index_support,fingerprint_support,similarity_metric,substructure_language,install_notes,benchmark_evidence,primary_citations,notes

3) Uncertainties (bulleted): list every field that was null/empty and why.

