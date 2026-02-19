# Glossary

## Chemical entity
A representation of a chemical structure plus associated identifiers and relationships (e.g., salts/tautomers/stereoisomers), suitable for storage and retrieval.

## Substance vs compound
Often used inconsistently. In this review, “chemical entity” is preferred; when sources distinguish “substance” (mixture, formulation, salt form) vs “compound” (neutral parent), record the source’s definition.

## SMILES
Text encoding of chemical structures. Canonical SMILES refers to deterministic normalization rules that produce a consistent string for a given structure (tool-dependent).

## InChI / InChIKey
Identifier derived from a structure. InChIKey is a hashed, fixed-length representation; equality can be used for fast matching but depends on standardization choices.

## SMARTS
Pattern language commonly used for substructure queries.

## Fingerprint
A vector/bitset representation of a molecule used for fast screening and similarity calculations (e.g., Morgan/ECFP-like).

## Similarity search
Retrieve molecules similar to a query by comparing fingerprints or embeddings with a metric (e.g., Tanimoto).

## Substructure search
Find molecules containing a query pattern as a subgraph. Typically implemented as:
1) fast screening via fingerprints/keys, then
2) exact verification with a subgraph isomorphism-like matcher.

