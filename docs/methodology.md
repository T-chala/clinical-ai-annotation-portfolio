# Methodology

## Dataset
The project uses 50 abstracts from the NCBI Disease Corpus development set for this portfolio.

## Manual annotation
I independently reviewed the 50 abstracts and marked disease-related text spans using the corpus categories:
- SpecificDisease
- DiseaseClass
- CompositeMention
- Modifier

## Comparison
Manual annotations were compared with the supplied gold annotations using normalized text-span and category matching. Whitespace and category-label formatting variations were normalized.

The comparison then separates:
1. exact span + category matches;
2. span/boundary differences;
3. category differences;
4. gold-only omissions;
5. manual-only annotations.

The analysis does not describe every non-exact match as a false positive/false negative. In particular, a boundary difference is treated as a boundary disagreement.

Because the original manual annotation document does not contain character offsets, the boundary analysis is based on the text spans and their occurrences in the supplied corpus rather than an independently recorded manual offset audit.
