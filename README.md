![Galaxy](https://img.shields.io/badge/Galaxy-blue)![Trimmomatic](https://img.shields.io/badge/Trimmomatic-e7ee23)![FastQC](https://img.shields.io/badge/FastQC-9d37e6)![HISAT2](https://img.shields.io/badge/HISAT2-bada55)![featurecounts](https://img.shields.io/badge/featurecounts-66cccc)![annotateMyIDs](https://img.shields.io/badge/annotateMyIDs-999999)![Limma](https://img.shields.io/badge/Limma-e8b025)



# Differential gene expression analysis using Limma-Hisat2 🧬
🔴 [PAPER](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10051992/pdf/molecules-28-02452.pdf) 🔴

## Background

QN-302, a unique compound that interacts with G-quadruplex DNA sequences in cancer-related genes, exhibits remarkable anti-proliferative activity in pancreatic cancer cell lines and significant anti-tumor effects in experimental models. Intriguingly, the S100P gene, a specific target of QN-302, harbors 60 potential quadruplex-forming sequences. One of these sequences, located within the promoter region, forms a highly stable G-quadruplex in vitro, which is further stabilized by QN-302. This interaction leads to the downregulation of S100P gene expression, potentially inhibiting the proliferation and invasiveness of pancreatic cancer cells.

QN-302 is currently in pre-IND development and is emerging as a promising therapeutic candidate for pancreatic cancer, with its mode of action potentially targeting the S100P promoter G-quadruplex at the transcriptional level. Although this hypothesis is supported by compelling evidence, it invites further exploration and validation.

To that end, I have set up this GitHub repository, which contains scripts and data files used for a differential expression analysis of RNA-seq data with a specific focus on pancreatic cancer. The primary objective of this project is to replicate the original authors' experiment to identify differentially expressed genes between poorly differentiated Pancreatic Ductal Adenocarcinoma (PDAC) and normal pancreatic samples. A critical part of this analysis is to explore the expression of the S100P gene in both disease and wild-type states and to observe the impact of QN-302, a naphthalene diimide compound known to target G-quadruplex DNA sequences in cancer-associated genes.

This replication experiment serves a dual purpose: Firstly, it provides me a valuable opportunity to gain hands-on experience with the RNA-seq pipeline development process. Secondly, it facilitates the exploration and mapping of differentially expressed genes across varying conditions. The tools used in this analysis, such as the Limma package for differential expression and Hisat2 for RNA sequence alignment, further augment this learning experience. 

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
### Summary of Results

From the authors of study:In normal pancreatic tissue, the expression of the S100P gene was not significantly affected by treatment with QN-302. The P value for the difference in expression between the treated and untreated groups was 0.46, and the LogFC was -0.08. This suggests that QN-302 does not have a significant effect on the expression of the S100P gene in normal pancreatic tissue.

In poorly differentiated pancreatic tissue, the expression of the S100P gene was significantly decreased by treatment with QN-302. The P value for the difference in expression between the treated and untreated groups was 0.0002, and the LogFC was -2.27. This suggests that QN-302 is a potent inhibitor of S100P expression in poorly differentiated pancreatic tissue.

The results of this study suggest that QN-302 may be a promising new therapeutic agent for the treatment of pancreatic cancer. However, further studies are needed to confirm the efficacy and safety of QN-302 treatment in humans.Below simple summary table. For a detailed results and discussion please refer to the link

### Summary Table

| Tissue Type | P Value | LogFC |
| ----------- | ------- | ----- |
| Normal      | 0.46    | -0.08 |
| PDAC        | 0.0002  | -2.27 |

My results:

Looking at my data (TSV file in this repository), it lists several genes along with their respective Log fold changes (LogFC) and adjusted p-values (adj.p.val). The LogFC is a measure of the ratio of changes in gene expression between the two conditions I'm comparing. When I see a positive LogFC, it indicates that a gene is upregulated, while a negative LogFC indicates downregulation.

The adjusted p-values listed here are the corrected p-values that account for the false discovery rate due to making multiple comparisons, which is common in high-throughput experiments like the one I'm doing with RNA-seq.

In my data, all of the genes listed have an adjusted p-value ranging from 0.52 1.00. In the biological studies I'm familiar with, an adjusted p-value below 0.05 is typically considered statistically significant. So, based on these data, none of the genes listed would be considered significantly differentially expressed at the traditional significance level.

That doesn't mean the changes aren't interesting. For instance, the gene REG3G shows a LogFC of 6.70, suggesting it's highly upregulated in one condition compared to the other. The gene TFF2, with a LogFC of -6.25, appears to be highly downregulated. But the high p-values mean that, according to typical thresholds, these changes aren't statistically significant.

In summary, given the high p-values, none of the changes in gene expression listed in my table would be considered statistically significant. This suggests to me that I might need to do more investigation or perhaps increase my sample size to confirm these changes.

This section will be updated with  discussion of results from further analysis.

## 📜 License

This project is licensed under the terms of the MIT license.

## 👏 Acknowledgments

Analysis for this project was performed using the Galaxy platform. The following paper provides more details about the platform and its capabilities:

Afgan, E., Baker, D., Batut, B., van den Beek, M., Bouvier, D., Čech, M., Chilton, J., Clements, D., Coraor, N., Grüning, B.A. and Guerler, A., 2018. The Galaxy platform for accessible, reproducible and collaborative biomedical analyses: 2018 update. Nucleic acids research, 46(W1), pp.W537-W544.

Galaxy platform can be accessed here: https://usegalaxy.org

We thank the Galaxy community for maintaining this useful resource for the scientific community.

