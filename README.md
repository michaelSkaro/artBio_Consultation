# artBio_consultation

Surface target evaluation in TCGA

The objective of this study is to profile The Cancer Genomes Atlas for expression
data in tumor and normal samples. The expression data will be analyzed with the 
intent to illuminate gene expression differences in genes encoding surface proteins.

Steps in the analysis:

- The TCGAbiolinks package will be used to access and analyze the expression data. 

- The differentially expressed genes for each of the indication will be listed.

- Upregualted genes in each indication will be intersected with the list of genes
encoding surface proteins.

- The 25th, 50th, 75th and 100th percentile of each of the GESP gene's expression 
will be listed for each indication in the TCGA database 
(TPM/FPKM availability dependent).

Visualizations:

- Heatmap of FC/Normal in indications where matched normal is available.
- Venn Diagram of intersection from GESP list and DEG list for each indication.
- Box plot for each differentially expressed gene in the intersected list. 
- PCA plot for tumor and normal tissues based solely on the DE GESPs

Filtering for Top30

A list of the top30 genes in each indication will be conducted. The genes
will be ranked on their fold change over normal and a pvalue below 0.01. 
Then the genes will be filtered on criteria described by ARTbio team. 

Filtering criteria:

- Exclude targets with tumor enrichment but ‘significant’ expression in colon, 
small intestine or haem compartments. The ARTbio team has not defined significant
but there is literature precedent to suggest high expression of surface targets
that have been successfully targeted with an ADC it 35TPM. We can use that as a 
minimum. 

- The average expression of constitutively expressed genes such as GAPDH
will be used as the upper limit. The median of expression in the colon between the
two will be used as a level for flagging. 

Non-visual outputs:

- Correlation between expression in TCGA and in the HPA database may/may not be
possible depending on the availability of data. Case by case basis will be used
and will be flagged as NA if this portion of the analysis cannot be executed 
due to missingness of the data. 



