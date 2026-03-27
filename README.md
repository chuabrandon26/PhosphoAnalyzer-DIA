# DIA Phosphoproteomics Analysis Pipeline

This repository contains a comprehensive pipeline for processing and analyzing Data-Independent Acquisition (DIA) phosphoproteomics data. The project focuses on quality control, data normalization, and the identification of significant phosphorylation sites in Jurkat cell lines.

## Project Overview
The primary goal of this analysis is to transform raw mass spectrometry outputs (from DIANN) into biologically meaningful insights. The pipeline includes robust data cleaning, statistical filtering, and visualization of global phosphorylation trends.

## Features
- **Data Cleanup & Filtering**: Automated removal of low-confidence identifications using Q-Value (< 0.01) and PEP (< 0.05) thresholds.
- **Duplicate Management**: Handles peptide-form duplicates by retaining high-confidence entries.
- **Quality Control**: Generates QC tables and descriptive statistics for precursor quantities and retention times.
- **Statistical Output**: Exports processed datasets into optimized formats for downstream differential expression analysis.

## Technical Stack
- **Language**: Python
- **Key Libraries**: Pandas, NumPy, Matplotlib, Seaborn
- **Data Source**: DIANN output (xlsx)

## Methodology
The pipeline follows a structured 6-step processing flow:
1. **Missing Value Assessment**: Evaluation of essential identifiers (Genes, Protein IDs).
2. **Quality Filtering**: Application of False Discovery Rate (FDR) constraints.
3. **Identifier Validation**: Removal of entries lacking genomic mapping.
4. **De-duplication**: Sorting and filtering of modified sequences.
5. **Type Casting**: Ensuring numerical consistency for mass and intensity metrics.
6. **Outlier Detection**: Filtering retention times and correcting invalid quantity values.

## Future Directions
- Implementation of Parallel Reaction Monitoring (PRM) for targeted validation of the top 50 regulated sites.
- Integration of kinase activity assays to assess the functional relevance of identified phosphosites (e.g., ZAP70).
