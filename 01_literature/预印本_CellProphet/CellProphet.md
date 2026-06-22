# 1 Dissecting dynamic gene regulatory network using transformer-based

2 temporal causality analysis

Rui Peng<sup>1,2</sup>, Juntian Qi<sup>3</sup>, Yuxing Lu<sup>1</sup>, Wei Wu<sup>1</sup>, Qichen Sun<sup>1</sup>, Chi Zhang<sup>1</sup>, Yihan Chen<sup>4</sup> , Jinzhuo Wang<sup>1,</sup> <sup>\*</sup>

1 Department of Big Data and Biomedical AI, College of Future Technology, Peking University, Beijing, 100871, China

2 Center for BioMed-X Research, Academy for Advanced Interdisciplinary Studies, Peking University, 100871, China

3 Laboratory of Bioinformatics and Genomic Medicine, Institute of Molecular Medicine, College of Future Technology, Peking University, Beijing, 100871, China 4 School of Life Sciences, Peking University, Beijing, 100871, China

\* Corresponding authors: J. Wang (wangjinzhuo@pku.edu.cn)

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

## Abstract

Gene regulatory networks (GRNs) dynamically regulate gene activation and repression, driving cellular differentiation. Despite advancements in GRN inference, challenges remain in capturing differentiation dynamics and causal inference. To address these limitations, we developed TRIGON, a Transformer-based model that infers dynamic GRN through learning temporal causality among genes. TRIGON achieved state-ofthe-art performance, improving accuracy by 204% over the latest methods across four developmental datasets. When applied to well-established paradigms, including mouse embryonic stem cell and hematopoietic stem cell differentiation, TRIGON identified key transcription factors (TFs) that were not detectable by differential expression analysis and revealed potential TFs associated with primitive endoderm differentiation. Furthermore, TRIGON constructed dynamic GRN across varying time resolutions, enabling the analysis of GRN dynamics from diverse time scales. Through in silico perturbation, TRIGON accurately recapitulated cell fate changes following Gata1 and Spi1 knockout and accurately predicted gene expression changes.

## Introduction

Gene regulatory networks (GRNs) consist of transcription factors (TFs) that bind to DNA regulatory elements, either promoting or inhibiting the expression of their target genes (TGs) during cellular differentiation<sup>1</sup> . These networks ensure that specific genes are activated or repressed at the right time and location, determining the cell fate. Over the decades, numerous methods have been proposed to infer cell lineage GRN from bulk transcriptomic data<sup>2-4</sup> . However, these bulk-based approaches require a sufficient number of transcriptomic samples to satisfy statistical assumptions, severely limiting their practicality. The advent of single-cell RNA sequencing (scRNA-seq)<sup>5</sup> enables high-throughput profiling of thousands of cells simultaneously, spurring the development of a variety of GRN inference methods. For instance, WGCNA<sup>6</sup> and GENIE3<sup>7</sup> inferred GRN by capturing the co-variation between TFs and TGs, CellOracle<sup>8</sup> leveraged bagging ridge regression to infer cell-type specific GRN using scRNA-seq and chromatin accessibility data, and CEFCON<sup>9</sup> utilized graph neural network alongside prior knowledge to model cell lineage GRN.

Despite significant advancements, several critical challenges in GRN inference remain unresolved. First, common approaches for constructing cell lineage GRN involve clustering cells and treat each cluster as a distinct cell type<sup>8,</sup> <sup>10,</sup> <sup>11</sup> , followed by inferring GRN independently for each cluster (Figure 1A). However, these clustering-based methods inherently discretize the continuous developmental cells into separate bins, which undermine the ability to capture the cellular differentiation dynamics. Moreover, GRNs inferred by these methods exhibit time resolution limited to the cluster level, meaning that the regulatory strength of TF-TG edges is only distinguished between clusters. They assume that cells within the same cluster share an identical GRN, but actually these cells exhibit developmental heterogeneity. Second, most existing methods focus on inferring static GRNs<sup>8,</sup> <sup>9,</sup> <sup>12,</sup> <sup>13</sup> , where the regulatory strength between TFs and TGs is assumed to remain constant over time. While Dictys<sup>14</sup> represents a notable effort to model dynamic GRN, it imposes numerous constraints on the moving window used for constructing dynamic network, which result in a fixed time resolution, limiting the ability to analyze GRN dynamics across varying time scales. Third, current cell lineage GRN inference methods often obtain suboptimal accuracy, with performance only slightly surpassing that of random predictions<sup>15</sup> .

To address the above challenges, we proposed TRIGON (Transformer-based method for inference of dynamic gene regulatory network), which focused on inferring cell lineage GRN. TRIGON extended the concept of granger causality to the context of gene regulation, enabling the inference of dynamic GRN and deciphering GRN dynamics across different time resolutions. We evaluated TRIGON against other latest methods across four developmental datasets and observed 204% improvement in inference accuracy. To demonstrate its applicability, we applied TRIGON to multiple wellcharacterized biological systems, including the differentiation processes of mouse embryonic stem cell (mESC) and hematopoietic stem cell (mHSC). TRIGON identified

76 well-known TFs at three critical stages of embryonic development, including TFs that   
77 could not be distinguished by differential expression analysis. During mHSC   
78 differentiation, TRIGON successfully recapitulated the effects of Gata1 and Spi1   
79 knockout on cell fate through in silico perturbation and was able to predict the gene   
80 expression changes following Gata1 knockout. Together, these results highlight that   
81 TRIGON establishes a novel paradigm for understanding gene regulation through   
82 temporal dynamic modeling.

## Results

## Overview of TRIGON:

Granger causality<sup>16</sup> is a statistical concept used to determine whether one time series can predict another. If variations in a time series X over a specific period are consistently followed by corresponding variations in a time series Y after a certain time lag, X is said to Granger-cause Y (Figure 1B, left). We posited that the temporal causality emphasized in granger causality aligns with the fundamental principles of GRNs. TFs regulate TGs by binding to their regulatory elements, thereby modulating transcription rates. Consequently, for a given TG, its expression after time point t is influenced by the expression of its TFs at preceding time points (Figure 1B, right). It is GRN that establishes the causal relationships between the gene expression of TFs and their TGs. Therefore, we formulated an inverse problem: can the temporal causality between the gene expression of TFs and their TGs be learned and then infer the underlying regulatory network? To address this, we developed a Transformer-based model, TRIGON, which incorporated two uniquely designed masks to learn the temporal causality in gene regulation and ultimately inferred the dynamic cell lineage GRN.

Here, we define two key terms: (1) watching window, representing the time window for observed gene expression. 2) forecasting window, representing the time window for gene expression that will be predicted. TRIGON took gene expression in watching window and a base GRN as input and output the predicted gene expression in forecasting window and a learned GRN coefficient matrix. The observed gene expression will first pass through the Temporal aggregation module, which aggregated the historical expression information for each gene (Figure 1C, Methods). At each time point, genes will attend its historical expression from all preceding time points and refine its value as a weighted sum of them. The aggregated gene expression data, together with the base GRN, were then processed by the Regulatory filtering module, which assigned a list of potential TFs to each TG, ensuring each TG’s expression was predicted solely based on the expression of its potential TFs.

TRIGON is constructed by Transformer encoders, leveraging the self-attention mechanism<sup>17</sup> to capture temporal causality among genes (Figure 1D, Methods). In the Temporal aggregation module, an upper triangular mask is introduced to ensure that the expression of a gene at a given time point can only attend to expression information from preceding time points. In the Regulatory filtering module, the base GRN is utilized as a binary mask, allowing each TG to attend only to TFs connected via edges present in the base GRN. Finally, TRIGON predict expression of TG in forecasting window, which is evaluated against observed ground truth using the Mean Squared Error (MSE) loss. After training, we utilize the inference module to obtain GRN (Extended Figure 1A, Methods). Specifically, the GRN coefficient matrix is extracted from the Regulatory filtering module, where each value represents the regulatory strength between TF and its TG. This matrix is subjected to post-processing to compute the regulatory score for each TF-TG edge, with the top k edges that will be selected to construct the inferred GRN (Methods)

## TRIGON shows state-of-art performance in extensive benchmarks

We first evaluated the accuracy of cell lineage GRNs inferred by TRIGON on mESC and mHSC datasets, both are provided by BEELINE<sup>15</sup> , a benchmarking study for GRN inference. The mHSC dataset has three sub-lineage datasets: mHSC-E (Erythroid lineage), mHSC-GM (Granulocyte-Monocyte lineage) and mHSC-L (Lymphoid lineage). For each lineage, we used available ChIP-seq data provided by BEELINE as the ground truth GRN to benchmark the reconstructed GRN. Testing data for each lineage was sampled based on watching windows. Each window generated a GRN through the inference module, and GRNs from different windows were averaged to construct the final cell lineage GRN (Figure 2A, Methods).

The accuracy of the inferred GRN can be evaluated using metrics employed in binary classification problems (Figure 2B, Methods). We used the area under the receiver operating characteristic curve (AUROC), area under the precision-recall curve (AUPRC) as metrics and compared TRIGON against seven GRN inference methods: (1) GENIE3<sup>7</sup> and GRNBoost2<sup>18</sup> , which are widely used classical methods for GRN inference. (2) CEFCON<sup>9</sup> and NetREX<sup>19</sup> , which require prior network as input to infer GRN. (3) CellOracle<sup>8</sup> , a multimodal machine learning method leveraging chromatin accessibility data to provide prior knowledge for GRN inference. (4) Random, which randomly selects k edges in all potential gene edges (k equals to the number of edges in the ground truth GRN) and (5) Prior Random, which randomly selects k edges in base GRN.

