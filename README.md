# Single-Cell-Liver-Fibrosis-Analysis
Mini-Pipeline for Discovery and Prioritization of Cell-Type-Specific Biomarkers in Human Liver Fibrosis
# Mini-Pipeline for Discovery and Prioritization of Cell-Type-Specific Biomarkers in Human Liver Fibrosis

# Mini-Pipeline for Discovery and Prioritization of Cell-Type-Specific Biomarkers in Human Liver Fibrosis

## Overview

This project analyzes publicly available human liver single-cell RNA sequencing data from GSE136103 to identify fibrosis-associated cell populations, disease-linked cellular states, and candidate biomarkers for human liver cirrhosis.

The objective was to build a compact end-to-end workflow that demonstrates dataset curation, quality control, cell-type annotation, differential expression analysis, pathway interpretation, and biomarker prioritization for translational applications.

---

## Dataset

Primary Dataset

- GSE136103: Resolving the fibrotic niche of human liver cirrhosis using single-cell transcriptomics

This dataset contains healthy and cirrhotic human liver samples profiled using single-cell RNA sequencing.

---

## Analysis Workflow

### 1. Data Loading and Metadata Curation
- Downloaded and processed GSE136103 data
- Curated healthy and cirrhotic sample metadata
- Created condition labels for downstream comparisons

### 2. Quality Control
Cells were filtered using:

- Number of detected genes
- Total UMI counts
- Percentage mitochondrial reads

After quality control:

- 60,455 cells retained
- 33,694 genes retained

### 3. Data Preprocessing
- Library size normalization
- Log transformation
- Highly variable gene selection
- Scaling of expression values

### 4. Dimensionality Reduction and Clustering
- Principal Component Analysis (PCA)
- Neighborhood graph construction
- UMAP visualization
- Leiden clustering

### 5. Cell Type Annotation
Major liver cell populations were annotated using canonical marker genes.

Identified populations:

| Cell Type | Number of Cells |
|------------|----------------|
| T cells | 20,473 |
| NK cells | 11,874 |
| Myeloid | 10,905 |
| Endothelial | 7,838 |
| Hepatocyte | 4,199 |
| Cholangiocyte | 3,545 |
| Plasma cells | 1,233 |
| Fibroblast / Stellate | 296 |
| Mast | 92 |

---

## Disease-Relevant Compartments

The analysis focused on the three disease-relevant compartments requested in the assignment:

### Hepatic Stellate / Fibroblast Cells
A distinct activated stellate-cell state was identified and found to be strongly enriched in cirrhotic liver samples.

### Myeloid Cells
Myeloid populations displayed inflammatory signatures and fibrosis-associated transcriptional programs.

### Endothelial Cells
Endothelial cells showed evidence of vascular remodeling and fibrosis-associated activation.

---

## Cell Composition Changes in Cirrhosis

Comparison of healthy and cirrhotic samples revealed major shifts in cellular composition.

Notable findings:

- Expansion of cholangiocytes
- Expansion of endothelial cells
- Expansion of plasma cells
- Strong enrichment of activated stellate cells
- Relative depletion of hepatocytes

---

## Activated Stellate Cell Discovery

Fibroblast/stellate cells were isolated and re-clustered to identify fibrosis-associated states.

Two major stellate-cell states were identified:

| Cluster | Cirrhotic (%) | Healthy (%) |
|-----------|-------------|-------------|
| Cluster 0 | 59.9 | 96.3 |
| Cluster 1 | 40.1 | 3.7 |

Cluster 1 represents a cirrhosis-associated activated stellate-cell population.

---

## Differential Expression Analysis

Fibrosis-associated genes identified in activated stellate cells included:

- TIMP1
- TGM2
- CST3
- EFEMP1
- LGALS1
- CCL21
- IL32
- IFITM2
- IFITM3
- RAMP2

These genes are associated with:

- Extracellular matrix remodeling
- Fibrosis progression
- Inflammatory signaling
- Immune recruitment
- Tissue remodeling

---

## Pathway Analysis

Pathway enrichment analysis identified significant activation of:

- Cytokine response pathways
- Type I interferon signaling
- Type II interferon signaling
- Peptide cross-linking
- Protease regulation
- Receptor internalization
- Inflammatory stromal remodeling

Representative enriched genes:

- TIMP1
- TGM2
- CST3
- IFITM2
- IFITM3
- LGALS1
- CCL21
- ANXA1
- CD9

These findings support a model in which activated stellate cells contribute to both extracellular matrix deposition and inflammatory remodeling during fibrosis progression.

---

## Biomarker Prioritization

A rule-based biomarker prioritization framework was developed using:

- Differential expression strength
- Fibrosis relevance
- Translational potential
- Cell-state specificity

### Top Ranked Candidates

| Rank | Gene | Biological Role |
|--------|--------|----------------|
| 1 | TIMP1 | ECM remodeling and fibrosis biomarker |
| 2 | TGM2 | Matrix cross-linking and fibrosis progression |
| 3 | CST3 | Secreted fibrosis-associated protein |
| 4 | EFEMP1 | Activated stellate-state marker |
| 5 | LGALS1 | Immune-fibrosis signaling |
| 6 | CCL21 | Chemokine-mediated recruitment |
| 7 | IL32 | Inflammatory activation |
| 8 | IFITM2 | Interferon response |
| 9 | IFITM3 | Interferon response |
| 10 | RAMP2 | Stromal remodeling |

---

## Key Conclusions

1. A cirrhosis-associated activated stellate-cell population was identified.
2. Activated stellate cells were substantially enriched in cirrhotic liver samples.
3. Fibrosis-associated genes were dominated by extracellular matrix remodeling and inflammatory signaling programs.
4. Pathway analysis supported activation of cytokine-response and interferon-signaling pathways.
5. TIMP1, TGM2, and CST3 emerged as the strongest translational biomarker candidates.
6. The workflow demonstrates a reproducible framework for biomarker discovery and target prioritization in liver fibrosis.

---

## Reproducibility

### Required Packages

bash pip install scanpy anndata pandas numpy matplotlib seaborn scikit-learn gseapy leidenalg igraph 

### Recommended Environment

- Python 3.11+
- Scanpy
- AnnData
- Pandas
- NumPy
- Matplotlib
- GSEAPY

### Running the Analysis

Run notebooks in the following order:

1. Data loading and QC
2. Cell-type annotation
3. Differential expression analysis
4. Pathway analysis
5. Biomarker prioritization

---

## Author

Jhalak Trivedi

MS Bioinformatics, Georgetown University

2026



