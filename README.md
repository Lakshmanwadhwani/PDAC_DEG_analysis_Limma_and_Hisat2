# PancreaticCancer-RNAseq-EdgeR-Hisat2

## Description

This repository contains scripts and data files used for a differential expression analysis of RNA-seq data focusing on pancreatic cancer. The primary objective is to identify differentially expressed genes between poorly differentiated Pancreatic Ductal Adenocarcinoma (PDAC) and normal pancreatic samples. The experiment pays particular attention to the expression of the S100P gene and the effects of the naphthalene diimide compound QN-302, which targets G-quadruplex DNA sequences in the promoter regions of cancer-related genes. The analysis incorporates the EdgeR package for differential expression analysis and Hisat2 for RNA sequence alignment.

## Workflow

1. Data importation from SRA using Anaconda's PowerShell.
2. Quality control checks on raw data using FastQC in Anaconda's PowerShell.
3. RNA sequence alignment using Hisat2 in Galaxy (version 23.0.3).
4. Differential expression analysis using EdgeR in Galaxy (version 23.0.3).

## Getting Started

### Prerequisites

- EdgeR
- Hisat2
- FastQC
- Anaconda
- Galaxy (version 23.0.3)

### Installation

Provide steps on how to install the required software.

#### Example:
1. Install Anaconda from [https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)
2. Install FastQC:
conda install -c bioconda fastqc


Copy code
3. Setup Galaxy server following instructions from [https://galaxyproject.org/admin/get-galaxy/](https://galaxyproject.org/admin/get-galaxy/)

### Data

Provide information about the dataset being used, such as the data source, and how it can be obtained.

### Usage

#### Importing Data from SRA
Provide steps on how to import data from SRA using Anaconda's PowerShell.

#### Example:
```powershell
# Command in PowerShell for importing data from SRA
Quality Control using FastQC
Provide steps on how to conduct quality control using FastQC.

Example:
powershell
Copy code
# Command in PowerShell for running FastQC
Galaxy Steps
Provide detailed steps on how to use Galaxy for RNA sequence alignment and differential expression analysis.

Results
Provide information on what results/output they should expect.

License
This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details

Acknowledgments
Mention any collaborators, funding bodies, etc.
