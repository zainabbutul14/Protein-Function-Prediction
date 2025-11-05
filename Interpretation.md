# Protein Function Prediction in Ovarian Cancer – Interpretation

This file provides a detailed interpretation of each analysis step for the six selected proteins: **KLK10, ERLIN1, LETMD1, DNAAF6, ZSWIM7, and KCTD13**.

---

## Step 1: Sequence Homology (BLASTp)

**Purpose:** Identify sequence homologs and infer protein functions based on similarity.

| Protein | Key Findings | Interpretation |
|----------|--------------|----------------|
| **KLK10**  | Top hit: KLK11 (E-value = 0.0, 43.4% identity) | Strong homology confirms KLK10 as a serine protease of the kallikrein family. Implicated in extracellular proteolysis. |
| **ERLIN1** | Top hit: ERLIN2 (E-value = 0.0, 78.8% identity) | ERLIN1 and ERLIN2 are conserved paralogs involved in ER lipid regulation and protein degradation. |
| **LETMD1** | No significant non-self hit | Indicates divergence or low conservation; requires domain-based inference. |
| **DNAAF6** | No strong homologs detected | Low homology suggests a specialized structural role, possibly unique to dynein complex assembly. |
| **ZSWIM7** | Only self-hit (E-value = 0.0) | May be evolutionarily unique; function must be inferred through domain structure. |
| **KCTD13** | Top hits: KCTD10 and TNFAIP1 (E-value ≈ 1.1×10⁻¹⁵², ~70% identity) | Highly conserved; likely functions as a CUL3 E3 ligase adapter protein. |

---

## Step 2: Domain and Motif Prediction (InterProScan)

**Purpose:** Identify conserved motifs and domains defining structure and function.

| Protein | Detected Domain | Tool (E-value) | Functional Insight |
|----------|-----------------|----------------|--------------------|
| **KLK10** | Trypsin-like serine protease domain | Pfam (1.9×10⁻⁵⁴) | Secreted protease that cleaves peptide bonds; contributes to ECM remodeling. |
| **ERLIN1** | SPFH/Band 7 domain + Transmembrane region | Pfam (9.9×10⁻²⁹) | ER membrane component in lipid and protein homeostasis. |
| **LETMD1** | LETM1-like ribosome-binding domain | Pfam (7.3×10⁻⁶²) | Mitochondrial Ca²⁺/H⁺ antiporter; regulates metabolism and apoptosis. |
| **DNAAF6** | PIH1 CS-like domain | Pfam (0.0091) | Involved in assembly of axonemal dynein motors; essential for cilia formation. |
| **ZSWIM7** | SWIM-type zinc finger | PANTHER (2.3×10⁻⁴⁷) | DNA/RNA-binding protein; potential transcriptional regulator or repair factor. |
| **KCTD13** | BTB/POZ domain | Pfam (7.3×10⁻¹⁶) | Confirms function as an E3 ligase adapter for protein ubiquitination. |

---

## Step 3: Expression Profiling (GEPIA3 – TCGA Ovarian Cancer)

**Purpose:** Evaluate differential expression between tumor and normal ovarian tissues.

| Gene | Median Tumor | Median Normal | p-Value | Trend | Biological Implication |
|------|---------------|---------------|----------|--------|------------------------|
| **KLK10** | 6.85 | 4.39 | 3.1×10⁻²⁷ | ↑ Upregulated | Oncogenic protease; promotes invasion and metastasis. |
| **KCTD13** | 3.74 | 4.59 | 1.9×10⁻²⁹ | ↓ Downregulated | Loss of degradation control; potential tumor suppressor. |
| **ZSWIM7** | 3.86 | 5.18 | 2.5×10⁻⁵⁵ | ↓ Downregulated | Candidate tumor suppressor; possible DNA repair regulator. |
| **LETMD1** | 5.24 | 6.29 | 2.9×10⁻³² | ↓ Downregulated | Mitochondrial dysfunction in tumors. |
| **ERLIN1** | 3.68 | 3.87 | 2.1×10⁻³ | ↓ Slightly downregulated | Mild effect; involved in ER stress and lipid regulation. |
| **DNAAF6** | 0.04 | 0.0 | 4.5×10⁻⁵ | ↑ Upregulated | Low expression but statistically significant; possible ciliary signaling link. |

