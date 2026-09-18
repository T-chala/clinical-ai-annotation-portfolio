# Annotation Quality Report

## Executive summary

Across **50 biomedical abstracts**, the manual annotation set contains **376 annotations**, compared with **385 gold-standard annotations**.

The comparison separates exact agreement from different types of disagreement:

| Outcome | Count |
|---|---:|
| Exact span + category matches | **364** |
| Span/boundary differences | **9** |
| Category differences | **3** |
| Gold-only omissions | **9** |
| Manual-only annotations | **0** |

This accounts for all 376 manual annotations and all 385 gold annotations.

### Strict exact-match metrics

- **Exact-match precision:** 364 / 376 = **96.8%**
- **Exact-match recall:** 364 / 385 = **94.5%**
- **Exact-match F1:** **95.6%**

### Mention coverage after accounting for boundary/category disagreements

Of the 385 gold annotations:

- 364 were exact matches;
- 9 had a corresponding manual annotation with a boundary difference;
- 3 had a corresponding manual annotation with a category difference;
- 9 were genuine gold-only omissions.

Thus, **376/385 = 97.7%** of gold mentions had a corresponding manual annotation when boundary and category disagreements are separated from genuine omissions.

## Disagreement analysis

### 1. Span/boundary differences — 9

These cases represent the same underlying mention selected with different text boundaries. 

- `tumor` vs `tumor types`
- `idiopathic Addison's disease` vs `Addison's disease`
- `idiopathic Addison's disease` vs `Addison's disease`
- `idiopathic adrenocortical insufficiency` vs `adrenocortical insufficiency`
- `attenuated adenomatous polyposis coli` vs `adenomatous polyposis coli`
- `classical galactosemia` vs `galactosemia`
- `tumor` vs `von Hippel-Lindau tumor`
- `tumor` vs `von Hippel-Lindau tumor`
- `severe X-linked recessive neurological disorder` vs `X-linked recessive neurological disorder`

These are reported as **boundary disagreements**, not false-positive/false-negative pairs.

### 2. Category differences — 3

- `adrenal insufficiency`: manual `SpecificDisease` vs gold `DiseaseClass` — two occurrences.
- `Huntington disease`: manual `SpecificDisease` vs gold `Modifier` — one occurrence.

### 3. Gold-only omissions — 9

The nine gold mentions without a corresponding manual annotation are:

1. `enzyme deficiency`
2. `inherited human disorder`
3. `metastasis`
4. `inherited human disease`
5. `cancer-associated diseases`
6. `microsatellite instability`
7. `defective formation of type II collagen`
8. `recessively inherited condition`
9. `PLP-associated disease`

### 4. Manual-only annotations — 0

After the span-level adjudication, there were **no unexplained manual-only annotations**.

## Interpretation

The results show high agreement with the supplied gold annotations. The main opportunities for improvement are:

- recognizing broad disease-related expressions;
- applying the corpus's disease-class policy consistently;
- making span boundaries consistent with the corpus;
- distinguishing disease mentions from modifiers when the same text can serve different annotation roles.

## Limitation

The manual annotation file records text spans rather than character offsets. Therefore, the boundary analysis is a text-span adjudication rather than a full independent offset-level boundary audit.
