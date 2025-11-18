# GABRA5_scRNAseq_Mm_P4_hpc
scRNA-seq analysis of murine age P4 hippocampal dataset

### [Introduction](#Introduction-1).

### [NGS dataset](#NGS-dataset-1)

### [dataset overview](#dataset-overview-and-pre-QC-parameters)

## [scRNA-seq data analysis](#analysis-workflow)

### [dataset aggregation](#dataset-aggregation-1)

### [QC](#qc-1)

### [doublet removal](#doublet-removal-1)

### [sample integration](#sample-integration-1)
  #### normalization, transformation, dimensionality reduction

### clustering

### cluster refinement

### marker identification and selection

### cell type assignment

### expression of genes of interest

## Introduction
We analyzed the subset of wt mice from a previously analysed scRNA-seq dataset from the human patient derived Scn2a_p.A263V mouse model for human SCN2A-associated developmental and epileptic encephalopathy (Reva et al. 2025, bioRxiv). Here, we focused on the expression of GABRA5 and related genes in wt mice at age of postnatal day (P) 4.

## NGS dataset
Demultiplexing, barcodes processing, gene counting and aggregations were made using the CellRanger version XXX (10X Genomics) by the sequencing facility (Cologne Center for Genomics, part of tha West German Sequencing Center) with murine reference genome (GRCm38/mm10). 

### dataset overview and pre-QC parameters

| Sample | genotype: Scn2a_p.A263V | no. of cells | total reads | Ø reads /cell | median genes /cell | median UMI counts /cell |
| :---: | :---: | :---: | --- | :---: | :---: |------------- |
| **1** | mut/mut | 1,316 | 125,560,642 | 95,411 | 6,622 | 38,745 | 
| **2** | wt/wt | 3,101 | 270,454,600 | 87,215 | 6,286 | 31,056 | 
| **3** | mut/wt | 3,818 | 309,772,057 | 81,135 | 6,404 | 32,473 | 
| **4** | wt/wt  | 1,348	| 116,983,834 | 86,783 | 6,496 | 36,345 | 
| **5** | mut/wt | 4,271 | 421,293,097 | 98,640 | 6,611 | 36,201 | 
| **6** | wt/wt  | 3,302 | 285,222,272 | 86,379 | 6,468 | 34,010 | 
| **7** | mut/wt | 4,616 | 339,856,499 | 73,626 | 6,253 | 31,347 | 
| **8** | mut/mut | 2,454 | 193,989,579 | 79,050 | 6,588 | 33,960 | 
| **9** | wt/wt  | 2,454 | 193,989,579 | 79,050 | 6,588 | 33,960 | 
| **10** | mut/wt | 2,454 | 193,989,579 | 79,050 | 6,588 | 33,960 | 

## Analysis workflow
scRNA-seq data analysis consisted of the following steps

### dataset aggregation

### QC

### doublet removal

### sample integration

#### normalization, transformation dimensionality reduction

#### integration of samples

### clustering

#### cluster refinement

#### marker identification and cell type assignment

### expression of genes of interest