**Visual Evidence:** Expression boxplots confirm trends (KLK10↑, DNAAF6↑, ZSWIM7↓, KCTD13↓, LETMD1↓, ERLIN1↓).

---

## Step 4: Functional Enrichment (g:Profiler)

**Purpose:** Identify shared biological processes, pathways, and transcription factors.

| Category | Key Enrichment Terms | p-Value | Interpretation |
|-----------|----------------------|----------|----------------|
| **Transcription Factor (TF)** | SOX4, ETV/PEA3, SREBP-1 | <0.01 | Shared upstream regulators of EMT, invasion, and metabolism. |
| **GO: Cellular Component** | Intracellular membrane-bounded organelle | 0.0093 | Suggests mitochondrial and ER functional disruption. |
| **GO: Biological Process** | Protein ubiquitination, DNA repair, metabolic regulation | <0.005 | Central roles in genomic stability and stress adaptation. |

**Takeaway:** The six genes form a cohesive regulatory network driven by master cancer regulators (**SOX4**, **ETV**, **SREBP-1**), connecting DNA repair, metabolism, and organelle function.

---

## Step 5: Protein-Protein Interaction Network (STRING)

**Purpose:** Explore molecular connectivity and identify functional hubs.

| Core Gene | High-Confidence Partner | Combined Score | Functional Link |
|------------|--------------------------|----------------|-----------------|
| **ZSWIM7** | SWSAP1 | 0.996 | DNA repair complex; homologous recombination. |
| **KCTD13** | TNFAIP1 | 0.989 | Ubiquitin ligase activity; apoptosis and inflammation. |
| **ERLIN1** | RNF185 | 0.915 | ERAD pathway; protein quality control. |

**Network Summary:**

* Three modules observed:
  1. **DNA Repair Cluster:** ZSWIM7–SWSAP1  
  2. **Protein Quality Control:** ERLIN1–RNF185–LETMD1  
  3. **Ubiquitination/Signaling:** KCTD13–TNFAIP1–KLK10  

**Interpretation:** Even without direct connections, these proteins act as a functionally cohesive module centered on maintaining cellular stability and stress balance.

---

## Final Biological Interpretation

| Category | Upregulated | Downregulated | Functional Theme |
|-----------|--------------|----------------|------------------|
| **Protease Activity** | KLK10 | — | ECM degradation & invasion |
| **ER/Organelle Quality Control** | — | ERLIN1 | Protein homeostasis |
| **Mitochondrial Regulation** | — | LETMD1 | Metabolic control |
| **Ciliary Signaling** | DNAAF6 | — | Cell motility, signaling |
| **DNA Repair** | — | ZSWIM7 | Genome stability |
| **Ubiquitin Signaling** | (varies) KCTD13 | — | Protein degradation & apoptosis |

**Conclusion:**  
The combined loss of **ZSWIM7**, **LETMD1**, and **KCTD13**, coupled with overexpression of **KLK10** and **DNAAF6**, outlines a potential molecular signature of ovarian cancer characterized by impaired repair, disrupted metabolism, and enhanced invasiveness.

---

## Summary of Biological Insights

- **ZSWIM7** and **KCTD13**: Likely tumor suppressors regulating genome and protein stability.  
- **LETMD1**: Mitochondrial regulator; downregulation implies metabolic dysregulation.  
- **KLK10**: Oncogenic protease and biomarker candidate.  
- **ERLIN1**: Supports ER stress adaptation and protein folding.  
- **DNAAF6**: Links to altered ciliary dynamics in tumors.

---

## Future Directions

- Perform survival analysis (GEPIA3) to correlate expression with patient prognosis.  
- Expand STRING to include first-shell interactors for deeper network context.  
- Validate functional predictions through structural modeling or literature mining.

---

**This file complements the main `README.md` by providing a detailed, stepwise interpretation of all analyses conducted in this project.**
