# Annotation Error Taxonomy

This project separates annotation disagreements from scoring artifacts.

- **Exact match:** same normalized text span and category.
- **Span/boundary difference:** the manual annotation and gold annotation refer to the same underlying mention, but the selected boundaries differ.
- **Category difference:** the same normalized text span is annotated, but the category differs.
- **Gold-only omission:** a gold-standard disease mention has no corresponding manual annotation.
- **Manual-only annotation:** a manual annotation has no corresponding gold mention.

A span/boundary difference is **not** counted as a manual false positive and gold false negative in the qualitative error analysis.