The receiver operating characteristic (ROC) curves of all methods (Figure 2D) indicated that TRIGON achieved the highest AUROC on the mESC, mHSC-GM, and mHSC-E datasets, surpassing the second-best methods (GENIE3, NetREX, and CellOracle) by 27%, 33%, and 0.7%. We observed that previously proposed methods showed no significant performance improvement compared to Random. For instance, on the mESC dataset, NetREX (0.522), GRNBoost2 (0.537), and GENIE3 (0.545) performed only marginally better than Random (0.506), indicating that the accuracy of these methods in GRN inference is barely above random guessing. However, TRIGON achieved an AUROC of 0.693, demonstrating the model’s superior performance. When analyzing the precision-recall (PR) curve (Figure 2E), we observed that all baseline methods exhibited a significant decrease in performance, with most methods achieving AUPRC below 0.2. In contrast, TRIGON achieved an average AUPRC of 0.752 across four datasets, representing a 204% improvement over the latest method CellOracle (0.247). To investigate the underlying reason, we examined the label distribution within each dataset and found a pronounced class imbalance across all datasets, with positive labels accounting for only 1.8%, 1.3%, 1.4%, and 2.3%, respectively (Figure 2C,

Extended Table 1, Methods). In such imbalanced scenarios, previous studies have demonstrated that AUPRC is a more reliable metric compared to AUROC<sup>20</sup> . Therefore, TRIGON's dominating advantage in AUPRC compared to other models further demonstrated its superior performance in cell lineage GRN inference.

We performed t-test to compare the performance of different methods across four datasets (Figure 2F, Figure 2G). The results indicated that TRIGON significantly outperformed other methods in both AUROC and AUPRC. For AUROC, the p-values between TRIGON and other methods were all less than 0.05, while for AUPRC, the pvalues were less than 0.001 for most methods. To confirm that the performance improvement of TRIGON was not attributed to the base GRN, we introduced Prior Random, which randomly selected k edges from the base GRN to construct the inferred GRN. Our experiments show that the AUROC of the Prior Random does not exhibit a significant advantage over Random across all four datasets (Figure 2F), suggesting that the provided prior knowledge was analogous to random guessing. To further validated this, we analyzed the noise proportion in base GRN (Extended Table 2, Methods). The result revealed that less than 0.5% of the edges in base GRN represented true regulatory interactions, while over 99.5% of the information was noise. Nevertheless, TRIGON demonstrated a significant improvement in AUROC compared to Prior Random (p-value < 0.05). These findings indicated that the enhanced performance of TRIGON was not attributable to the quality of the base GRN but rather to the intrinsic strength of itself.

## Identification of key TFs in mESC differentiation

Identifying key TFs during cellular differentiation is pivotal for elucidating the regulatory mechanisms that govern cell fate. We applied TRIGON to the mESC dataset (Figure 3A), which comprised scRNA-seq data collected at five distinct time points (0, 12, 24, 48, and 72 hours) as mouse embryonic stem cells progress toward primitive endoderm (PrE). We utilized AUCell<sup>10</sup> (Extended Figure 1B, Methods) to calculate the activity score of each TF regulon in individual cells based on the inferred GRN. A TF regulon is defined as a gene set comprising the TF itself and its TGs (Figure 3B). The activity score reflects the proportion of genes within the TF regulon that are highly expressed in a given cell, with a higher score indicating that the TF regulon is more active in that cell. We performed Analysis of Variance (ANOVA) to compare the activity score of each TF’s regulon across different time points and selected those with significant differences (p-value < 0.01) as the identified key TFs (Methods). In the mESC dataset, 33 key TFs were identified and the dynamic changes in their activity scores were visualized (Figure 3C, Extended Figure 2).

TRIGON identified three categories of key TFs based on the temporal dynamics of their activity scores during differentiation. (1) Early-stage TFs: These TFs exhibit ed high activity scores at the onset of differentiation (00h) and gradually declined as differentiation advances. These TFs were highly expressed during the early stages of differentiation, suggesting their involvement in maintaining stem cell identity and promoting differentiation. This was further supported by GO term enrichment analysis, which linked them to “stem cell number maintenance” and “stem cell differentiation”. Among them, Nanog, Pou5f1, Esrrb, and Sox2 are well-established regulators of stem cell pluripotency<sup>21-23</sup> , Utf1 and Ezh2 have been previously reported to play critical roles in maintaining stem cell identity<sup>23-26</sup> . (2) Mid-stage TFs: This group was characterized by transient increases in activity scores during the intermediate stages of differentiation (12h and 24h), suggesting their roles in initiating and promoting the differentiation process. GO term enrichment of these genes highlighted terms related to “embryonic development”. Among them, Gata4 has been reported to direct the development of two distinct types of Sox17+ endoderm, including an epCam+Dpp4+ subtype of visceral endoderm<sup>27</sup> . (3) Late-stage TFs: These TFs exhibited high activity scores during the terminal stages of differentiation (48h and 72h), GO term analysis revealed that these genes are associated with biological processes related to cellular functions, suggesting their potential involvement in the function and maturation of PrE. However, current studies on the specific roles of these genes in the PrE remain limited. They were the potential TFs identified by TRIGON and warranted further validation.

To verify whether TRIGON has an advantage over differential expression analysis (DEA) in identifying TFs. We calculated the log fold change (logFC) in gene expression and identified the key TFs based on p-value (Figure 3D). DEA highlighted four TFs (Pou5f1, Nanog, Sox2, and Esrrb), whose expression decreased during differentiation. This trend was consistent with the TF activity scores calculated by TRIGON (Figure 3E). However, TRIGON identified a group of genes (Klf4, Myc, Nrf1, et al.) that could not be distinguished by DEA. They were labeled as “stable” in DEA and were not identified as key TFs, boxplots of Myc and Nrf1 expression across different time points further supported this as their expression show minimal changes that can’t detected by DEA (Figure 3F). In contrast, these genes were recognized as key TFs by TRIGON, with their activity scores being high during the early stages of differentiation (Figure 3C). This finding was consistent with previous reports that Myc and Nrf1 promote the maintenance of stem cell pluripotency<sup>28,</sup> <sup>29</sup> , showing the capacity of TRIGON to identify TFs with greater precision.

## Constructing dynamic GRN in mHSC differentiation

During cellular differentiation, the regulatory strength between TF-TG changes dynamically over time. TRIGON was able to infer dynamic GRN and observed them across different time resolutions. Unlike the method for constructing cell lineage GRN, after inferring a GRN for each watching window, we applied gaussian smoothing to the regulatory strength of each TF-TG edge across all GRNs to construct the dynamic GRN (Figure 4A). The length of the watching window is regarded as the time resolution of the dynamic GRN. Unlike cluster-based methods, where each cluster typically involves tens to hundreds of cells, the watching window in TRIGON involved a smaller number of cells, enabling higher resolution of GRN dynamics. Notably, if the length of watching window is set to 1, TRIGON could infer single-cell resolution dynamic GRN.

We applied TRIGON to the mESC dataset to infer dynamic GRN. The primary objective is selecting representative TF-TG edges. We visualized the sub-regulatory network of Nanog (Figure 4B), which included predicted TGs such as Sox7 and Pou5f1. We selected four genes (Eps8, Fkbp4, C2cd5, and Ptpn) as representative target genes because they are located on the same chromosome as Nanog. To validate whether these four TF-TG edges predicted by TRIGON are indeed present during mESC differentiation, we integrated supporting evidence from previously published study<sup>30</sup> , which provided high-throughput chromosome conformation capture (Hi-C) data<sup>31</sup> , histone modification data (H3K9me3, H3K27me3, H3K4me1, H3K4me3, H3K27ac), single-cell assay for transposase-accessible chromatin sequencing (scATAC-seq) data<sup>32</sup> , and chromatin immunoprecipitation sequencing (ChIP-seq) data.

We analyzed Hi-C data to generate the chromatin contact matrix (Methods) and visualized using heatmap (Figure 4C, left), where we focused on the regulatory regions within 30 Mb flanking the Nanog gene (chromosomal coordinates 90 Mb to 150 Mb). In this region, we analyzed Hi-C and scATAC data to identify chromatin loops, ATAC peaks, and the Nanog footprint (Methods). These results, together with histone modification data and Nanog ChIP-seq data collected from ChIP-Atlas<sup>33</sup> , were subsequently visualized in the Integrative Genomics Viewer (IGV)<sup>34</sup> (Figure 4C, right). We selected the Nanog footprint region that consistent with ChIP-seq results for further analysis and found it located in the peak of scATAC-seq data. Furthermore, this region exhibited high value of H3K4me1, H3K4me3, H3K27ac while low value of H3K9me3 and H3K27me3. Through Hi-C loops, we identified that this Nanog-binding region formed loops with the regions of four previously identified TGs (Ptpn6, Fkbp4, Eps8, and C2cd5), validating that the TF-TG edges between Nanog and these four TGs inferred by TRIGON are true.

We selected Ptpn6, the target gene closest to Nanog, as well as Esrrb, Nr0b1, and Utf1 with their corresponding TGs, to analyze the dynamic GRN through mESC differentiation (Figure 4D). Under time resolution of 4, we observed that the regulatory strengths of these four TF-TG edges progressively decreased during differentiation, a trend consistent with the expression changes of the corresponding TFs. We calculated the Pearson correlation coefficients (PCC) between TF expression and regulation strengths (Figure 4E). Results showed PCC exceeding 0.7, with Esrrb and Utf1 above 0.9, demonstrating the accuracy of the inferred dynamic GRN. Furthermore, TRIGON offered flexible time resolutions, enabling GRN dynamics to be analyzed from various time scales. We computed the dynamic GRNs under time resolution of 1, 2, 8, 16 (Extended Figure 3). The results indicated that at time resolution of 1, the PCC was the lowest. However, as the time resolution changed from 2 to 16, the PCC and Rsquared improved progressively (Figure 4F, Figure 4G). This trend may be attributed to the technical noise inherent in single-cell sequencing data, where GRNs inferred from individual cell was more prone to bias. As the number of cells increases, these biases are mitigated, resulting in more accurate dynamic network. In the mESC dataset, the most accurate dynamic GRN was obtained at time resolution of 16. Similar phenomenon was observed for Sox2 (Extended Figure 4), at time resolution of 16, TRIGON achieved PCC of approximately 0.8. We believed that as single-cell sequencing technologies continue to advance and technical limitations are addressed, TRIGON will be able to capture dynamic GRN of single-cell resolution with greater precision.

