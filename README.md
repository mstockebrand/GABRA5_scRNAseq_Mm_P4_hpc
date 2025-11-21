# GABRA5_scRNAseq_Mm_P4_hpc
scRNA-seq analysis of murine age P4 hippocampal dataset (Liebeskind et al. 2026, Commun Biol)

### [Introduction](#Introduction-1).

### [NGS dataset](#NGS-dataset-1)

### [dataset overview](#dataset-overview-and-pre-QC-parameters)

## [scRNA-seq data analysis](#analysis-workflow)

### [dataset loading and adjustment](#dataset-loading-and-adjustment-1)

### [QC](#qc-1)

### [doublet removal](#doublet-removal-1)

### [sample integration](#sample-integration-1)
  #### normalization, transformation, dimensionality reduction

### [clustering](#clustering-1)

##### molecular marker - identification and expression

### [cell type assignment](#cell-type-assignment-1)

##### cell type refinement

### [expression of genes of interest](#expression-of-genes-of-interest-1)

## Introduction
We analyzed the subset of wt mice from a previously analysed scRNA-seq dataset of a human patient mutation-derived Scn2a_p.A263V mouse model for SCN2A-associated developmental and epileptic encephalopathy (Reva et al. 2025, bioRxiv). Here, we focused on the expression of GABRA5 and related genes in wildtype (wt) mice at the age of postnatal day (P) 4 (Liebeskind et al. 2026, Commun Biol).

The dataset is available from EMBL-EBI's BioStudies database (http://www.ebi.ac.uk/biostudies) under accession number E-MTAB-15970 (https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-MTAB-15970).

## NGS dataset
Single cells were prepared from acute brain slices with a papain dissociation system (Worthington) and universal 3' gene expression library prep was performed with sc 3'  Demultiplexing, barcodes processing, gene counting and aggregations were performed with CellRanger version 4.00 (10X Genomics) by the sequencing facility (Cologne Center for Genomics, part of tha West German Sequencing Center) with murine reference genome (GRCm38/mm10). For this analysis we used the cell ranger aggregated ten sample containing dataset which required only minor adjustments during aggregation for normalizing the effective sequencing depth by downsampling (fraction of reads kept between 81 - 100% with mean ± s.d. = 91.9% ± 5.9%). 

### dataset overview and pre-QC parameters

| Sample | genotype: Scn2a_p.A263V | no. of cells | total reads | Ø reads /cell | median genes /cell | median UMI counts /cell | batch  |
| :---: | :---: | :---: | --- | :---: | :---: | :-------------: | :---: |
| **1** | mut/mut | 3,806 | 175,773,979 | 46,183 | 3,884 | 12,976 | 1 | 
| **2** | **wt/wt** | 3,362 | 153,336,015 | 45,609 | 3,458 | 10,801 | 1 | 
| **3** | wt/mut | 3,978 | 185,148,542 | 46,543 | 3,610 | 11,270 | 1 | 
| **4** | **wt/wt** | 2,531 | 132,854,755 | 52,491 | 3,839 | 12,149 | 2 | 
| **5** | wt/mut | 3,158 | 175,474,788 | 55,565 | 4,142 | 13,950 | 2 | 
| **6** | **wt/wt** | 3,870 | 189,599,838 | 48,992 | 3,730 | 11,801 | 3 | 
| **7** | wt/mut | 5,903 | 292,842,049 | 49,609 | 3,721 | 11,626 | 3 | 
| **8** | mut/mut | 3,607 | 197,687,623 | 54,807 | 3,651 | 11,355 | 3 | 
| **9** | **wt/wt** | 3,330 | 192,664,644 | 57,857 | 3,975 | 12,973 | 3 | 
| **10** | wt/mut | 4,644 | 262,851,819 | 56,600 | 3,850 | 12,308 | 3 | 

total of **13,093 wt cells**
We continue with the total dataset and subset wt dataset from the final integrated, cell type-assigned datast for genotype-phenotypic characterization to be performed elsewhere.


## Analysis workflow
scRNA-seq data analysis was performed in R with package Seurat and packages within (Hao et al. 2023 Nat Biotechnol, https://doi.org/10.1038/s41587-023-01767-y, https://satijalab.org/seurat/). 
It consisted of the following steps

### dataset loading and adjustment
The dataset aggregated by the cellranger pipeline was loaded and converted into a Seurat object. Metadata was updated with sample information and some QC-parameters.

### QC
QC consisted of filtering cells with poor library quality based on library depth (n(detected transcripts), n(detected genes), percentage of mitochondrial content, etc.)

### doublet removal
Doublets were removed after detection with DoubletFinder (McGinnis et al. 2019, Cell Syst: https://doi.org/10.1016/j.cels.2019.03.003, https://github.com/chris-mcginnis-ucsf/DoubletFinder)

### sample integration

#### normalization, transformation dimensionality reduction
For clustering SCT normalization was performed, for plotting gene expression, we used log1p-normalization.

#### integration of samples
We chose CCA-Integration method.

### clustering

#### molecular marker - identification and expression

### cell type assignment

#### cell type refinement

### expression of genes of interest


