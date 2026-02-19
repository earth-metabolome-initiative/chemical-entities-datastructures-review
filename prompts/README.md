# Prompt kit

These prompts are designed to help you:
- draft and iteratively refine the narrative synthesis,
- extract structured data into the CSV schemas in `data/extraction/`,
- build reproducible bibliographic search queries.

## General usage
- Prefer **one source at a time** (one paper, one README, one vendor page) for extraction prompts.
- Paste the relevant text (abstract, methods/results, README sections) directly into the prompt.
- Enforce “no guessing”: if a field is not stated, output it as unknown.

## Hallucination controls (recommended)
Add these constraints (or keep them if already present in the prompt):
- Do not invent DOIs, versions, licenses, or performance numbers.
- Do not infer capabilities that are not explicitly described.
- When unsure: output an empty value (or `null` in JSON) and list it under “Uncertainties”.

## Output formats
Extraction prompts typically ask for:
1. **JSON** aligned with a CSV schema, and
2. a **single CSV row** (comma-separated) for quick paste into the table.

If your model struggles with CSV quoting, paste JSON only and transcribe into the CSV manually.

