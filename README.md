# Zenodo Version 2 upload set

This archive supports the revised manuscript on EBV-associated intestinal-type gastric cancer. It replaces the historical three-dataset probe-concatenation/top-200 workflow in Version 1 with two independent cohorts (GSE51575 and GSE62254), probe-to-gene reduction, inverse-variance fixed-effect meta-analysis, concordant-direction filtering, and downstream analysis of 606 genes.

Upload the six numbered ZIP files together with `README.md`, `requirements.txt`, `LICENSE`, and `CITATION.cff` as a **new version of the existing Zenodo record**. Use the DOI minted by Zenodo; do not select “I already have a DOI.”

## Packages

1. `01_GEO_cross_cohort_meta_analysis.zip` — processed probe-level inputs, sample audit, dataset-specific gene results, full meta-analysis table, and the 606-gene primary set.
2. `02_PPI_hub_enrichment_analysis.zip` — STRING input/network, centrality tables, four cytoHubba top-five exports, enrichment results, source JSON, and figures.
3. `03_TCGA_STAD_EBV_expression_analysis.zip` — EBV-stratified TCGA-STAD expression analysis, local inputs, statistics, sample-level outputs, workbook, and figures.
4. `04_TCGA_STAD_survival_analysis.zip` — analysis-ready TCGA inputs, Cox and Kaplan–Meier outputs, workbook, and figures.
5. `05_DGIdb_exploratory_drug_gene_analysis.zip` — raw DGIdb response, complete and selected associations, Cytoscape import tables, workbook, figures, and retrieval script.

## Core selection logic

- Independent cohorts: GSE51575 and GSE62254.
- GSE66229 is not an independent cohort; it is the SuperSeries containing GSE62254.
- Meta-analysis: inverse-variance fixed effect.
- Primary set: concordant direction in both cohorts and BH-adjusted meta-analysis P < 0.05.
- Primary set size: 606 genes.
- STRING threshold: combined score >= 0.40.
- Hub genes: union of the top five genes from MCC, MNC, Degree, and DMNC, yielding CD8A, IFNG, CCR7, PTPRC, GZMB, TNFRSF4, NCR1, IL21R, CXCR6, ENTPD1, CD2, and LCK.

## Transparency note

The native Cytoscape session file (main_network.cys) is provided in 06_Cytoscape_network.zip. Network module detection was performed using the CytoCluster plugin with the IPCA algorithm and a threshold of 0.9. Cluster-level tables and figures are reported in the manuscript and supplementary materials..

## Data sources

GEO: GSE51575 and GSE62254. TCGA-STAD PanCancer Atlas data were obtained through cBioPortal. Network and enrichment sources were STRING v12 and Enrichr. Drug–gene associations were obtained from DGIdb v5.0 on 2026-08-04.
