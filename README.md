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

## Workflow Summary
