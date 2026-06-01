# Single-Cell-Liver-Fibrosis-Analysis
Mini-Pipeline for Discovery and Prioritization of Cell-Type-Specific Biomarkers in Human Liver Fibrosis
# Mini-Pipeline for Discovery and Prioritization of Cell-Type-Specific Biomarkers in Human Liver Fibrosis

## Overview

This project analyzes publicly available human liver single-cell RNA-seq data from GSE136103 to identify fibrosis-associated cell populations, disease-linked cellular states, and translational biomarker candidates for human liver cirrhosis.

The analysis focuses on:

- Hepatic stellate / fibroblast-like cells
- Myeloid / macrophage populations
- Endothelial cells
- Fibrosis-associated gene signatures
- Biomarker prioritization

## Dataset

Primary dataset:

- GSE136103: Resolving the fibrotic niche of human liver cirrhosis using single-cell transcriptomics

The raw matrix files were downloaded from GEO and processed locally. Raw data files are not included in this repository due to file size.

## Repository Structure

```text
notebooks/
  01_load_qc_annotation.ipynb
  02_celltype_DE_biomarkers.ipynb

figures/
  umap_cell_types.png
  umap_condition.png
  cell_type_composition.png
  stellate_subclusters.png
  stellate_state_proportions.png
  timp1_tgm2_violins.png

results/
  liver_DE_by_celltype.csv
  ranked_biomarker_candidates.csv
  pathway/
    stellate_pathway_enrichment.csv

report/
  executive_summary.pdf
  written_screening_responses.pdf

environment/
  requirements.txt
