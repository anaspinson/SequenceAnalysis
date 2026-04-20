# Bacterial Transcriptome Analysis Pipeline (Snakemake)

## Overview
This project implements a **reproducible Snakemake workflow** for bacterial transcriptome analysis using RNA-seq data.

The pipeline covers the full analysis process:
1. Quality control and preprocessing
2. Optional de novo genome assembly
3. Read alignment and gene quantification
4. Differential gene expression (DGE) analysis
5. Phylogenetic analysis

The workflow is designed to be flexible, supporting both:
- Reference-based abalysis
- De novo genome assembly when no reference is available

---

## Workflow Summary
<p align="center">
  <img src="figures/Bacterial Transcriptome Analysis Workflow.jpeg" width="700">
</p>

## Tools
- **Workflow management**: Snakemake  
- **QC & preprocessing**: FastQC, Cutadapt  
- **Assembly**: MEGAHIT, QUAST, Pilon  
- **Annotation**: Prokka, BLAST+  
- **Alignment**: HISAT2, Bowtie2, samtools  
- **Quantification**: featureCounts (Subread)  
- **Differential expression**: DESeq2 (R, Bioconductor)  
- **Phylogenetics**: Clustal Omega, FastTree, Toytree  
- **Other tools**: Kraken2, BEDtools, seqtk  

---

## Key Features

- Modular and scalable Snakemake workflow  
- Supports both **reference-based** and **reference-free (de novo)** analysis  
- Automated quality control with MultiQC reports  
- Integrated statistical analysis using R (DESeq2)  
- End-to-end pipeline from raw reads to biological insights  

---

## Results (Example Dataset)

The workflow was tested on RNA-seq data from *Shigella flexneri* (16 samples):

- Identified **78 differentially expressed genes** (reference-based analysis)
- Generated:
  - MA plots
  - Volcano plots
  - Heatmaps of top DE genes
- Constructed phylogenetic trees (de novo workflow)

Some limitations observed:
- Annotation quality strongly impacts downstream analysis  
- Long runtimes for multiple sequence alignment (Clustal Omega)  
- De novo assembly requires careful parameter tuning  

---

## My Contribution

This project was developed as part of a collaborative academic project for an Applied Sequence Analysis course, part of the Bioinformatics MSc program at FU Berlin. The course focused on building reproducible sequencing workflows.

My contributions included:
- Designing and implementing parts of the Snakemake workflow  
- Integrating RNA-seq preprocessing, alignment, and DGE steps  
- Developing and running DESeq2 analysis in R  
- Interpreting results and troubleshooting pipeline issues  
- Contributing to workflow design and final report

The original repository can be found here: 
https://github.com/rosareitmeir/SequencingAnalysis

---

## Reproducibility

The workflow follows **Snakemake best practices** for reproducibility:
- Configurable parameters via config file  
- Modular rule-based design  
- Clear separation of steps  
- Support for different analysis modes  

To run the pipeline:

```bash
snakemake --cores N