## In silico perturbation in mouse hematopoietic stem cells

The objective of constructing cell lineage GRN is to uncover the underlying mechanisms of cellular differentiation, ultimately enabling the manipulation of cell fate. Perturbation experiments serve as a critical approach for achieving this goal. We employed a method inspired by CellOracle<sup>8</sup> to evaluate whether the predicted GRN could recapitulate the fate changes following the knockout of key TFs. The GRN inferred by TRIGON was represented as a directed graph, with edges indicating regulatory strengths from TFs to TGs. Perturbing a specific TF propagated the effects to its TGs along these edges, where the extent of the effect on each TG is determined by the edge weight (Figure 5A). To simulate gene knockout, the expression of the TF was set to zero, resulting in a perturbed expression vector. This vector was subsequently multiplied by the GRN coefficient matrix inferred by TRIGON, propagating the perturbation effects to the TGs (Extended Figure 1C, Methods). By iteratively propagating these effects, we computed the final expression difference vector for each cell and derived the perturbation vector (Extended Figure 1D, Methods). The vector indicates the direction of fate change for each cell following the perturbation (Figure 5A, Methods).

We applied TRIGON to perform in silico perturbation on the mHSC dataset, which has several key cellular states: (1) hematopoietic stem cell (HSC), (2) multipotent progenitor (MPP), (3) lymphoid multipotent progenitor (LMPP), (4) common myeloid progenitor (CMP), (5) megakaryocyte-erythrocyte progenitor (MEP), and (6) granulocyte-monocyte progenitor (GMP) (Figure 5B). We focused on two wellcharacterized TFs, Gata1 and Spi1, to investigate cell fate changes following in silico knockout. Previous studies have demonstrated that Gata1 promotes erythroid lineage development in HSC and facilitates the differentiation of CMP into MEP<sup>35-37</sup> . In contrast, Spi1 enhances LMPP differentiation and promotes the differentiation of CMP into GMP while simultaneously inhibits their differentiation into MEP<sup>38</sup> (Figure 5C).

We conducted in silico perturbation of Gata1 in the erythroid lineage (Figure 5D). Each cell was colored based on its pseudotime, and the pseudotime gradient vector was computed (Methods). By visualizing Gata1 expression, we observed high expression in CMP and MEP, with low expression in other cells. Upon knocking out Gata1, we calculated perturbation vector for each cell and found that these vectors were oriented opposite to the actual differentiation trajectory. Notably, perturbation vectors were more densely clustered in regions containing CMP and MEP. To quantify the effect of Gata1 perturbation, we calculated the perturbation score for each cell (Methods). If pseudotime gradient vector and perturbation vector have same direction, the perturbation score is positive and cells are colored by green, indicating that TF knockout promoted the cell’s differentiation. Conversely, the perturbation score is negative and cells are colored by purple, indicating that TF knockout inhibited the cell’s differentiation (Figure 5F). Upon Gata1 knockout, all cells in the mHSC-E dataset were colored purple (Figure 5D), showing an overall inhibition of differentiation. The perturbation scores were particularly pronounced in regions containing MEP and CMP, demonstrating a greater impact on these populations, which is consistent with the high expression of Gata1 in these cell types. Next, we conducted in silico knockout of Spi1 across cells from all three lineages. We visualized pseudotime, Spi1 expression, and the pseudotime gradient vectors for all cells (Figure 5E). Spi1 was found to be highly expressed in LMPP and GMP, with low expression in MEP. Following Spi1 knockout, the perturbation vectors for LMPP and GMP were directed toward MEP, and these cells received negative perturbation scores, indicating that Spi1 knockout suppressed their differentiation and caused them to progress toward MEP. CMP exhibited perturbation vectors directed toward MEP but received positive perturbation scores, indicating that Spi1 knockout promoted their differentiation into MEP. These observations align with Figure 5C.

The knockout experiments for Gata1 and Spi1 collectively validated the accuracy of the cell lineage GRN inferred by TRIGON, demonstrating its ability to simulate changes in cell fate following gene perturbations. In addition, we collected gene expression data following Gata1 knockout and found TRIGON could successfully predict the gene expression changes after perturbation (Figure 5G).

## Discussion

Understanding the GRNs underlying cell lineage development is crucial for deciphering the molecular mechanisms that govern cell fate decisions. GRN provides a framework to map the intricate interactions among TFs and their target genes, enabling researchers to explore how specific regulatory elements drive cellular identity and behavior during lineage progression. Accurate reconstruction of cell lineage GRN is vital for advancing our knowledge in developmental biology, regenerative medicine, and disease modeling.

Previous methods for GRN inference have predominantly concentrated on static networks, which operate under the assumption that TF-TG regulatory strengths remain constant over time. However, these approaches fail to account for the dynamic changes in regulatory interactions that occur as cells transition through distinct states along their differentiation process. Such limitations hinder a comprehensive understanding of the temporal dynamics by which GRN orchestrates lineage commitment and differentiation processes.

We observed the granger causality in gene regulatory processes, motivating us to infer GRN by analyzing the temporal causality between TF and TG expression. To achieve this, we employed the self-attention mechanism from Transformer to model temporal correlation among genes, framing GRN inference as a multivariate time series prediction problem. TRIGON designed two unique masks, a temporal mask aggregated historical expression information for each gene, and a regulatory filter mask assigned potential TFs to each TG. By predicting TG expression in the forecasting window based on TF expression in the watching window, TRIGON learned the causal relationship between the two time series and output a GRN coefficient matrix, which was subsequently post-processed to construct the final GRN.

TRIGON demonstrated state-of-the-art performance across four developmental datasets, achieving significant improvements in AUROC and AUPRC. Notably, TRIGON achieved an average AUPRC of 0.752, representing a 204% improvement over the latest CellOracle method. We applied TRIGON to analyze the differentiation of mESC and identified three classes of key TFs active at distinct stages of differentiation. Beyond recognizing well-known TFs such as Nanog, Sox2, and Pou5f1, TRIGON also uncovered potential TFs associated with PrE differentiation and identified some TFs that DEA could not distinguish. Additionally, we constructed dynamic GRN for mESC differentiation, enabling the observation of GRN dynamics at various time resolutions. During mHSC differentiation, TRIGON successfully recapitulated cell fate changes following the knockouts of Gata1 and Spi1 and validated TRIGON’s ability to predict the gene expression changes after perturbation.

TRIGON offers a novel approach to dynamic GRN construction through time series prediction. The flexible time resolution provided by TRIGON opens new avenues for precise analysis of dynamic changes during cellular differentiation, providing a much broader scope for future biological discovery and investigation.

Although TRIGON demonstrates high accuracy in inferring GRN for specific cell lineage, it is limited to training and deriving GRN for individual lineage, lacking generalization capabilities. Moreover, gene regulation is influenced by various factors, such as intercellular communication and chromatin accessibility, which TRIGON has not yet incorporated. In future work, we aim to enhance TRIGON by integrating multimodal data and developing foundational model for GRN inference, leveraging the potential of large language models.

## Methods

## Raw data

mESC dataset<sup>39</sup> . This dataset comprises scRNA-seq data for 421 primitive endoderm differentiated from mouse embryonic stem cells, collected across five time points: 0, 12, 24, 48, and 72 hours. BEELINE utilized Slingshot<sup>40</sup> to calculate pseudotime for each cell, with cells measured at 0h as the starting cluster and the cells measured at 72h as the ending cluster.

mHSC dataset<sup>41</sup> . This dataset consists of scRNA-seq data from 1,656 hematopoietic stem cells undergoing differentiation. Notably, the dataset is divided into three lineagespecific datasets: mHSC-E (Erythroid lineage), mHSC-GM (Granulocyte-Monocyte lineage), and mHSC-L (Lymphoid lineage). BEELINE applied Slingshot to independently calculate pseudotime for cells within each of the three lineages.

## Time series data construction

BEELINE utilized Slingshot to compute pseudotime for each cell. However, due to the errors in pseudotime calculation, we corrected the pseudotime using metadata from the dataset. Specifically, in the mESC dataset, each cell’s barcode contained the sequencing time, such as “RamDA\_mESC\_00h\_C01”, indicating the cell was sequenced at hour 0. To account for sequencing time, we first sorted the cells by their sequencing time (0, 12, 24, 48, 72 hours). Within each sequencing time, cells were further ordered in descending order of their pseudotime. This adjustment prevents the occurrence of cells sequenced at 72 hours being positioned before cells sequenced at 48 hours due to pseudotime discrepancies. For the mHSC dataset, the cell barcodes include the cell type (e.g., “Prog\_008,” “LT\_HSC\_113,” “HSPC\_009”). Referring to the original publication for this dataset, we confirmed the differentiation trajectory from long-term hematopoietic stem cells (LT\_HSC) to hematopoietic stem and progenitor cells (HSPC), and finally to progenitor cells (Prog). We ensured that cells are first sorted by their cell type and then by pseudotime within each cell type to achieve a more precise order. BEELINE calculated the variance of gene expression, the top 2000 genes with the highest variance were selected for further analysis. To ensure the selected genes align with those present in the provided ground truth GRN and the base GRN, we computed the intersection of these three sets. The final number of genes was reported in Extended Table 1.

