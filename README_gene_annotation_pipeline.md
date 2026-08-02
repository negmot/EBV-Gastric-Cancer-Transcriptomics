# Reproducible gene-annotation and DEG-integration package

This package reproduces the retained EBV-positive versus EBV-negative intestinal-type gastric cancer analysis based on GSE51575, GSE62254, and GSE66229.

## Run

Open `02_gene_annotation_and_deg_integration.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab and select **Run all**. The notebook searches for the required input files beside the notebook, in `data/`, or in `upload/`.

Required Python packages:

- Python 3
- pandas
- numpy
- openpyxl

## Reproduced results

- Significant probe-level records before symbol filtering: 8,372
- Records without usable gene symbols: 796
- Retained annotated probe-level records: 7,576
- Upregulated records: 3,118
- Downregulated records: 4,458
- Top records prioritized by absolute log2 fold change: 200

## Important provenance notes

The GSE62254 and GSE66229 GEO2R tables contain gene symbols. The retained GSE51575 table does not; its three significant probe annotations are recovered from the preserved `All(1).xlsx` result by exact matching on probe ID, adjusted p-value, and log2 fold change.

The historical workflow retained multi-symbol annotations such as `GENE1 /// GENE2` and repeated probe/gene-symbol records. Therefore, 7,576 is the number of annotated significant probe-level records, not the number of unique gene symbols. There are 5,256 distinct literal symbol labels in that table.

The historical Excel workbook automatically converted nine gene symbols beginning with `MARCH` or `SEPT` into dates. The notebook preserves their correct symbols from the original GEO2R text tables and explicitly tests for the historical conversion during validation.

## Outputs

Running the notebook creates `outputs_gene_annotation/` containing:

- `01_input_audit.csv`
- `02_all_significant_probe_records.tsv`
- `03_annotated_probe_records.tsv`
- `04_top200_by_absolute_logFC.tsv`
- `05_processing_summary.csv`
- `06_reproduction_checks.csv`
