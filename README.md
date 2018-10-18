# RNASeqPipeline

## Workflow

| STEP  |  Process  | Reference  |
|------:|:----------|:----------:|
|1(optional)|fastqc->multiqc||
|2|merge fastq||
|3(optional)|trim adapters (trimomatic)||
|4|fastqc->multiqc||
|5|fastq -> uBAM||
|6|uBAM align(STAR)||
|7(optional)|PicardStats->multiqc||
|8|Mark Duplicates||
|9|Split'N'Trim||
|10|Indel Realign||
|11|Base Recalibration||
|12|PicardStats->MultiQC||
|13|count QC||
|13a| boxplots of known genes ||
|13b| Heatmaps of Known Markers||
|13c| PCA||
|14| Model ||
|14a| SVA ||
|14b| MVA ||
|15| QC of models post model||
|16a| boxplots of known genes ||
|16b| Heatmaps of Known Markers||
|16c| PCA||
|17| DEG (DESeq2)||
|17a| DEG QC ||
|17ai| QQ |
|17aii| Volcano ||
|17b| Pathway ||
|17c| WGCNA ||
|18| Exon Counting (DEXSeq) ||
|19| Variant Calling ||

