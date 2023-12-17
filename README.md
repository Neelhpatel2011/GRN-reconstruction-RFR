Gene Regulatory Network Reconstruction

Overview:
Here, I worked with synthetic data sets provided by SERGIO to infer GRNs from expression data. I developed a program/method/tool for this purpose and evaluated my tool on the provided data.


The input to the method is an “expression matrix” that provides expression levels of genes in different experimental conditions. A subset of the genes will be marked as “TFs” (these are the candidate regulators for all genes) while the rest of the genes will be the “target genes”. 
My method should discover which of the TFs regulate each target gene, based solely on this matrix.

The provided information will include the true regulators of each target gene (this constitutes the “ground truth” GRN), which of course will not be made available to the GRN inference method. I evaluated your GRN inference method by comparing its predictions to this provided ground truth, using objective measures, such as F1 score, confusion matrices, AUPRC, and AUROC.

The overarching goal of this project is to develop and understand the strengths and weaknesses of a GRN reconstruction methods and its variants.

Dataset overview:
In my recent project, I worked with three distinct datasets available on the Canvas page under "Project1.zip". These datasets are named "5_mr_50_cond", "40_mr_50_cond", and "100_mr_50_cond". Each one includes a ground truth Gene Regulatory Network (GRN) and an expression matrix created using the SERGIO tool, based on the GRN.

In these GRNs, there are two types of genes: transcription factors (TFs) and target genes (G). In all datasets, the number of TFs and target genes is the same, with 100 of each (n_TF = 100 and n_G = 100). The regulation dynamics are intriguing: any gene can be regulated by several TFs, typically between 3 and 7 out of the 100 TFs. Also, each TF may regulate a different number of genes.

The complexity of inferring the GRN varies across datasets. "100_mr_50_cond" is the easiest, "40_mr_50_cond" has a medium difficulty, and "5_mr_50_cond" is the most challenging.

Each dataset is organized into three main files:

bipartite_GRN.csv: This file represents the ground truth GRN. Each line indicates a connection in the GRN, with the first number being the TF's identifier (ranging from 0 to 99) and the second number being the target gene's identifier (ranging from 100 to 199).

simulated_noNoise.txt: This is the expression matrix. It consists of 51 rows for the "5_mr_50_cond" and "40_mr_50_cond" datasets, and 101 rows for the "100_mr_50_cond" dataset, representing different experimental conditions. The first row is a header with identifiers for the 100 TFs and 100 target genes. The columns (200 in total) correspond to the expression levels of these genes under various conditions.

roc.txt: Although not essential for my analysis, this file offers a baseline for comparison. It contains the Area Under the Receiver Operating Characteristic (AUROC) values obtained by the GENIE3 method for each target gene in the dataset. These AUROC values provide a useful benchmark, as a random method would score 0.50 and a perfect method 1.0.

Through my work, I aimed to evaluate and reconstruct the GRN for each dataset separately, considering the varying levels of difficulty posed by each.
