# TCGA-LUAD Differential Expression Analysis

Differential gene expression analysis of lung adenocarcinoma (LUAD)
tumour vs normal tissue using public TCGA RNA-seq data.

**Status:** work in progress (analysis done, report in preparation)

## Question
Which genes are differentially expressed between lung adenocarcinoma
tumour and normal lung tissue, and which biological processes do they
affect?

## Data
- Source: TCGA-LUAD, RNA-seq (STAR - Counts), via TCGAbiolinks (GDC)
- 540 primary tumour and 59 solid tissue normal samples
  (2 recurrent tumour samples excluded)
- 54,717 genes after filtering low-count genes

## Methods
- Differential expression: DESeq2 (tumour vs normal)
- Significance: adjusted p < 0.05 and |log2 fold change| > 1
- Visualisation: volcano plot (EnhancedVolcano), heatmap (pheatmap)
- Functional analysis: GO Biological Process enrichment
  (clusterProfiler), background = all tested genes

## Key results
- 11,868 genes upregulated and 3,288 downregulated in tumour
- Top upregulated genes include FAM83A, PYCR1, AFAP1-AS1, ETV4
- Upregulated genes enriched for cell division and chromatin
  organisation, and also for B cell / immunoglobulin terms
- Downregulated genes enriched for blood vessel, coagulation and
  extracellular matrix processes

## Limitations
- Unbalanced groups (540 tumour vs 59 normal)
- Bulk RNA-seq measures a mixture of cell types, so some differences
  may reflect tissue composition
- Differential expression does not detect DNA mutations

## Files
- `analysis.R`: full analysis script
- `figures/`: plots
- `results/`: results tables

## Reproducing
Run `analysis.R` in R (4.5). Data are downloaded from TCGA via
TCGAbiolinks. 
