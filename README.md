# Guerin et al., 2025: UT23_snRNAseq Publication
## Overview
This repository contains code for the data analysis of "Mycobacterium vaccae immunization ameliorates the inflammatory environment in the aging brain" (Guerin et al., 2025)

There are two quarto documents used for this analysis. The "other" folder contains various test files with code that was not used in the publication. Finally, there is a .CSV file that contains a list of inflammatory genes used for part of the analysis. 

### UT23_scRNAseq.qmd 

This Quarto file documents the single-nucleus RNA-seq analysis workflow using the Seurat package in R. It covers the steps from data import (reading .h5 count matrices), sample metadata annotation, quality control, filtering, normalization, batch integration with Harmony, clustering, marker gene identification, initial visualization, cell type annotation, and saves a processed Seurat object. 

### ut23_graphs_2.pmd

This Quarto file reads in the Seurat object processed in UT23_scRNAseq.qmd, normalizes and annotates the data, generates multiple plots summarizing cell type distributions and marker expression, and conducts differential gene expression analysis between experimental groups for various cell types. It then visualizes the results with volcano plots and gene set enrichment analyses (GO and KEGG), producing figures for each cell type. 

### inflammatorygenelist.csv

All significant DEGs within each cell type cluster were compared to this list of 757 known neuroinflammation related genes (nCounter® Human Neuroinflammation Panel, nanoString). 

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

## References
### tidyverse

Wickham H, Averick M, Bryan J, Chang W, McGowan LD, François R, Grolemund G, Hayes A, Henry L, Hester J, Kuhn M, Pedersen TL, Miller E, Bache SM, Müller K, Ooms J, Robinson D, Seidel DP, Spinu V, Takahashi K, Vaughan D, Wilke C, Woo K, Yutani H (2019). "Welcome to the tidyverse." Journal of Open Source Software, 4(43), 1686. doi:10.21105/joss.01686

### Seurat

Hao Y, Hao S, Andersen-Nissen E, Mauck WM, Zheng S, Butler A, Lee MJ, Wilk AJ, Darby C, Zager M, Hoffman P, Stoeckius M, Papalexi E, Mimitou EP, Jain J, Srivastava A, Stuart T, Fleming LM, Yeung B, Rogers AJ, McElrath J, Blish CA, Satija R (2021). "Integrated analysis of multimodal single-cell data." Cell, 184(13):3573-3587.e29. doi:10.1016/j.cell.2021.04.048

### hdf5r

Pau S, Fuchs M, Sklyar O, Boutros M, Huber W (2022). hdf5r: Interface to the HDF5 Library. R package version 1.3.8. https://CRAN.R-project.org/package=hdf5r

### sctransform

Hafemeister C, Satija R (2019). "Normalization and variance stabilization of single-cell RNA-seq data using regularized negative binomial regression." Genome Biology, 20(1), 296. doi:10.1186/s13059-019-1874-1

### glmGamPoi

Ahlmann-Eltze C, Huber W (2020). "glmGamPoi: fitting Gamma-Poisson generalized linear models on single cell count data." Bioinformatics, 36(22-23), 5701–5702. doi:10.1093/bioinformatics/btaa1009

### harmony

Korsunsky I, Millard N, Fan J, Slowikowski K, Zhang F, Wei K, Baglaenko Y, Brenner M, Loh PR, Raychaudhuri S (2019). "Fast, sensitive and accurate integration of single-cell data with Harmony." Nature Methods, 16(12):1289-1296. doi:10.1038/s41592-019-0619-0

### patchwork

Pedersen TL (2020). patchwork: The Composer of Plots. R package version 1.1.3. https://CRAN.R-project.org/package=patchwork

### figpatch

Pedersen TL (2024). figpatch: Compose Plots with Patchwork. R package version 0.1.2. https://CRAN.R-project.org/package=figpatch

### SeuratObject

Satija Lab (2024). SeuratObject: Data Structures for Single Cell Genomics. R package version 4.1.4. https://CRAN.R-project.org/package=SeuratObject

### RColorBrewer

Neuwirth E (2014). RColorBrewer: ColorBrewer Palettes. R package version 1.1-2. https://CRAN.R-project.org/package=RColorBrewer

### EnhancedVolcano

Blighe K, Rana S, Lewis M (2019). "EnhancedVolcano: Publication-ready volcano plots with enhanced colouring and labeling." R package version 1.17.0. https://github.com/kevinblighe/EnhancedVolcano

### ggthemes

Arnold JB (2021). ggthemes: Extra Themes, Scales and Geoms for 'ggplot2'. R package version 4.2.4. https://CRAN.R-project.org/package=ggthemes

### ggprism

Edwards K (2022). ggprism: A 'ggplot2' Extension Inspired by 'GraphPad Prism'. R package version 1.0.4. https://CRAN.R-project.org/package=ggprism

### pheatmap

Kolde R (2019). pheatmap: Pretty Heatmaps. R package version 1.0.12. https://CRAN.R-project.org/package=pheatmap

### MAST

Finak G, McDavid A, Yajima M, Deng J, Gersuk V, Shalek AK, Slichter CK, Miller HW, McElrath MJ, Prlic M, Linsley PS, Gottardo R (2015). "MAST: a flexible statistical framework for assessing transcriptional changes and characterizing heterogeneity in single-cell RNA sequencing data." Genome Biology, 16, 278. doi:10.1186/s13059-015-0844-5

### Matrix

Bates D, Maechler M, Modregger P, Walker S (2024). Matrix: Sparse and Dense Matrix Classes and Methods. R package version 1.7-0. https://CRAN.R-project.org/package=Matrix

### dittoSeq

Bunis DG, Andrews J, Fragiadakis GK, Bintz M, Dhariwal A, Krentz NAJ, Ng B, Balagtas J, Christian E, McCoy J, Tung A, Spitzer MH, Nolan GP, Yosef N (2020). "dittoSeq: A user-friendly, modular R package for single-cell RNA sequencing data analysis." BMC Bioinformatics, 21, 296. doi:10.1186/s12859-020-03684-z

### org.Rn.eg.db

Carlson M (2023). org.Rn.eg.db: Genome wide annotation for Rat. R package version 3.18.0. https://bioconductor.org/packages/org.Rn.eg.db/

### AnnotationDbi

Carlson M (2023). AnnotationDbi: Manipulation of SQLite-based annotations in Bioconductor. R package version 1.64.1. https://bioconductor.org/packages/AnnotationDbi/

### clusterProfiler

Yu G, Wang LG, Han Y, He QY (2012). "clusterProfiler: an R package for comparing biological themes among gene clusters." OMICS: A Journal of Integrative Biology, 16(5), 284-287. doi:10.1089/omi.2011.0118

### genekitr

Liu S, Gao F, Li M, Wu J, Gao Y, Zhang Y, Liu Y, Wang H, Li J, Gao C (2023). "genekitr: a comprehensive toolkit for gene-centric bioinformatics analysis." Bioinformatics, 39(1), btac707. doi:10.1093/bioinformatics/btac707

### scales

Wickham H, Seidel D (2022). scales: Scale Functions for Visualization. R package version 1.2.1. https://CRAN.R-project.org/package=scales

### fgsea

Korotkevich G, Sukhov V, Budin N, Shpak B, Artyomov MN, Sergushichev A (2021). "Fast gene set enrichment analysis." bioRxiv, doi:10.1101/060012
