# Paper extraction prompt (to fill `data/extraction/studies.csv`)

## What to paste in
Paste (in order):
1) BibTeX key you want to use (or leave blank)
2) Paper metadata (title/year/venue/DOI if known)
3) Abstract and, if available, relevant full-text sections (methods/results/benchmark details)

## Prompt
Extract structured information from the provided paper text for a scoping review about chemical entity management in databases.

CONSTRAINTS
- Use ONLY the provided text.
- Do not invent a DOI, dataset size, benchmark numbers, or tool capabilities.
- If a field is not explicitly stated, set it to `null` in JSON and leave it empty in the CSV row.

OUTPUT
1) JSON object with EXACT keys matching the `studies.csv` header:
{
  "bibkey": "...",
  "year": "...",
  "title": "...",
  "venue": "...",
  "doi": "...",
  "dbms": "...",
  "tool_id": "...",
  "study_type": "...",
  "dataset": "...",
  "queries": "...",
  "metrics": "...",
  "results_summary": "...",
  "limitations": "...",
  "future_work": "...",
  "source_type": "peer_reviewed|vendor_doc|github|other",
  "notes": "..."
}

2) One CSV row in the same column order as `data/extraction/studies.csv`:
bibkey,year,title,venue,doi,dbms,tool_id,study_type,dataset,queries,metrics,results_summary,limitations,future_work,source_type,notes

3) Uncertainties (bulleted): list every field that was null/empty and why.

