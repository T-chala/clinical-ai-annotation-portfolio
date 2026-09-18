# Clinical Disease Entity Annotation & Quality Analysis

## Overview
A portfolio project demonstrating manual clinical text annotation and annotation-quality analysis using the **NCBI Disease Corpus**. I independently annotated 50 biomedical abstracts and compared my annotations with the corresponding gold-standard annotations.

## About Me

I am a licensed Medical Doctor with 6+ years of clinical experience in Ethiopia, including general practice, pediatrics, emergency, inpatient and outpatient care.

I am transitioning into healthcare data and medical AI, applying my clinical expertise to data annotation, clinical text analysis, and Medical AI evaluation.

### Skills demonstrated
- clinical disease-entity recognition
- annotation guideline interpretation
- span/boundary selection
- entity-category classification
- quality assurance
- gold-standard comparison
- error analysis

## Dataset
- Source: NCBI Disease Corpus development set
- Sample: **50 abstracts**
- Gold-standard annotations in the supplied sample: **385**
- Submitted manual annotations: **376**

The original NCBI Disease Corpus and its gold-standard annotations are not redistributed in this repository. The project uses the corpus as an external reference dataset, while this repository contains my independently produced annotation and analysis artifacts. Users should obtain the original corpus directly from NCBI and follow the applicable terms governing its use and redistribution.
https://www.ncbi.nlm.nih.gov/CBBresearch/Dogan/DISEASE/

## Method
Manual annotations were compared with gold annotations using normalized **PMID + text span + category** matching. Whitespace and case were normalized; duplicate mentions were retained rather than collapsed.

## Results

| Metric                                        | Result |
| --------------------------------------------- | -----: |
| Abstracts                                     |     50 |
| Gold annotations                              |    385 |
| Manual annotations                            |    376 |
| Exact span + category matches                 |    364 |
| Span/boundary differences                     |      9 |
| Category differences                          |      3 |
| Gold-only omissions                           |      9 |
| Manual-only annotations                       |      0 |
| Exact-match precision                         |  96.8% |
| Exact-match recall                            |  94.5% |
| Exact-match F1                                |  95.6% |
| Abstracts with exact annotation-set agreement |  34/50 |

### Category-level results

| category         |   gold |   manual |   tp |   fp |   fn |   precision |   recall |       f1 |
|:-----------------|-------:|---------:|-----:|-----:|-----:|------------:|---------:|---------:|
| specificdisease  |    216 |      219 |  212 |    7 |    4 |    0.968037 | 0.981481 | 0.974713 |
| diseaseclass     |     66 |       55 |   53 |    2 |   13 |    0.963636 | 0.80303  | 0.876033 |
| compositemention |     14 |       14 |   14 |    0 |    0 |    1        | 1        | 1        |
| modifier         |     89 |       87 |   84 |    3 |    5 |    0.965517 | 0.94382  | 0.954545 |

## Error analysis
The main remaining errors involve DiseaseClass recall, SpecificDisease/DiseaseClass classification, and coverage of less-obvious disease-related expressions.

## Portfolio relevance
This project demonstrates applied medical text annotation and QA using a real biomedical corpus. It is intended to support applications for medical data annotation, clinical text labeling, healthcare AI evaluation, and medical AI training-data QA roles.

## Repository structure
```text
clinical-ai-annotation-portfolio/
├── README.md
├── docs/
│   ├── annotation_guidelines.md
│   ├── methodology.md
│   └── error_taxonomy.md
├── annotations/
│   ├── manual_annotations.jsonl  
├── analysis/
│   └── annotation_quality_report.md
└── results/
    ├── agreement_summary.csv
    └── error_summary.csv
```
## Final comparison summary
The 50-abstract comparison contains **376** manual annotations and **385** gold annotations: **364** exact matches, 9 span/boundary differences, 3 category differences, 9 gold-only omissions, and 0 manual-only annotations. Exact-match precision is **96.8%**, recall **94.5%**, and F1 **95.6%**. When boundary and category disagreements are separated from genuine omissions, **97.7%** of gold annotations have a corresponding manual annotation.
