# Protein Function Prediction in Ovarian Cancer
Predicting functions of uncharacterized human proteins using sequence, expression, and network analysis.

---

## Project Overview

This project focuses on **protein function prediction** using a combination of sequence similarity, domain analysis, expression profiling, and enrichment network exploration to identify potentially important or novel proteins involved in **ovarian cancer**.

Six proteins were selected to represent varying levels of annotation:

| Category | Proteins |
|-----------|-----------|
| **Uncharacterized** | ZSWIM7, DNAAF6 |
| **Partially Annotated** | LETMD1, ERLIN1, KCTD13 |
| **Well-Known** | KLK10 |

By integrating multiple computational tools, this study demonstrates how bioinformatics can uncover hidden biological roles, validate known biomarkers, and predict potential novel tumor suppressors or oncogenic regulators.

---
## Objectives

- Predict functional roles of poorly characterized human proteins.  
- Identify structural motifs and evolutionary relationships.  
- Assess gene expression patterns in ovarian cancer vs. normal tissue.  
- Explore pathway enrichment and protein–protein interactions to reveal disease mechanisms.

---
## Datasets and Tools Used

| Step | Tool / Database | Purpose |
|------|-----------------|----------|
| 1. Protein Sequence Retrieval | UniProt | Obtained FASTA sequences of selected proteins |
| 2. Sequence Similarity Search | NCBI BLASTp | Identified homologous proteins and inferred conserved functions |
| 3. Domain & Motif Prediction | InterProScan | Detected functional domains and structural motifs |
| 4. Expression Profiling | GEPIA3 (TCGA Data) | Compared tumor vs. normal gene expression |
| 5. Functional Enrichment | g:Profiler | Identified enriched pathways, transcription factors, and GO terms |
| 6. Protein Interaction Network | STRING  | Visualized biological interactions and network relationships |

---
## Workflow

1. **Protein Selection & FASTA Retrieval** → UniProt  
2. **Homology Search (BLASTp)** → Functional inference via top hits  
3. **Domain Analysis (InterPro)** → Structural motif annotation  
4. **Expression Profiling (GEPIA3)** → Clinical relevance evaluation  
5. **Functional Enrichment (g:Profiler)** → Pathway and TF enrichment  
6. **Network Analysis (STRING)** → Interaction visualization and hub identification

---
## What I Did

- Retrieved six protein sequences from UniProt and performed **BLASTp** analysis to identify sequence homology and evolutionary conservation.  
- Conducted **InterProScan** domain prediction to validate or uncover protein motifs.  
- Used **GEPIA3** for expression profiling to evaluate each gene’s differential regulation in ovarian cancer.  
- Performed **functional enrichment** with **g:Profiler** to identify shared transcriptional regulators (SOX4, ETV/PEA3, SREBP-1).  
- Built a **protein–protein interaction network** using **STRING**, revealing key hubs and pathway connectivity.

---
## Results Summary

| Gene | Main Function | Key Domain | Expression in Ovarian Cancer | Biological Role |
|-------|----------------|-------------|--------------------------------|------------------|
| **KLK10** | Serine protease | Trypsin domain | Upregulated (p≈10⁻²⁷) | Oncoprotein / Biomarker |
| **KCTD13** | E3 ligase adapter | BTB/POZ | Downregulated (p≈10⁻²⁹) | Potential tumor suppressor |
| **ZSWIM7** | DNA-binding / repair | SWIM zinc finger | Downregulated (p≈10⁻⁵⁵) | Novel tumor suppressor candidate |
| **LETMD1** | Mitochondrial regulator | LETM1-like RBD | Downregulated (p≈10⁻³²) | Loss of mitochondrial function |
| **ERLIN1** | ER protein quality control | SPFH/Band 7 | Slightly downregulated (p≈10⁻³) | ER stress response factor |
| **DNAAF6** | Dynein assembly factor | PIH1-like domain | Upregulated (p≈10⁻⁵) | Altered cell motility / signaling |

**Key Findings**

- Downregulation of **ZSWIM7**, **LETMD1**, and **KCTD13** may contribute to loss of genomic stability, mitochondrial dysfunction, and protein quality control in ovarian cancer.  
- **KLK10** and **DNAAF6** show oncogenic or adaptive upregulation, supporting cancer progression mechanisms.  
- **g:Profiler** analysis links the gene set to **SOX4**, **ETV/PEA3**, and **SREBP-1** — master regulators of epithelial–mesenchymal transition (EMT) and metabolic reprogramming.

---
## What I Learned

- How to build a **computational protein annotation pipeline** from sequence to function.  
- Integrating **sequence, structure, and expression data** reveals functional insights even for uncharacterized proteins.  
- Learned practical use of bioinformatics tools: **BLASTp, InterPro, GEPIA3, g:Profiler, STRING**.  
- Understood how computational biology connects molecular functions to disease mechanisms.

---

## Impact and Achievements

- Predicted **new potential tumor suppressor proteins** in ovarian cancer (ZSWIM7, LETMD1).  
- Validated the known biomarker **KLK10** using a computational multi-step approach.  
- Identified **SOX4** and **SREBP-1** as upstream transcriptional regulators linking these genes to cancer hallmarks.  
- Built a **multi-level functional annotation pipeline** that can be applied to other diseases.

---
## Conclusion

This project demonstrates how raw protein sequences can be transformed into biological hypotheses using integrated computational pipelines.  
It highlights the power of **bioinformatics-driven discovery** to uncover functional and clinical insights relevant to human disease — even in the absence of wet-lab data.

---

## Repository Structure
```
protein-function-prediction/
├── data
│   ├── BLASTp.csv
│   ├── BOXPLOT EXPRESSION GEPIA3.csv
│   ├── FASTA_sequences.fasta
│   ├── gprofiler_results.csv
│   ├── interpro results.csv
│   └── string_interactions.tsv
└── Figures
    ├── DNAAF6 BOXPLOT.png
    ├── ERLIN1 BOXPLOT.png
    ├── KCTD13 BOXPLOT.png
    ├── KLK10 BOXPLOT.png
    ├── LETMD1 BOXPLOT.png
    ├── STRING NETWORK.png
    └── ZSWIM7 BOXPLOT.png
```
---

## Additional File Suggestion

**`Interpretation.md`**

A supplementary file summarizing detailed step-by-step results for each protein:

- Step 1: BLASTp interpretation  
- Step 2: InterPro domain analysis summary  
- Step 3: GEPIA3 differential expression results  
- Step 4: g:Profiler enrichment terms  
- Step 5: STRING network interpretation

This helps keep the README concise and makes the repository more organized.

---

## Acknowledgment

This project was completed as part of an independent bioinformatics research exercise for **protein function prediction in ovarian cancer**.  
Special thanks to:

- **NCBI**, **UniProt**, **InterPro**, **GEPIA3**, **g:Profiler**, and **STRING** for providing open-access biological databases and analytical platforms.

---

# License

This repository is licensed under the MIT License.
