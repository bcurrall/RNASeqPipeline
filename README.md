# RNASeqPipeline

## Workflow Overview

| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|
|1|Pre-processing||
|2|Alignment||
|3|Model||
|4|Differential Expression Genes (DEG) Analysis||
|5|Pathways Analysis||
|6|Other Analysis||
|7|Pipeline||

## 1. Pre-processing
| STEP  |  Process  | Reference  |
|:------|:----------|:----------:|
|1(optional)|fastqc->multiqc||
|2|merge fastq||
|3(optional)|trim adapters (trimomatic)||
|4|fastqc->multiqc||

1. (optional) fastqc-> multiqc
	* [FastQC][1] is a terrific, lightweight analysis package to get an idea of the quality of your fastq files. It can be run prior to merging to determine if there were problems in individual lanes or flows.
	```
	fastqc *
	```

	* [MultiQC][2]
	```
	multiqc .
	```
	
MultiQC

## Alignment
| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|
|2.1|uBAM align(STAR)||
|2.2(optional)|PicardStats->multiqc||
|2.3|Mark Duplicates||
|2.4|Split'N'Trim||
|2.5|Indel Realign||
|2.6|Base Recalibration||
|2.7|PicardStats->MultiQC||

## Model
| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|
|3.1|Pre-model QC||
|3.1.1| boxplots of known genes ||
|3.1.2| Heatmaps of Known Markers||
|3.1.2| PCA||
|3.2| Model ||
|3.2.1| SVA ||
|3.2.2| MVA ||
|3.3| QC of models post model||
|3.3.1| boxplots of known genes ||
|3.3.2| Heatmaps of Known Markers||
|3.3.3| PCA||

## Differential Analysis
| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|
|4.1| DEG (DESeq2)||
|4.2| DEG QC ||
|4.2.1| QQ |
|4.2.2| Volcano ||

## Pathway Prediction
| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|

## Additional Analysis
| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|
|6.1| WGCNA ||
|6.2| Exon Counting (DEXSeq) ||
|6.3| Variant Calling ||

[1]: http://www.bioinformatics.babraham.ac.uk/projects/fastqc/
[2]: https://multiqc.info/
