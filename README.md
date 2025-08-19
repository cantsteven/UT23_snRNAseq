# Guerin et al., 2025: UT23_snRNAseq Publication
## Overview
This repository contains code for the data analysis of "Mycobacterium vaccae immunization ameliorates the inflammatory environment in the aging brain" (Guerin et al., 2025)

There are two quarto documents used for this analysis. The "other" folder contains various test files with code that was not used in the publication. 
### UT23_scRNAseq.qmd 

This Quarto file documents the single-nucleus RNA-seq analysis workflow using the Seurat package in R. It covers the steps from data import (reading .h5 count matrices), sample metadata annotation, quality control, filtering, normalization, batch integration with Harmony, clustering, marker gene identification, initial visualization, cell type annotation, and saves a processed Seurat object. 

### ut23_graphs_2.pmd

This Quarto file reads in the Seurat object processed in UT23_scRNAseq.qmd, normalizes and annotates the data, generates multiple plots summarizing cell type distributions and marker expression, and conducts differential gene expression analysis between experimental groups for various cell types. It then visualizes the results with volcano plots and gene set enrichment analyses (GO and KEGG), producing figures for each cell type. 

## Dependencies 
The following R packages were used in each Quarto document: 
### UT23_scRNAseq.qmd 
- tidyverse
- Seurat
- hdf5r
- sctransform
- glmGamPoi
- harmony

### UT23_scRNAseq.qmd 
- tidyverse
- patchwork
- figpatch
- SeuratObject
- RColorBrewer
- Seurat
- EnhancedVolcano
- ggthemes
- ggprism
- pheatmap
- MAST
- harmony
- Matrix
- dittoSeq
- org.Rn.eg.db
- AnnotationDbi
- clusterProfiler
- genekitr
- scales
- fgsea
