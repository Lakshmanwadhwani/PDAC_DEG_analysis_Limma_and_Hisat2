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

To run this project, you will need to have a Galaxy account and access to the Galaxy GUI platform. Once you have logged into Galaxy, you can follow these instructions:

Import the project files into Galaxy.
Run the fastqc tool on the FASTQ files.
Run the trimmomatic tool on the FASTQ files.
Run the hisat2 tool on the trimmed FASTQ files.
Run the limma tool on the alignment files.
Run the annotateMyIDs tool on the results of the limma analysis.

### Data

All data was obtained from NCBI sequence read archive at https://www.ncbi.nlm.nih.gov/sra.
The RNA-seq data set was generated to study the effects of the drug QN-302 on the expression of the S100P gene in pancreatic cancer cells. The data set includes two groups of samples: two poorly differentiated pancreatic cancer cell lines (PDAC) and two normal pancreatic tissue samples. The goal of the differential expression analysis is to identify genes that are differentially expressed between the two groups of samples.
The data was aligned to the human genome using the Hisat2 aligner and then analyzed using the Limma package. The results of the analysis will be used to identify genes that are up- or down-regulated in response to QN-302 treatment. These genes may be involved in the molecular pathways that are affected by the drug, and they could be potential therapeutic targets for pancreatic cancer.

Here are some additional details about the data:

The data set includes a total of 4 samples: 2 PDAC samples and 2 normal pancreatic tissue samples.
The data was generated using the Illumina HiSeq 2500 platform.
The sequencing depth is approximately 10 million reads per sample.
The data was aligned to the human genome (hg19) using the Hisat2 aligner.
The differential expression analysis was performed using the Limma package.
| Tissue Type | SRA Accession No. |
|-------------|-------------------|
| PDAC        | SRR23641868       |
| PDAC        | SRR23641867       |
| Normal      | SRR23641863       |
| Normal      | SRR23641862       |


## 📥 Importing Data from the SRA

You can download data directly from the Sequence Read Archive (SRA). Here are the steps:

1. Go to the [SRA website](https://www.ncbi.nlm.nih.gov/sra).
2. In the search bar, enter the SRA accession number or other relevant keywords for the data you want to download.
3. Click on the desired dataset from the search results.
4. Click on the "Send to" button, select "File", and then click "Create File". This will download a file that contains the information required to download the actual data.
5. Use the `fastq-dump` command from the SRA Toolkit to download the data. The command looks like this: `fastq-dump SRRxxxxxx`.

Please replace `SRRxxxxxx` with the specific SRA accession number.

## 📊 Results

This section will be updated with results from the analysis.

## 📜 License

This project is licensed under the terms of the MIT license.

## 👏 Acknowledgments

I would like to thank everyone who has contributed to this project.