## Training of TRIGON

TRIGON inferred GRN by learning the temporal causality between TF and TG expression. Specifically, the time-series data we constructed is denoted as $\mathbf { E } \in \mathbb { R } ^ { \mathbf { T } \times \mathbf { G } }$ where <sub>T</sub> and <sub>G</sub> represents time points and genes, $\mathrm { E _ { i j } }$ indicates the expression of gene <sub>j</sub> at time point <sub>i</sub> . $\mathrm { ~ E ~ } = \ [ \mathbf { e } _ { 1 } , \ldots , \mathbf { e } _ { \mathrm { T } } ] ^ { \mathrm { ~ T ~ } }$ possesses the temporal information of genes during the differentiation process, where $\mathbf { e } _ { \mathrm { i } } \in \mathbb { R } ^ { \mathrm { G } }$ represents all genes’ expression at the i-th time point. Based on the watching windows and forecasting windows, we constructed the training dataset $\mathsf { D } = \{ ( \mathsf { X } _ { \mathrm { i } } , \mathsf { Y } _ { \mathrm { i } } ) | \mathsf { i } = 1 , 2 , . . . , \mathsf { N } \}$ , where $\mathrm { X _ { i } }$ is TRIGON’s input, $\mathrm { Y _ { i } }$ is the ground truth expression associated to each input and N is the number of training samples. Each input $\bar { \mathrm { X } } _ { \mathrm { i } } = [ \mathrm { e } _ { \mathrm { i } } , \dots , \mathrm { e } _ { \mathrm { i } + \mathrm { W } - 1 } ] \in \mathbb { R } ^ { \mathrm { W } \times \mathrm { G } }$ and $\begin{array} { r } { \mathrm { Y } _ { \mathrm { i } } = [ \mathbf { e } _ { \mathrm { i } + \mathrm { W } } , \dots , \mathbf { e } _ { \mathrm { i } + \mathrm { W } + \mathrm { M } - 1 } ] ^ { \mathrm { ~ T ~ } } \in \mathrm { ~ \mathbb { R } ^ { ~ M } \times G ~ } } \end{array}$ is the gene expression in watching window of length W and forecasting window of length M respectively. Therefore, the inference process can be formulated as a multivariate time series forecasting problem and our goal is to learn a mapping function <sub>??GRN</sub> :

$$
f _ { \mathrm { G R N } } ( \mathbf { e } _ { \mathrm { t - W + 1 } } , \dots , \mathbf { e } _ { \mathrm { t } } ) = ( \mathbf { e } _ { \mathrm { t + 1 } } , \dots , \mathbf { e } _ { \mathrm { t + M } } )
$$

We embeded the expression of each gene using fully connected layers, transforming the matrix $\mathsf { X } \in \mathbb { R } ^ { \hat { \mathsf { W } } \times \mathsf { G } }$ to $\boldsymbol { \mathsf { X } } \in \mathbb { R } ^ { \bar { \mathsf { W } } \times \mathsf { G } \times \mathsf { d } _ { \mathsf { m o d e } } | }$ , where $\mathtt { d } _ { \mathrm { m o d e l } }$ is the embedding dimension. The data will be transposed to ${ \sf X } _ { \sf i n p u t } \ \in \ \mathbb { R } ^ { \sf G \times w \times d _ { \sf m o d e } | }$ which will be input to Temporal aggregation module to aggregate the gene expression information within the watching window. We constructed a unique temporal mask $\mathbb { M } ^ { \mathrm { t } } \in \mathbb { R } ^ { \mathsf { W } \times \mathbb { W } }$ for calculation of attention:

