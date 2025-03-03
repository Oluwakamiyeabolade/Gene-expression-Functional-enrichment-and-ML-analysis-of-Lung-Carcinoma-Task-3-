# Gene-expression-Functional-enrichment-and-ML-analysis-on-Lung-adenocarcinoma-Data
Gene Expression Analysis, Functional Enrichment, and Machine Learning on Lung Adenocarcinoma Data

Contributors:

@Oluwakamiye, @Sapi, @Mojoyin, @Berkay, @Jumblosu, @Josiah, @Ifeoluwa01, @Oluwatosin.

Code link:

https://github.com/Oluwakamiyeabolade/Gene-expression-Functional-enrichment-and-ML-analysis-of-Lung-Carcinoma.git

Introduction

Adenocarcinoma is a malignant neoplasm arising from epithelial cells of the glands or glandular-like structures. Adenocarcinoma can arise in multiple sites of the body. Some of the common sites that develop adenocarcinoma are the breast, lung, prostate, and gastrointestinal tract, etc. (Mullangi et al., 2023).

**Methods **

Dataset Overview

We worked with the TCGA Lung Adenocarcinoma dataset from the Cancer Genome Atlas (TCGA) project, which included gene expression data and corresponding metadata with clinical attributes.

Data preparation and preprocessing

The data was normalized to account for variability in sequencing depth and gene expression values across samples and filtered to remove low-expressed genes. The data was downsized to include 20 samples each for tumor and normal tissue types for downstream analysis.

Differential gene expression analysis

Differential expression analysis between tumor and normal tissue types was done with the DESeq2 package in R. Genes with significant differential expression (adjusted p-value < 0.05) were identified. 

Enrichment analysis

Gene Ontology (GO) and KEGG pathway enrichment analyses were performed using the list of differentially expressed genes. ClusterProfiler and enrichGO were used for functional enrichment analysis. We also classified tumor vs. normal tissue types based on gene expression data by comparing two machine learning models: k-nearest neighbors (KNN) and Random Forest.

Data Preparation:

High-variance genes were selected to reduce the feature space and improve model performance. The dataset was split into training and testing sets. The KNN model and Random Forest classifier were trained on the selected features with cross-validation; an accuracy of 75% and 100%, respectively, was achieved on the data testing. The models correctly classified most samples as either tumors or normal.

**Results**

