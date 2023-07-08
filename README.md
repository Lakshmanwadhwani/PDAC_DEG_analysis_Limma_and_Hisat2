![Galaxy](https://img.shields.io/badge/Galaxy-blue)![Trimmomatic](https://img.shields.io/badge/Trimmomatic-e7ee23)![FastQC](https://img.shields.io/badge/FastQC-9d37e6)![HISAT2](https://img.shields.io/badge/HISAT2-bada55)![featurecounts](https://img.shields.io/badge/featurecounts-66cccc)![annotateMyIDs](https://img.shields.io/badge/annotateMyIDs-999999)![Limma](https://img.shields.io/badge/Limma-e8b025)


# PancreaticCancer-RNAseq-Limma-Hisat2 🧬

## Description

This repository contains scripts and data files used for a differential expression analysis of RNA-seq data focusing on pancreatic cancer. The primary objective is to identify differentially expressed genes between poorly differentiated Pancreatic Ductal Adenocarcinoma (PDAC) and normal pancreatic samples. The authors primary focus was to understand the expression of the S100P gene in the context of disease and wild-type and the effects of the naphthalene diimide compound QN-302, which targets G-quadruplex DNA sequences in the promoter regions of cancer-related genes. The analysis incorporates the Limma package for differential expression analysis and Hisat2 for RNA sequence alignment.

## Workflow 🧰
![Workflow Diagram](./image.png)



















The work flow was largley conducted using the galaxy web interface (version 23.0.3), with the exception of the data importation and QC steps conducted using Anaconda powershell's command line.

1. Data importation from SRA using Anaconda's PowerShell.
2. Quality control checks on raw data using FastQC in Anaconda's PowerShell.
3. Trimmomatic functions on data
4. QC on trimmomatic data
5. RNA sequence alignment using Hisat2 in Galaxy (version 23.0.3).
6. FeatureCounts
7. AnnotateMyID
8. Differential expression analysis using Limma in Galaxy (version 23.0.3).

## Getting Started

### Prerequisites

- Limma
- annotateMyIDs
- featurecounts
- Hisat2
- FastQC
- Anaconda
- Galaxy (version 23.0.3)

### Installation

Software
The following software was used in this project:

-Anaconda is a free and open-source distribution of the Python programming language for scientific computing. It includes a collection of pre-compiled software packages for data analysis, machine learning, and other scientific computing tasks.
-VS Code is a code editor developed by Microsoft. It is a lightweight and extensible editor that can be used for a variety of programming languages.
-PowerShell is a command-line shell and scripting language developed by Microsoft. It is used to automate tasks on Windows computers.
-FastQC is a tool for quality control of high-throughput sequencing data. It can be used to assess the quality of FASTQ files, identify potential problems with the data, and generate reports.
-Trimmomatic is a tool for trimming adapters and low-quality sequences from FASTQ files. It is used to improve the quality of the data before it is analyzed further.
-Hisat2 is a tool for aligning RNA-seq reads to a reference genome. It is a fast and accurate aligner that can be used to map reads from a variety of sequencing platforms.
-Limma is a statistical package for analyzing differential gene expression data. It can be used to identify genes that are differentially expressed between two or more conditions.
-AnnotateMyIDs is a tool for annotating gene IDs with gene symbols, descriptions, and other information. It can be used to make the results of the limma analysis more interpretable.
#Instructions
To run this project, you will need to have a Galaxy account and access to the Galaxy GUI platform. Once you have logged into Galaxy, you can follow these instructions:

Import the project files into Galaxy.
Run the fastqc tool on the FASTQ files.
Run the trimmomatic tool on the FASTQ files.
Run the hisat2 tool on the trimmed FASTQ files.
Run the limma tool on the alignment files.
Run the annotateMyIDs tool on the results of the limma analysis.

### Data

All data was obtained

### Usage

#### Importing Data from SRA
```powershell
# Step 1: Open Anaconda's PowerShell

# Step 2: Install the SRA Toolkit
conda install -c bioconda sra-tools

# Step 3: Download the data using the SRA Toolkit. Replace `SRA_ACCESSION` with the actual SRA accession number.
fastq-dump --split-3 SRA_ACCESSION

# Step 4: Optionally specify a different directory to download the data using the -O option.
# Replace '/path/to/your/directory' with the actual directory path.
fastq-dump --split-3 -O /path/to/your/directory SRA_ACCESSION

# Step 5: Optionally download multiple datasets by listing multiple SRA accession numbers.
# Replace 'SRA_ACCESSION1', 'SRA_ACCESSION2', etc with the actual SRA accession numbers.
fastq-dump --split-3 -O /path/to/your/directory SRA_ACCESSION1 SRA_ACCESSION2 SRA_ACCESSION3

# Step 6: Once the data is downloaded, you can proceed to the quality control checks and subsequent analysis steps.


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