$$
\begin{array} { r } { \mathsf { M } _ { \mathrm { i j } } ^ { \mathrm { t } } = \left\{ { - \mathrm { i n f } , \mathrm { i f } \mathrm { j } > \mathrm { i } } \right. } \\ { \mathsf { M } _ { \mathrm { i j } } ^ { \mathrm { t } } = \mathrm { i } } \end{array}
$$

$\mathsf { M } ^ { \mathrm { t } }$ constraints cell at a given time point can't attend to information at subsequent cells. This trick is in line with the principles of cell differentiation, as a cell at specific time can only know the gene information from its ancestors but not its descendants, because they haven't been born yet at this point. Thus, the calculation of temporal attention in Temporal aggregation module is modified as follows:

$$
\mathrm { { T e m p o r a l A t t e n t i o n ( Q , K , V ) = \ s o f t m a x ( \frac { Q K ^ { T } } { \sqrt { d _ { k } } } \odot M ^ { t } ) V } }
$$

where $\begin{array} { r } { d _ { k } = \frac { d _ { m o d e l } } { h } , } \end{array}$ <sub>ℎ</sub> is the number of heads in multi-head self-attention and <sub>⨀</sub> represents hadamard product. The output $\boldsymbol { \mathrm { X } } _ { \mathrm { o u t p u t } } \in \mathbb { R } ^ { G \times W \times \mathbf { d } _ { \mathrm { m o d e l } } }$ will be transposed to $\widehat { \Chi } _ { \mathrm { o u t p u t } } \in \mathbb { R } ^ { W \times \mathbf { G } \times \mathbf { d } }$ model , which will be input into Regulatory filtering module alongside the base GRN to learn the coefficient between genes. The base GRN is a collection of gene regulatory interactions from over 50 public data sources of mouse<sup>42</sup> , we filtered the genes involved in the base GRN to those present in the singlecell input, ensuring the base GRN only focuses on the relationships among the G genes. In addition, we refined the base GRN by merging its edges with those from the ground truth GRN, ensuring that the edges to be inferred are included within the base GRN. Since base GRN can be represented as a graph, we used its adjacency matrix $\textsf { P } \in$ $\mathbb { R } ^ { 6 \times 6 }$ as the mask:

$$
\begin{array} { r l } { { \sf M } _ { \mathrm { i j } } ^ { s } = \left\{ { \tau } _ { 1 } ^ { } \mathrm { i n f } , \frac { } { } \right. } & { { } \mathrm { i f } \mathrm { P } _ { \mathrm { i j } } = 0 } \\ { \quad } & { { } \quad \mathrm { i f } \mathrm { P } _ { \mathrm { i j } } = 1 } \end{array}
$$

$M ^ { s }$ ensures the attention is computed between genes that are known to have regulation in base GRN, rather than focusing on unrelated genes. Thus, the calculation of regulatory attention in Regulatory filtering module can be formulated as follows:

$$
\mathrm { R e g u l a t o r y A t t e n t i o n ( Q , K , V ) = s o f t m a x ( \frac { Q K ^ { T } } { \sqrt { d _ { k } } } \odot M ^ { s } ) V }
$$

Ultimately, the output will go through a linear layer to obtain the predicted gene expression $\widehat { \Upsilon } _ { \mathrm { i } } \in \mathbb { R } ^ { \mathbf { M } \times \mathbf { G } }$ . We use MSE loss as our loss function:

$$
\mathcal { L } = \mathrm { M S E } ( \mathrm { Y _ { i } } , \widehat { \mathrm { Y _ { i } } } )
$$

## Cell lineage GRN inference

During inference, the sampling strategy for the test data differs from that used in the training phase, as outlined below:

$$
\begin{array} { r l } & { \mathrm { ~ X ^ { \ t e s t } _ { i } ~ = ~ [ e _ { i * w } , \ldots , e _ { i * ( W + 1 ) - 1 } ] ~ \in ~ \mathbb { R } ^ { W \times G } _ { \Sigma } } } \\ & { Y _ { i } ^ { t e s t } = ~ [ { \bf e } _ { \mathrm { i } * ( W + 1 ) } , \ldots , { \bf e } _ { \mathrm { i } * ( W + 1 ) + \mathrm { M } - 1 } ] ~ \in ~ \mathbb { R } ^ { \mathrm { M } \times \mathrm { G } } } \end{array}
$$

The time-series data are divided into segments, each with a length of W corresponding to the watching window. These segments are processed through the trained TRIGON. In the Regulatory filtering module, we obtain the GRN coefficient matrix $\mathrm { ~ H ~ } \in \ \mathbb { R } ^ { \mathrm { G \times G } }$ , which represents the regulatory strength between genes. It is important to note that the regulatory strength in the masked regions is zero, as no regulatory edges exist between those gene pairs in the base GRN. The matrix <sub>H</sub> obtained from TRIGON requires additional post-processing to form the final GRN. For each TF-TG edges, we compute their regulatory score:

$$
\mathrm { r e g u l a t o r y s c o r e = h \times \ l o g F C \times \ d e g r e e \times \ C }
$$

where <sub>h</sub> is the coefficient value of the edge in <sub>H</sub>, <sub>logFC</sub> represents the fold change of the TF corresponding to the edge, <sub>degree</sub> refers to the number of genes targeted by the TF and <sub>C</sub> indicates the number of target genes with <sub>logFC</sub> <sub>></sub> <sub>1</sub>. We assume that a TF which has a greater number of targeted genes contributes more to the network. Additionally, if the target genes’ <sub>logFC</sub> <sub>></sub> <sub>1</sub> , indicating that these genes show significant changes during development and are likely contributors to the developmental process. Thus, multiplying by <sub>C</sub> acts as a reward term to the TF. Each watching window, after being processed by the trained TRIGON, results in an inferred GRN. Assuming the number of cells in the lineage is <sub>N</sub>，a total of $\frac { \textsf { N } } { \textsf { W } }$ GRNs will be inferred (for simplicity, we assume that N is divisible by W). To obtain the GRN for the entire lineage, we average the regulatory scores across all inferred GRNs and select the top k edges to construct the cell lineage GRN, where k corresponds to the number of edges in the ground truth GRN.

## Cell lineage GRN benchmarking

BEELINE provides ground truth GRN for each dataset obtained from ChIP-seq data. Assuming the total number of genes is <sub>G</sub>，the total number of edges is ${ \sf G } \times ( { \sf G } -$ <sub>1)</sub> <sub>/</sub> <sub>2</sub>. Among these edges, those present in the ground truth GRN are labeled as 1 (positive edges), while the remaining edges are labeled as 0 (negative edges). Thus, the evaluation of GRN can be treated as a binary classification problem, where the task is to determine whether the edges identified by the model exist in the ground truth GRN. We computed AUROC and AUPRC as metrics. The PR curve describes the relationship between recall and precision, while the ROC curve illustrates the relationship between false positive rate (FPR) and true positive rate (TPR). Their definitions are as follows:

$$
{ \mathrm { r e c a l l } } = { \frac { \mathrm { T P } } { \mathrm { T P } \ + \Sigma _ { \mathrm { T P } } ^ { \mathrm { F N } } } }
$$

$$
\mathrm { p r e c i s i o n } = \frac { \mathrm { 1 } \mathrm { Y } } { \mathrm { T P } + \mathrm { F P } }
$$

$$
\mathrm { F P R } \ = \ \frac { \mathrm { F P } } { \mathrm { F P } \ _ { \mathrm { T P } } ^ { + } \mathrm { T N } }
$$

$$
\mathrm { T P R } = { \frac { \mathrm { \Large ~ \cdot ~ } { \mathrm { \Large ~ I ~ r ~ } } } { \mathrm { T P } + \mathrm { \Large ~ F N } } }
$$

where TP (True Positive) refers to edges predicted as true by the model that are also present in the ground truth GRN. FP (False Positive) refers to edges predicted as true by the model but absent from the ground truth GRN. TN (True Negative) refers to edges predicted as false by the model that are also absent from the ground truth GRN, while FN (False Negative) refers to edges predicted as false by the model but actually present in the ground truth GRN.

## Influence of base GRN

TRIGON uses the base GRN as a mask in the Regulatory filtering module, allowing to learn the regulatory relationships only between edges present in the base GRN. This approach narrows the search space for gene pairs. To demonstrate that the reduction in search space is not the main factor contributing to the model’s performance improvement, we evaluated the impact of the base GRN on model accuracy. Specifically, we introduced a method called Prior Random during benchmarking to verify the accuracy of randomly selecting the top k edges from the base GRN. We found that the AUROC of this method was not significantly different from the Random method. This suggests that the base GRN contains substantial noise, with many false positive edges, leading to performance comparable to random guessing. To further support this, we calculated the number of edges in the base GRN and their overlap with the ground truth GRN. The statistics, provided in the Extended Table 1, show that approximately 99.5% of the edges in the base GRN are false positives. Additionally, the benchmarking methods we compared against, including CEFCON, NetREX, and CellOracle, also employed the base GRN to reduce the search space. Our performance demonstrates significant improvement over these methods across all datasets, suggesting that the base GRN is not the key factor driving the performance improvement of our model.

## AUCeLL algorithm

To identify key TFs during cellular differentiation based on the inferred GRN, we employed the AUCell algorithm to calculate the activity score for each TF. AUCell first ranks gene expression in each cell from high to low and sets a threshold (defaulting to the top 5%) to identify highly expressed genes in that cell. For each threshold (ranging from 0 to 5%), the algorithm calculates the proportion of genes within the TF regulon that are highly expressed in the given cell. By computing the area under the curve (AUC), the algorithm determines the activity score of each TF in the cell. A higher score indicates that the TF is more actively expressed in the given cell. Since the mESC dataset includes five sequencing time points (0h, 12h, 24h, 48h, and 72h), we performed

ANOVA on the TF activity scores across these time points. TFs with a p-value less than 0.01 were identified as key regulators in the differentiation process.

## Dynamic GRN inference

During the inference stage, testing data are sampled based on watching windows. Given a lineage containing <sub>N</sub> cells, a total of $\frac { \textsf { N } } { \textsf { W } }$ watching windows can be generated, where <sub>W</sub> denotes the length of the watching window. Each window, when processed through the trained TRIGON, yields a GRN. The parameter <sub>W</sub> represents the time resolution of the inferred dynamic GRN. Specifically, when <sub>W</sub> is set to 1, the GRN can be inferred for each individual cell, enabling a single-cell resolution dynamic GRN. The $\frac { \textsf { N } } { \textsf { W } }$ inferred GRNs are then temporally smoothed by gaussian smoothing, capturing the dynamic changes in gene regulation throughout the lineage differentiation process.

## mESC Hi-C and scATAC-seq data processing

To identify the TF-TG edges for constructing dynamic GRNs, we utilized previously published experimental datasets<sup>30</sup> to validate the accuracy of the edges inferred by TRIGON. The datasets included mouse Hi-C and scATAC-seq data, analyzed using the mm9 reference genome. For Hi-C data, raw FASTQ files were processed using HiC-Pro<sup>43</sup> to generate all valid pairs and the contact matrix. To convert the all valid pairs into “.hic” format, we used the “pre” function from JuicerTools, followed by chromatin loops identification at a 20 kb resolution using the “hiccups” function. For scATACseq data, reads were aligned to the mm9 reference genome using Bowtie2<sup>44</sup> , with mitochondrial reads and those overlapping blacklist regions removed. Following prior studies<sup>45,</sup> <sup>46</sup> , to account for Tn5 transposase binding as a dimer and inserting adapters separated by 9 bp, we adjusted the read positions: reads aligned to the (+) strand were shifted by +4 bp, while those aligned to the (-) strand were shifted by -5 bp. Peak calling was performed using MACS<sup>47</sup> , and TF footprints were identified using the “footprinting" function in Regulatory Genomics Toolbox (RGT)<sup>48</sup> . To analyze Nanog regulatory regions, we retrieved the Nanog motif from JASPAR<sup>49</sup> and scanned the identified footprint regions to locate Nanog footprint.

Finally, we integrated the chromatin loops derived from Hi-C data, histone modification data (H3K9me3, H3K27me3, H3K4me1, H3K4me3, and H3K27ac), peaks identified from scATAC-seq data, Nanog footprint, and Nanog ChIP-seq data obtained from ChIP-Atlas<sup>33</sup> . These data were visualized collectively using IGV, enabling the comprehensive evaluation of the regulatory landscape.

## In silico perturbation

We followed the in silico perturbation outlined in CellOracle to validate whether the GRN inferred by TRIGON can simulate cell fate changes after TF knockout. The expression of the perturbed TF is set to zero, creating an expression difference vector relative to its original expression value. This vector is then multiplied by the GRN coefficient matrix output by TRIGON. Note that this matrix is the average of the matrices obtained from $\frac { \textsf { N } } { \textsf { W } }$ watching windows, where <sub>N</sub> represents the number of cells in lineage, and <sub>W</sub> is the length of the watching window. The GRN coefficient matrix encodes the regulatory strength between each TF and its TG. We computed PCC between the expression of the TF and its TG, if PCC is less than zero, the corresponding coefficient value is multiplied by -1 to indicate that the TF exerts a repressive effect on its TG. After each propagation step, the change in the perturbed gene’s expression is reset to the original perturbation value, indicating that the effect of the perturbation persists through each iteration. After the propagation, each cell obtains the final expression difference vector, which will be used to calculate the transition probability:

$$
\mathrm { P _ { i j } = \frac { \ e x p { ( c o r r ( r _ { i j } , d _ { i } ) / T ) } } { \sum _ { j \in G } \ e x p { ( c o r r ( r _ { i j } , d _ { i } ) / T ) } } }
$$

${ \mathrm { d } } _ { \mathrm { i } }$ is the final expression difference vector for cell <sub>i</sub>, $\boldsymbol { \mathrm { r } } _ { \mathrm { i j } }$ is origin gene expression difference between cell <sub>i</sub> and cell <sub>j</sub>, <sub>corr</sub> represents the Pearson correlation between these two vectors and <sub>T</sub> is the temperature parameter. This formula calculates the transition probability from cell <sub>i</sub> to cell <sub>j</sub>. Subsequently, the transition probability of cell <sub>i</sub> are weighted and summed with the coordinate difference vector $\mathrm { V _ { i j } }$ between cell <sub>i</sub> and its neighboring cell <sub>j</sub> in the two-dimensional space determined by the diffusion map<sup>50,</sup> <sup>51</sup> . The final perturbation vector for cell <sub>i</sub> is computed as follows:

$$
\mathrm { V _ { i , p e r t u r b e d } = \sum _ { j \in G } p _ { i j } \ V _ { i j } }
$$

The perturbation vector indicates the direction in which the current cell will change when the gene is perturbed.

## Perturbation score

We calculated the gradient of the pseudotime using the “numpy.gradient” function, resulting in a two-dimensional vector representing the differentiation direction. Subsequently, we computed the inner product between the pseudotime gradient vector and the perturbation vector, which is used as the perturbation score (PS). If the differentiation direction of the current cell aligns with the perturbation direction, the PS will be positive, indicating that the knockout of the TF promotes the development of the current cell. Conversely, if the directions are opposite, the PS will be negative, suggesting that the knockout of the TF inhibits the current cell’s development.

## Gene expression prediction after perturbation

In addition to predicting cell fate changes after perturbation based on the perturbation vector, we collected gene expression data associated with Gata1 knockout. This dataset includes gene expression from three wild-type and three knockout mice. We averaged the expression of the three wild-type and three knockout mice respectively, and calculated the difference between them as the ground truth. We then utilized the final expression difference vector generated by the in silico perturbation as the predicted gene expression profile following Gata1 perturbation and evaluated whether the predicted direction of gene expression changes aligned with the ground truth.

## Acknowledgments

This research was supported by National Natural Science Foundation of China (6220071694), National Key Research and Development Program of China (2024YFF0507404), Discipline Development of Peking University (7101302940, 7101303005, 7101303742), Emerging Engineering Interdisciplinary Project, Peking University, the Fundamental Research Funds for the Central Universities, and Young Elite Scientist Sponsorship Program by Beijing Association for Science and Technology (BYESS2023026).

## Author Contributions

Conceptualization: P.R., J.W.. Data acquisition: P.R., J.W. Analysis: P.R., J.Q., W.W., Y.L., Y.C., J.W. Methodology: P.R., J.W. Supervision: J.W. Funding acquisition: J.W. Project administration: J.W. Writing: P.R., J.Q., W.W., Y.L., C.Z., Q.S., Y.C., J.W.

## Competing Interests statement

The authors declare no competing financial interests.

## Data availability

All the datasets analyzed in this study are publicly available. The scRNA-seq datasets are available in the Gene Expression Omnibus (GEO) under accession codes: GSE98664[https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98664] (mESC), and GSE81682[https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE81682] (mHSC). The prior gene interaction network was from NicheNet<sup>42</sup> , which can be downloaded from https://github.com/saeyslab/nichenetr. The ChIP-seq data for validating the constructed GRN were obtained from BEELINE<sup>15</sup> . Epigenomic datasets for mESC, including scATAC-seq, histone modification, and Hi-C data, are available in the GEO under accession codes: GSE159623[https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE159623]. The Gata1 knockout data for mHSC can be accessed in the GEO under accession codes: GSE279985[https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE279985]. Source data are provided with this paper.

## Code availability

The TRIGON algorithm is implemented in Python. The source code of TRIGON is available at https://github.com/prsigma/TRIGON.

## References

1. Badia-i-Mompel, P. et al. Gene regulatory network inference in the era of single-cell multi-omics. Nature Reviews Genetics 24, 739-754 (2023).

2. Basso, K. et al. Reverse engineering of regulatory networks in human B cells. Nat Genet 37, 382-390 (2005).

3. Scutari, M. Learning Bayesian networks with the bnlearn R Package. Journal of Statistical Software 35 (2010).

4. Margolin, A.A. et al. ARACNE: an algorithm for the reconstruction of gene regulatory networks in a mammalian cellular context. BMC Bioinformatics 7 Suppl 1, S7 (2006).

5. Tang, F. et al. mRNA-Seq whole-transcriptome analysis of a single cell. Nat Methods 6, 377-382 (2009).

6. Langfelder, P. & Horvath, S. WGCNA: an R package for weighted correlation network analysis. BMC bioinformatics 9, 1-13 (2008).

7. Huynh-Thu, V.A., Irrthum, A., Wehenkel, L. & Geurts, P. Inferring regulatory networks from expression data using tree-based methods. PLoS One 5 (2010).

8. Kamimoto, K. et al. Dissecting cell identity via network inference and in silico gene perturbation. Nature 614, 742-751 (2023).

9. Wang, P. et al. Deciphering driver regulators of cell fate decisions from singlecell transcriptomics data with CEFCON. Nat Commun 14, 8459 (2023).

10. Aibar, S. et al. SCENIC: single-cell regulatory network inference and clustering. Nature methods 14, 1083-1086 (2017).

11. Bravo González-Blas, C. et al. SCENIC+: single-cell multiomic inference of enhancers and gene regulatory networks. Nature methods 20, 1355-1367 (2023).

12. Yuan, Q. & Duren, Z. Inferring gene regulatory networks from single-cell multiome data using atlas-scale external data. Nat Biotechnol (2024).

13. Shu, H. et al. Modeling gene regulatory networks using neural network architectures. Nat Comput Sci 1, 491-501 (2021).

14. Wang, L. et al. Dictys: dynamic gene regulatory network dissects developmental continuum with single-cell multiomics. Nat Methods 20, 1368- 1378 (2023).

15. Pratapa, A., Jalihal, A.P., Law, J.N., Bharadwaj, A. & Murali, T.M. Benchmarking algorithms for gene regulatory network inference from singlecell transcriptomic data. Nat Methods 17, 147-154 (2020).

16. Shojaie, A. & Fox, E.B. Granger causality: A review and recent advances. Annual Review of Statistics and Its Application 9, 289-319 (2022).

17. Vaswani, A. Attention is all you need. Advances in Neural Information Processing Systems (2017).

18. Moerman, T. et al. GRNBoost2 and Arboreto: efficient and scalable inference of gene regulatory networks. Bioinformatics 35, 2159-2161 (2019).

19. Wang, Y. et al. Reprogramming of regulatory network using expression uncovers sex-specific gene regulation in Drosophila. Nat Commun 9, 4061 (2018).

20. Davis, J. & Goadrich, M. in Proceedings of the 23rd international conference on Machine learning 233-240 (2006).

21. Wang, Z., Oron, E., Nelson, B., Razis, S. & Ivanova, N. Distinct lineage specification roles for NANOG, OCT4, and SOX2 in human embryonic stem cells. Cell Stem Cell 10, 440-454 (2012).

22. Marucci, L. Nanog Dynamics in Mouse Embryonic Stem Cells: Results from Systems Biology Approaches. Stem Cells Int 2017, 7160419 (2017).

23. Kondoh, H. Different Types of Pluripotent Stem Cells Represent Different Developmental Stages. Results Probl Cell Differ 72, 11-25 (2024).

24. Raina, K., Dey, C., Thool, M., Sudhagar, S. & Thummer, R.P. An insight into the role of UTF1 in development, stem cells, and cancer. Stem Cell Reviews and Reports 17, 1280-1293 (2021).

25. Shan, Y. et al. PRC2 specifies ectoderm lineages and maintains pluripotency in primed but not naive ESCs. Nat Commun 8, 672 (2017).

26. Lavarone, E., Barbieri, C.M. & Pasini, D. Dissecting the role of H3K27 acetylation and methylation in PRC2 mediated control of cellular identity. Nat Commun 10, 1679 (2019).

27. Holtzinger, A., Rosenfeld, G.E. & Evans, T. Gata4 directs development of cardiac-inducing endoderm from ES cells. Dev Biol 337, 63-73 (2010).

28. Varlakhanova, N.V. et al. myc maintains embryonic stem cell pluripotency and self-renewal. Differentiation 80, 9-19 (2010).

29. Liu, S. et al. NRF1 association with AUTS2-Polycomb mediates specific gene activation in the brain. Mol Cell 81, 4663-4676 e4668 (2021).

30. Zhu, Y. et al. Relaxed 3D genome conformation facilitates the pluripotent to totipotent-like state transition in embryonic stem cells. Nucleic acids research 49, 12167-12177 (2021).

31. Lieberman-Aiden, E. et al. Comprehensive mapping of long-range interactions reveals folding principles of the human genome. Science 326, 289-293 (2009).

32. Buenrostro, J.D. et al. Single-cell chromatin accessibility reveals principles of regulatory variation. Nature 523, 486-490 (2015).

33. Zou, Z., Ohta, T. & Oki, S. ChIP-Atlas 3.0: a data-mining suite to explore chromosome architecture together with large-scale regulome data. Nucleic Acids Research, gkae358 (2024).

34. Robinson, J.T. et al. Integrative genomics viewer. Nature biotechnology 29, 24- 26 (2011).

35. Ohneda, K. & Yamamoto, M. Roles of hematopoietic transcription factors GATA-1 and GATA-2 in the development of red blood cell lineage. Acta haematologica 108, 237-245 (2002).

36. Fujiwara, Y., Browne, C.P., Cunniff, K., Goff, S.C. & Orkin, S.H. Arrested development of embryonic red cell precursors in mouse embryos lacking transcription factor GATA-1. Proceedings of the National Academy of Sciences 93, 12355-12358 (1996).

37. Gutiérrez, L., Caballero, N., Fernández‐Calleja, L., Karkoulia, E. & Strouboulis, J. Regulation of GATA1 levels in erythropoiesis. IUBMB life 72, 89-105 (2020).

38. Zhang, P. et al. PU.1 inhibits GATA-1 function and erythroid differentiation by blocking GATA-1 DNA binding. Blood 96, 2641-2648 (2000).

39. Hayashi, T. et al. Single-cell full-length total RNA sequencing uncovers dynamics of recursive splicing and enhancer RNAs. Nat Commun 9, 619 (2018).

40. Street, K. et al. Slingshot: cell lineage and pseudotime inference for single-cell transcriptomics. BMC Genomics 19, 477 (2018).

41. Nestorowa, S. et al. A single-cell resolution map of mouse hematopoietic stem and progenitor cell differentiation. Blood 128, e20-31 (2016).

42. Browaeys, R., Saelens, W. & Saeys, Y. NicheNet: modeling intercellular communication by linking ligands to target genes. Nature methods 17, 159-162 (2020).

43. Servant, N. et al. HiC-Pro: an optimized and flexible pipeline for Hi-C data processing. Genome biology 16, 1-11 (2015).

44. Langmead, B. & Salzberg, S.L. Fast gapped-read alignment with Bowtie 2. Nature methods 9, 357-359 (2012).

45. Reznikoff, W.S. Tn5 as a model for understanding DNA transposition. Molecular microbiology 47, 1199-1206 (2003).

46. Davies, D.R., Goryshin, I.Y., Reznikoff, W.S. & Rayment, I. Threedimensional structure of the Tn 5 synaptic complex transposition intermediate. Science 289, 77-85 (2000).

47. Zhang, Y. et al. Model-based analysis of ChIP-Seq (MACS). Genome biology 9, 1-9 (2008).

48. Li, Z. et al. RGT: a toolbox for the integrative analysis of high throughput regulatory genomics data. BMC bioinformatics 24, 79 (2023).

49. Rauluseviciute, I. et al. JASPAR 2024: 20th anniversary of the open-access database of transcription factor binding profiles. Nucleic Acids Research 52, D174-D182 (2024).

50. Coifman, R.R. et al. Geometric diffusions as a tool for harmonic analysis and structure definition of data: Multiscale methods. Proceedings of the National Academy of Sciences 102, 7432-7437 (2005).

51. Coifman, R.R. & Lafon, S. Diffusion maps. Applied and computational harmonic analysis 21, 5-30 (2006).

![](images/646d6d2cd57ae9441756ce2fea884245bef79bbf961aa60c2ed5af831f96c3f8.jpg)  
Figure 1. Overview of TRIGON. A, Cluster-based methods group cells along lineage and construct GRN for each individual cluster, which fail to capture the dynamics of GRN during cellular differentiation. B, The concept of granger causality is observed in gene regulation, where the expression of TG is determined by the expression of its TFs over a given time period. TRIGON leverages this concept to infer dynamic GRN. C, TRIGON takes the expression of TFs within the watching window and a base GRN as input. Through the Temporal aggregation module and the Regulatory filtering module, it predicts the expression of TGs in the forecasting window, learns the temporal causality between TFs and TGs and ultimately outputs a GRN coefficient matrix. D, TRIGON is built on Transformer encoders, where Temporal and Regulatory masks are specifically designed to compute self-attention. The attention map generated in the Regulatory filtering module is regarded as the GRN coefficient matrix.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

A  
![](images/3b4713cb159a969c447230cbcbae198bd590cd0ae868f00c7bef209a931001f4.jpg)  
B

![](images/0497f3f55ccf76f1cfcb64d05f3884c50b234c242cc776e89bbd2b4c8680a1cb.jpg)

![](images/7645abcecd4e84c163b9d28f41ec0fd4beaa74af7ba10db3d68a0e1a2ba06aca.jpg)

![](images/98e272711e4a4e4a2fff0d220ab6958af2fc9e0975e78afde5dd40c25432893f.jpg)

![](images/70003c2c97bfd515d99dba5bc0655c2b1f57938b9f39ad9513914f957bac892d.jpg)  
C

![](images/89c39fbc47fab5c0fe9dce227de3b817c80e167994d3b8f33fee29736a44d4b6.jpg)

D  
![](images/e5b4def15e87ae3f4a177dff18395da8ca7a6919ece207becc6e4bb5348df381.jpg)

![](images/7f9c6587c656305a838e1729583cbbade9285a599ab2052bbf5a148130a3aa5d.jpg)

E  
![](images/8443d08bc8c974b0c4eaeccd8c0c621dddb64eae8af0ff7a4147ad3180eeab1f.jpg)

![](images/5f872f68d55e46044e8d65b9c8905dd6e69d2ed8e0ec786d65499b70e5df4482.jpg)

![](images/caa08199251d124b402416b25fc9b51f1e06491ab0d939dae3fc428aebbcb3d9.jpg)

![](images/274ac95b247b58de6b2da164b9e1c8a08c50f58cb9a59213c99392c2257a046d.jpg)

![](images/a24034dbf2b9c0153b966959ba2d6f671498dcf9f03b06a60b24ec8bd08bc8a7.jpg)

![](images/717533a1ee199dc5d617c379e5116348e826bd8f8e6b940a413eb0c000c2ef23.jpg)

F  
G  
![](images/9f014388c1bb325fdbc9c605c91c3b24949fbffa59970c22c666a23f778e21c5.jpg)

![](images/89f356cae0032049847fd99c2021961de21b1092a4e951536ac9cc08c2a2c997.jpg)  
Figure 2. TRIGON shows superior performance over existing methods in extensive benchmarks. A, TRIGON analyzes each lineage by sampling testing data based on watching windows. GRNs inferred from all windows are averaged, and the top k edges are selected to construct the final cell lineage GRN. B, GRN evaluation is treated as a binary classification task, determining whether the edges identified by the algorithm are present in the ground truth GRN. $\mathbf { C } ,$ The ratio of positive and negative labels in the four datasets shows significant class

835 imbalance, with only approximately 2% of edges classified as positive (edges present in the   
836 ground truth GRN). D, ROC curves for the four datasets. Curves closer to the top left corner   
837 represent AUROC approaching 1, reflecting better performance. E, PR curves for the four   
838 datasets. Curves closer to the top right corner represent AUPRC approaching 1, reflecting better   
839 performance. F, One-sided paired t-test results for AUROC across the four datasets show that   
840 TRIGON significantly outperforms other methods, \*P<0.05. G, One-sided paired t-test results   
841 for AUPRC show that TRIGON achieves the best performance, with an average value of 0.752   
842 across the four datasets. \*P<0.05, \*\*P<0.01, \*\*\*P<0.001.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

![](images/37301ef2965a1a6d8de6807e2da5769703dc35c9d7f199f63cfb565620653fa4.jpg)  
B

![](images/3cd6ad03a8096966e1faca6ac0fc832b59487a6b7b0883ae431606f458ae78fa.jpg)

C  
![](images/e78df8b0d44d4730f84d484c19c450030c5fc723e74693420c8c5340596e4c20.jpg)  
Go term enrichment formation of primary germ layer endodermal cellfate commitment stem cel differentiation stem cell population maintenance maintenanceof cell number

![](images/df7d893e0bb93dad601cffd8ba8e3036f86a21b019658db2102d652d5935c726.jpg)

![](images/9f8cf87a23d3e7f1c1744bcb1e769275fec060844e9416c3e68ce9748bb3d133.jpg)  
Go term enrichment stem cell division endoderm formation endoderm development

![](images/75f97077c4290ccbc2c33fc5feaa171d9c46acc9ac499f815527ea9044065e3a.jpg)

![](images/eee25ebceecad29adb15a752d05a441b4ff78f2837e291db46e37faaa33d9762.jpg)

![](images/3ec0c6f6e04e7ee569aa0cc834fb6d7f7bcb37387558edcdb8dfd4ba2cf2ebfb.jpg)

![](images/fbebda5f848c0a0a14cfcd30e62a0b5ac891dc552e45e56288ca3ecbf16fa6ee.jpg)

D  
![](images/de6739a38217a68905da9b557acf60737f00158df7d891e60b167fe3a627385e.jpg)

E  
![](images/92b3cf069646bb73d519f9864fcd6d310eddd84f10ac3e99e3abe111e012685c.jpg)

![](images/06105eaee8af54cdd83f51f964fc926c5709f9079f2c7d9d75509996fed3fd59.jpg)

![](images/bab28dd50a45f71c0387dd44439b11bc6e5ed1e7d2cdff7ffa0aa3b0e859908e.jpg)

F  
![](images/8e5c474fb8676609664d4d9770e0a76760243ef774324da29b2f44bfec27e0e7.jpg)

![](images/738a81bf45f634a27b2e91d6708c6861a68dde4b4b64dcb442e0bea73c2f71f3.jpg)

![](images/48395b1c4879e9b756fa14b1244b48991e362d0ad73e57c0bcbb8209125764ba.jpg)  
Figure 3. TRIGON is capable of identifying key TFs involved in the process of cellular differentiation. A, The mESC dataset consists of 421 scRNA-seq data capturing the differentiation of mouse embryonic stem cells into primitive endoderm, sequenced at five distinct time points. B, A TF regulon is defined as a gene set comprising the TF itself and its target genes, as determined by the inferred GRN. $\mathbf { C } ,$ The activity score of each TF regulon is calculated using the AUCell algorithm. ANOVA is performed on TF activity scores across the five sequencing time points, and TFs with P < 0.01 are identified as key TFs. The z-scores of activity scores are calculated and their temporal dynamics are visualized using a heatmap. D, Volcano plot from DEA, where the logFC threshold for identifying key TFs is set to 1, and pvalues are corrected using Bonferroni correction. DEA identifies a subset of key TFs (e.g., Pou5f1, Nanog and Sox2) also detected by TRIGON, while a group of genes labeled as “stable”

855 could not be identified as key TFs. E, The temporal trends of TF activity scores for key TFs   
856 identified by TRIGON are fitted with quadratic curves, illustrating their dynamics over   
857 differentiation process. F, Violin plots show the expression of two key TFs identified by   
858 TRIGON but not by DEA. These TFs exhibit minimal changes in expression across the five   
859 sequencing time points.   
865 between Nanog and its target genes highlighted using color intensity. C, Epigenomic data for   
866 mouse embryonic stem cells, including histone modification, scATAC-seq, and Hi-C data,   
867 provide evidence that TRIGON correctly identifies the regulatory relationships between Nanog   
868 and its four target genes (Ptpn6, Fkbp4, Eps8, and C2cd5). D, Dynamic GRNs inferred at time   
869 resolution of 4 demonstrate that the regulatory dynamics of Nanog, Esrrb, Nr0b1, and Utf1   
870 align closely with their gene expression trends. E, KDE plots of TF expression versus dynamic   
871 regulatory strength changes show PCC above 0.7, with Esrrb and Utf1 achieving PCC as high   
872 as 0.9, indicating a strong correlation between changes in gene expression and TF regulatory   
873 dynamics. F-G, TRIGON analyzes dynamic network changes across different time resolutions.   
874 Networks inferred at a resolution of 1 show the lowest performance, likely due to limitations in   
875 sequencing technology. As the resolution changes to 16, the PCC and R-squared of the dynamic   
876 GRN inferred by TRIGON steadily improve.

A  
![](images/71b468d2318d0ffd9447229f6472ebef3de50faa57c0bda347df6a7c72685aa3.jpg)

![](images/420931edcb58b7ec4d71b192081df4e8c01d8b47782bc866891010bd20d85630.jpg)  
B

![](images/0c5fa2e55084343800d48262eeebef9bd776d4f6282c7a0ae8a03a924f2625c7.jpg)

C  
![](images/3af5567c3466684d9c01b2a1665fa83fcbbcd3cd57feb03240b39a401e4014bf.jpg)

![](images/2f26cba05f937ec996ce8fb2318a05fa9e98e91935e6cfd46a39d2a47f7beb74.jpg)

D  
![](images/e481d43d74f94f9e4ec243252574607042aba010b37c4f2bcfc57891bd75baea.jpg)

![](images/99410371ea61eeb77f702aeca92e4ae062c1a3283158a88323cb155b7b78592c.jpg)

![](images/53c11117a12cd0abd09e2ad16a94e73347ab8aa48a5b190158618fa33e47620f.jpg)

![](images/88f4d58cb77dec0900cc5877f23b17b5ed329efd0fe614f90832feeb49985488.jpg)

E  
![](images/6d0f37d8c9582b9e5a5cb82e45af661f0ba49404112c17d933e60ddb089ae7e4.jpg)

F  
![](images/7a7c69aae8a0af44feb0ee7baa6561eb932c7086beff312cb055f2f0eab58015.jpg)

![](images/679b5b7f30b558b0d292d427f7846ee873b0930d23dcef7d18eab7c1a672d1d8.jpg)

![](images/c574fe9e8047dd07c06140403d1311d70b534725eb90c2ce33b704559c3ccbda.jpg)

G  
![](images/1b556d0167298cb1812cd3308191425cc9052d0a45fa34e0632decb3cc2329cf.jpg)

![](images/bfba436009314eed3d5fd5afcc136c53748bb8441ba58cf9ddc2bab552dd3d1c.jpg)  
Figure 4. TRIGON constructs dynamic GRNs across different time resolutions. A, Pipeline of dynamic GRN construction. For each watching window, the TF-TG regulatory strengths inferred in GRN are smoothed using gaussian smooth to generate temporal variation curves. B, The regulatory network of Nanog inferred by TRIGON, with the regulatory strengths

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

![](images/d147bcd829c3326051dd843dbec20a79b3685c7716759019ae361f4cf7157166.jpg)  
Figure 5. TRIGON predicts changes in cell fate through in silico perturbation. A, Pipeline of in silico perturbation. The expression of perturbed gene is set to zero, generating an expression difference vector. This vector is multiplied by the inferred GRN coefficient matrix to propagate the perturbation's effects to the target genes of the TF. Each cell ultimately generates a perturbation vector, whose direction indicates the cell's fate changes following the perturbation. B, The three lineages of mHSC dataset, detailing the associated cell states and differentiation trajectories. C, Gata1 promotes the differentiation of HSC toward the erythroid lineage, while Spi1 promotes the differentiation of HSC toward granulocyte-monocyte lineage and lymphoid lineage, and inhibits erythroid lineage differentiation. D, Pseudotime and Gata1 expression are colored on the erythroid lineage, along with the pseudotime gradient vector field and Gata1 knockout simulation vector field annotated with perturbation scores. E, Pseudotime and Spi1 expression are colored for the three lineages, along with pseudotime gradient vector fields and Spi1 knockout simulation vector fields annotated with perturbation scores. F, Perturbation score calculation process. If the pseudotime gradient vector and the perturbation vector are aligned in the same direction, the score is positive; if they are opposite, the score is negative. G, TRIGON accurately predicts gene expression changes following Gata1 knockout. The ground truth is derived from the difference between perturbed and wild-type cells.

## Extended Items

![](images/9dd2147abb938d9c7eb3bf6206473ac0a84e4ff1840dd7973d7b42b7944c59a2.jpg)

Figure 1. GRN inference process and workflows of AUCell, in silico perturbation. A, After training, TRIGON processes the testing data through its Regulatory filtering module to infer the GRN coefficient matrix. Regulatory scores are calculated for each TF-TG edge based on this matrix, and the top k edges are selected as the final inferred GRN. B, Threshold of AUCell is progressively increased to determine how many genes in each TF regulon are highly expressed in a given cell. The area under the resulting curve is computed as the TF's activity score. C, The effects of gene perturbations are propagated according to the GRN coefficient matrix. After each propagation step, the value of the perturbed gene is reset to its initial perturbation value to ensure the perturbation's influence persists throughout the whole propagation process. D, Once the final expression difference vector for a cell is obtained, the transition probabilities are calculated by comparing the vector to the original expression difference vectors of its neighboring cells. These probabilities are combined with the coordinate difference vectors in the 2D space of the cells to compute a weighted sum, resulting in the perturbation vector for the cell.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

![](images/0a196866d0b6e67fc64ad52941b013d8e7f5fd441e30b0b59059b175f971c728.jpg)  
Extended Figure 2. The activity score trends of key TFs identified by TRIGON. These activity scores were fitted with quadratic curves, revealing three distinct patterns of change.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

![](images/dd996d83d5008fb2864c08785a9f5191434d32805bb2b7dc07087cac8e1ed841.jpg)  
Extended Figure 3. TRIGON constructs dynamic GRNs at different time resolutions. At resolution of 1, the PCC between the regulatory strengths and the corresponding gene expression is the lowest. As the resolution changes to 16, the PCC steadily improve, reaching above 0.7.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

A  
![](images/a3186cd30727d9f4c992713ab7221f75cc73581ee22108aa52990163ccabc381.jpg)

![](images/0d28a0f854bf4df1a4edb96dff76ffe6a15ac72d5f1983b6f81bd3edd5ff5a0a.jpg)

B  
![](images/e16196447321d7d57b6f7191404d6ae72aa831450cae68e94a4034c052c80220.jpg)

![](images/e3cc397327aff365d118a33930daadd3e7608baa685e784e8dfd7c0ec325cb6f.jpg)

![](images/af96d2fe64c14280ac843ded7b1631943c5a0b2730b048f1f9136276ef7578c6.jpg)

![](images/41b9cbdd9c1d78fe02e8992f158d428d0be74668e66847eae5f4b6d17477b412.jpg)

C  
![](images/d2941921bdef0beea90434dfb869941870706109690440d5c8b296a366514185.jpg)

![](images/61408249b4362bc2126e8f34b857f0c9e16eb087098adb29f9ea6b0e5ffce680.jpg)

D  
![](images/5b533e0eca0c20c62a86ef065ab95072ae383e54a034802ffbf4e275dc2c04fe.jpg)

![](images/31900ce97e38f81a40c62962e4fe739d46c25f1dce7857825572578b069d2651.jpg)

E  
![](images/9bc3a0929dece4ca49b5ebc2ef94433f69990fa8e333bc80f1517a178cb1d5ec.jpg)

![](images/9d6e1ed723fbe5787501c275db3886e75c81e7c1329c9e02597fb22eb5090ff5.jpg)  
Extended Figure 4. Dynamic GRN of Sox2. A, Four target genes of Sox2 (Elf2, Setd7, Trim59, Kpna4) inferred by TRIGON are validated by Hi-C and scATAC-seq data. B, Dynamic GRN of Sox2 at time resolution of 16. C, In the inferred Sox2 dynamic GRN, regulatory strength shows a high correlation with Sox2 gene expression. D-E, Comparison of PCC and Rsquared for the Sox2 dynamic GRN across different time resolutions.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

<table><tr><td></td><td>mESC</td><td>mHSC-E</td><td> mHSC-GM</td><td> mHSC-L</td></tr><tr><td>Genes</td><td>1652</td><td>1933</td><td>1520</td><td>640</td></tr><tr><td>Potential edges</td><td>1363726</td><td>1867278</td><td>115440</td><td>204480</td></tr><tr><td>Positive edges</td><td>24557</td><td>24726</td><td>16198</td><td>4705</td></tr><tr><td>Proportion of positive edges</td><td>1.80%</td><td>1.30%</td><td>1.40%</td><td>2.30%</td></tr></table>

Extended Table 1. Label distribution. Across the four datasets, positive edges account for only 1.8%, 1.3%, 1.4%, and 2.3% of all potential edges, respectively. This indicates that positive labels are significantly outnumbered by negative labels, resulting in severe class imbalance.

bioRxiv preprint doi: https://doi.org/10.1101/2025.02.05.636766; this version posted February 8, 2025. The copyright holder for this preprint (which was not certified by peer review) is the author/funder. All rights reserved. No reuse allowed without permission.

<table><tr><td></td><td>mESC</td><td>mHSC-E</td><td>mHSC-GM</td><td> mHSC-L</td></tr><tr><td>Base GRN edges</td><td>7100331</td><td>7100331</td><td>7100331</td><td>7100331</td></tr><tr><td>Ground truth GRN edges</td><td>24557</td><td>24726</td><td>16198</td><td>4705</td></tr><tr><td>Overlap edges</td><td>24557</td><td>24726</td><td>16198</td><td>4705</td></tr><tr><td>Positive edges proportion</td><td>0.35%</td><td>0.35%</td><td>0.23%</td><td>0.07%</td></tr></table>

Extended Table 2. Noise distribution in the Base GRN. Across the four datasets, edges present in the ground truth GRN account for less than 0.4% of the edges in the base GRN, indicating that the base GRN contains a substantial amount of noise. TRIGON needs to identify the 0.4% of the whole edges in base GRN that correspond to the ground truth GRN.