Figure 1 shows significant upregulation and downregulation in tumor tissue compared to normal tissue.
![image](https://github.com/user-attachments/assets/6d9537f2-469e-4285-9a96-d5727a71c21a)
Figure 1: Heatmap of Differentially Expressed Genes

Figure 2 shows genes expressed in tumor tissue compared to normal tissue  

![image](https://github.com/user-attachments/assets/0501b96e-c018-466e-84e6-ff01175b2a87)
Figure 2: Volcano plots of differentially expressed genes

Figure 3&4 are the results of the functional enrichment analysis, which revealed key important pathways that are implicated by the upregulated and downregulated genes, with the top four significant pathways highlighted.
Upregulated

![image](https://github.com/user-attachments/assets/18a3a30e-8c56-433c-a414-a3c6a488fa78)
Figure 3: Enrichment analysis of upregulated genes

downregulated

![image](https://github.com/user-attachments/assets/cdb90589-c480-45f1-858e-c05f1bd2eb4a)

Figure 4: Enrichment analysis of downregulated genes


Figure 5&6 shows the KEGG enrichment analysis results. The size of the dot correlatse to the degree of impact. The interaction and impact of some of the implicated pathways have been reported in several literatures (Zhang et al., 2023; Gao et al., 2024).

![image](https://github.com/user-attachments/assets/b1f2484c-d5dc-46c8-878a-5fee99ce509c)
Figure 5: KEGG enrichment analysis of upregulated genes

upkegg

Figure 6: KEGG enrichment analysis of downregulated genes

image

Figure 7: ROC Curve of knn ML model

image

Figure 8: Confusion matrix of knn ML model

image

Figure 9: ROC Curve of Random forest ML model

image

Figure 10: Confusion matrix of Random forest ML model

image

Figure 11: model accuracy comparisons of knn and Rf models

Conclusion

Differential gene expression identified crucial genes involved in lung adenocarcinoma progression, and functional enrichment analysis highlighted the key biological processes and pathways implicated in the disease. Machine learning models demonstrated high accuracy in classifying tumor vs. normal tissue, with Random Forest performing exceptionally well. These analyses provide insights into potential gene markers for lung adenocarcinoma and showcases the use of machine learning for accurate tissue classification based on gene expression profiles.

References

Carlson M. (2024). _org.Hs.eg.db: Genome-wide annotation for human_. R package version 3.19.1.
Chen Y, Chen L, Lun ATL, Baldoni P, Smyth GK (2024). “edgeR 4.0: powerful differential analysis of sequencing data with expanded functionality and improved support for small counts and larger datasets.” bioRxiv. doi:10.1101/2024.01.21.576131.
D. Risso, K. Schwartz, G. Sherlock, and S. Dudoit (2011). GC-Content Normalization for RNA-Seq Data. BMC Bioinformatics 12:480
Gao, Y., Zhang, H. & Tian, X. (2024). Integrated analysis of TCGA data identifies endoplasmic reticulum stress-related lncRNA signature in stomach adenocarcinoma. Oncologie, 26(2), 221-237. https://doi.org/10.1515/oncologie-2023-0394
Guangchuang Yu, Li-Gen Wang, Yanyan Han and Qing-Yu He. clusterProfiler: an R package for comparing biological themes among gene clusters.OMICS: A Journal of Integrative Biology 2012, 16(5):284-287
McCarthy DJ, Chen Y, Smyth GK (2012). “Differential expression analysis of multifactor RNA-Seq experiments with respect to biological variation.” Nucleic Acids Research, 40(10), 4288-4297. doi:10.1093/nar/gks042
Mounir, Mohamed, Lucchetta, Marta, Silva,   T, Olsen, Catharina, Bontempi, Gianluca, Chen, Xi, Noushmehr, Houtan, Colaprico, Antonio, and Papaleo, Elena (2019). “New functionalities in the TCGAbiolinks package for the study and integration of cancer data from GDC and GTEx.” PLoS computational biology, 15(3), e1006701.
Mullangi, S., & Lekkala, M. R. (2023). Adenocarcinoma. In StatPearls. StatPearls Publishing.
Ritchie ME, Phipson B, Wu D, Hu Y, Law CW, Shi W, Smyth GK (2015). “limma powers differential expression analyses for RNA-sequencing and microarray studies.” Nucleic Acids Research, 43(7), e47. doi:10.1093/nar/gkv007. 
Robinson MD, McCarthy DJ, Smyth GK (2010). “edgeR: a bioconductor package for differential expression analysis of digital gene expression data.” Bioinformatics, 26(1), 139-140. doi:10.1093/bioinformatics/btp616.
S Xu, E Hu, Y Cai, Z Xie, X Luo, L Zhan, W Tang, Q Wang, B Liu, R Wang, W Xie, T Wu, L Xie, G Yu. Using clusterProfiler to characterize multiomics data. Nature Protocols. 2024, doi:10.1038/s41596-024-01020-z
Silva, C. T., Colaprico, Antonio, Olsen, Catharina, D'Angelo, Fulvio, Bontempi, Gianluca, Ceccarelli, Michele, Noushmehr, Houtan (2016). “TCGA Workflow: Analyze cancer genomics and epigenomics data using Bioconductor packages.” F1000Research, 5.
Wickham H, François R, Henry L, Müller K, Vaughan D (2023). _dplyr: A Grammar of Data Manipulation_. R package version 1.1.4, <https://CRAN.R-project.org/package=dplyr>.
Zhang, L., Liu, Y., Zhuang, J. G., Guo, J., Li, Y. T., Dong, Y., & Song, G. (2023). Identification of key genes and biological pathways in lung adenocarcinoma by integrated bioinformatics analysis. World journal of clinical cases, 11(23), 5504–5518. https://doi.org/10.12998/wjcc.v11.i23.5504
T Wu, E Hu, S Xu, M Chen, P Guo, Z Dai, T Feng, L Zhou, W Tang, L Zhan, X Fu, S Liu, X Bo, and G Yu. clusterProfiler 4.0: A universal enrichment tool for interpreting omics data. The Innovation. 2021, 2(3):100141
** **

** **

** **

** **
