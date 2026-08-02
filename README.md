# EBV Gastric Cancer Transcriptomics

A reproducible Python workflow for annotation and cross-dataset processing of differential-expression records in Epstein–Barr virus-positive versus Epstein–Barr virus-negative intestinal-type gastric cancer.

## Overview

This repository contains the input data, computational notebook, reference outputs, and documentation used to reproduce the gene-annotation and differential-expression record-integration stage of the study.

The workflow processes dataset-specific GEO2R results from three independent Gene Expression Omnibus datasets:

- GSE51575
- GSE62254
- GSE66229

The comparison of interest is EBV-positive versus EBV-negative intestinal-type gastric cancer.

This workflow does not pool raw expression matrices and does not perform a formal cross-platform meta-analysis. Instead, it reproduces the annotation, filtering, retention, and prioritization of significant differential-expression records obtained from the individual GEO2R analyses.

## Repository Structure

```text
EBV-Gastric-Cancer-Transcriptomics/
├── data/
│   ├── All(1).xlsx
│   ├── All_filtered(1).xlsx
│   ├── GSE51575.top.table_Intestinal.tsv
│   ├── GSE62254_Intestinal_EBV+vs_.top.table.tsv
│   ├── GSE66229.top.table.tsv
│   └── Top200_DEGs(1).xlsx
├── reference_outputs/
│   ├── 01_input_audit.csv
│   ├── 02_all_significant_probe_records.tsv
│   ├── 03_annotated_probe_records.tsv
│   ├── 04_top200_by_absolute_logFC.tsv
│   ├── 05_processing_summary.csv
│   └── 06_reproduction_checks.csv
├── 02_gene_annotation_and_deg_integration.ipynb
├── README_gene_annotation_pipeline.md
├── requirements.txt
├── CITATION.cff
├── LICENSE
└── README.md
