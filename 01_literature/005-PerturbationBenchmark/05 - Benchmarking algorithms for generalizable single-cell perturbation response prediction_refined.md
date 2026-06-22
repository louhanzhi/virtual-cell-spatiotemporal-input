# Benchmarking algorithms for generalizable single-cell perturbation response prediction — Source Index

**Authors:** Zhiting Wei, Yiheng Wang, Yicheng Gao, Shuguang Wang, Ping Li, Duanmiao Si, Yuli Gao, Siqi Wu, Danlu Li, Kejing Dong, Xingbo Yang, Chen Tang, Shaliu Fu, Xiaohan Chen, Wannian Li, Yuzhou You, Chen Zhang, Aibin Liang, Guohui Chuai & Qi Liu
**Journal / Venue:** Nature Methods, 2025 (Vol/Issue/Pages unverified; see Flags)
**DOI:** doi:10.1038/s41592-025-02980-0
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/05 - Benchmarking algorithms for generalizable single-cell perturbation response prediction_cleaned.md

---

## In One Sentence
A comprehensive benchmark of 27 single-cell perturbation-response prediction methods (including foundation models and 4 baselines) across 29 datasets with 6 metrics, evaluated under two generalization scenarios (new cellular context; new perturbation), finding that no method works across all datasets, that generalization is governed more by data quality/similarity than by model complexity or dataset size, and that foundation models beat simple baselines only when fine-tuning data are large.

## Orientation (non-binding)
Strongest fit to roadmap Claim 1 (data is the bottleneck; pure data-driven / foundation models generalize poorly) and Claim 9 (cross-study incomparability, no metric/preprocessing standard). Also touches Claim 7 (perturbation response is cellular-context-dependent — "inter-heterogeneity"), Axis B / Claim 2-temporal angle (time-point/dosage covariates matter but are rarely used), Claim 10 (throughput/feasibility limits of large-scale screens; robustness to noise/sparsity), and weakly Claim 4 (expression data alone misses functional knowledge). Note: the paper is RNA-only and contains no spatial-omics or destructive-measurement/lineage-tracing argument, so it is silent on Axes C (spatial) and the explicit time-pairing constraint (Claim 3); per the context file's boundary, its granular per-tool selection guidance is out of scope and not captured as evidence. Can serve as BOTH support (its findings echo our "data > model" thesis) and as a representative artifact of the very fragmentation we critique.

---

## Load-Bearing Excerpts

> "Yet despite claims of promising performance, concerns remain about their true efcacy, particularly when evaluated across diverse and previously unseen cellular contexts and perturbation scenarios."
> — Abstract · bears on: Claim 1 · the paper frames foundation-model effectiveness as unsettled under unseen contexts.

> "Our results provide practical guidance for method selection and underscore the need for cellular context embedding approaches to enhance the generalizability of perturbation efect prediction in single-cell research."
> — Abstract · bears on: Claim 1, Claim 7 · central conclusion: generalizability requires encoding cellular context.

> "Despite its immense potential, the application of single-cell perturbation sequencing at large scales faces substantial practical and economic barriers. Conducting large-scale perturbation screens, particularly for combined perturbations, is infeasible because of the exponential growth in complexity."
> — Introduction · bears on: Claim 10 · throughput/economic ceiling on experimentally measuring perturbation combinations.

> "Specifically, many of these methods do not outperform baseline models or linear models on the basis of straightforward assumptions when they are evaluated across multiple datasets. This has led to a growing call for more comprehensive and rigorous assessments of these methods."
> — Introduction · bears on: Claim 1 · advanced models often fail to beat simple baselines across datasets.

> "Our study indicated that there is no 'one-size-fits-all' method that works well across all datasets."
> — Introduction · bears on: Claim 1, Claim 9 · no universally generalizable method.

> "In the cellular context generalization scenario, owing to limitations in algorithm design, that is, neglecting the specificity of perturbation responses across different cellular contexts (intercellular heterogeneity, or for simplicity inter-heterogeneity), all methods likely exhibit poor generalizability. Specifically, when predicting the effects of perturbations in a new cellular context that is quite different from the training datasets, all methods performed poorly, even worse than the baseline models."
> — Introduction · bears on: Claim 1, Claim 7 · all methods fail to generalize to a dissimilar new cellular context, falling below baselines.

> "By analyzing datasets of varying sizes, it is found that baseline models tend to perform better on smaller training datasets. In contrast, foundation models tend to perform better in terms of both prediction accuracy and generalizability, when the fine-tuning datasets are sufficiently large."
> — Introduction · bears on: Claim 1 · foundation-model advantage is conditional on large fine-tuning data; baselines win on small data.

> "For challenging cases where perturbation effect prediction needs to be generalized to a new cellular context that is substantially different from the model's training contexts, we explored a cellular context embedding strategy as a potential approach to enhance generalization."
> — Introduction · bears on: Claim 1, Claim 7 · proposes injecting cellular-context prior knowledge to aid generalization.

> "Accuracy evaluation presents a particular challenge because of the lack of consensus on the most suitable evaluation metrics in the feld. A variety of metrics have been proposed for evaluating single-cell perturbation efect prediction performance, but their reliability and informativeness are still debated."
> — Results, Evaluation metrics · bears on: Claim 9 · no community consensus on evaluation metrics.

> "we conducted an extensive literature survey covering 28 existing tools and benchmarking studies in the feld … From these sources, we identifed 19 evaluation metrics and selected three population-average metrics and three population-distribution metrics"
> — Results, Evaluation metrics · bears on: Claim 9 · 19 candidate metrics in circulation, reduced to 6 — quantifies metric fragmentation.

> "Furthermore, we found that, in contrast to population-average metrics, all methods performed relatively poorly on population-distribution metrics, particularly on the Common-DEGs metric. … on average, only about 10% of the true most differentially expressed genes were recovered."
> — Results, cellular context generalization · bears on: Claim 1, Claim 3 (distribution-level), Claim 9 · methods capture average effects but fail at the single-cell distribution and at recovering DEGs.

> "Among the 14 methods tested, only biolord, scDisInFact and scVIDR utilized these additional metadata … time-point/dosage covariates generally had a substantial effect on the cellular response."
> — Results, cellular context generalization · bears on: Axis B (temporal), Claim 2 · time-point/dosage strongly shapes response, yet almost no method uses it.

> "Models that consider covariates affecting cellular responses provide more accurate predictions of single-cell perturbation effects. However, most existing tools do not incorporate covariates, and those that do are still far from being sufficiently accurate. Given the increasing availability of multi-condition data in the single-cell perturbation field, there is a pressing need to develop high-performing models tailored for multi-condition data"
> — Results, cellular context summary · bears on: Axis B (temporal), Claim 2, Claim 8 · multi-condition (time/dose) data are under-exploited; covariate/condition information improves prediction.

> "As the noise and sparsity in the data increased, the performance of all methods decreased markedly … We also noted that the performance of the algorithms deteriorated more severely for high-sparsity data, indicating that their performance is more sensitive to data sparsity."
> — Results, cellular context generalization · bears on: Claim 1, Claim 10 · prediction quality is bounded by data noise/sparsity, especially sparsity (a single-cell data-quality limit).

> "in the Afriat dataset, even the trainMean baseline performed exceptionally well, with a median PCC-delta of 0.92 and an average value of 0.85 … in datasets such as KaggleCrossCell, all machine learning models performed poorly, with a median PCC-delta of 0.54 and an average value of 0.52"
> — Results, Limitations (cellular context) · bears on: Claim 1, Claim 9 · performance is dataset-driven, not method-driven; a trivial mean baseline can top complex models.

> "when the inter-heterogeneity between the test context and training context was low, the methods generally performed well. In contrast, when the inter-heterogeneity between the test context and training context was high, the performance of the methods was poor. This result indicated that it is still challenging for the current methods to be generalized to a new cellular context that is dissimilar to the training cellular context"
> — Results, Limitations (cellular context) · bears on: Claim 1, Claim 7 · generalization fails exactly where train/test contexts are dissimilar.

> "the performance of the evaluated methods is highly dependent on the inter-heterogeneity. When predicting perturbation effects in a new cellular context that differs substantially from the training datasets, all methods likely performed unsatisfactorily, highlighting their limited generalizability. We believe that accounting for intercellular heterogeneity is crucial for enhancing the generalizability of current models across diverse cellular contexts."
> — Results, Limitations (cellular context) summary · bears on: Claim 1, Claim 7 · cellular-context heterogeneity is the dominant determinant of generalization failure.

> "It is surprising that models relying on unaligned natural language embeddings outperform those leveraging transcriptome-informed embeddings. … This suggests that the performance advantage likely stems from the rich biological priors embedded in LLM-derived embeddings, rather than model complexity or architecture."
> — Results, Genetic perturbation setting · bears on: Claim 1, Claim 4 · representational priors, not architecture, drive gains; transcriptome-derived embeddings underperform.

> "These results indicate that LLM-derived gene embeddings may capture high-level functional and contextual knowledge that is otherwise hard to extract from gene expression data alone."
> — Results, Genetic perturbation setting · bears on: Claim 4 · gene-expression data alone is insufficient to capture functional/contextual knowledge.

> "In our study, the four baseline models and linearModel performed relatively poorly, which differs from the findings of previous studies—potentially due to differences in data preprocessing and the size of the training set"
> — Results, Genetic perturbation setting · bears on: Claim 9 · explicitly attributes contradictory cross-study conclusions to preprocessing/training-set differences (incomparability).

> "recent studies suggest that for predicting gene expression profiles under combined perturbations, the simplest additive model … often outperforms complex deep learning models or foundation models such as scGPT. However, these conclusions were derived from a single dataset."
> — Results, perturbation generalization · bears on: Claim 1, Claim 9 · prior "linear beats deep" claims rested on a single dataset — motivates broader, comparable benchmarking.

> "increasing the number of cells or perturbations in the training data did not lead to performance gains across all evaluation metrics … Further analysis revealed that model performance declined on perturbations with high inter-heterogeneity, suggesting that generalization is more strongly influenced by data quality—particularly the similarity between training and testing perturbations—than by dataset size."
> — Results, Limitations (perturbation generalization) · bears on: Claim 1, Claim 9 · data quality/similarity, not scale, drives generalization.

> "strong perturbations were associated with increased MSE, E-distance and Wasserstein values, suggesting greater difficulty in accurately capturing their expression responses … these findings highlight the current limitations in the generalizability of deep learning models for perturbation effect prediction, especially in the presence of strong perturbations and heterogeneous perturbations"
> — Results, Limitations (perturbation generalization) · bears on: Claim 1 · the strongest, most informative perturbations are the hardest to predict.

> "We observed that all methods likely performed poorly on population-distribution metrics especially on the Common-DEGs metric in genetic perturbation scenarios. For instance, in genetic single-perturbation datasets, even the best-performing model, baseMLP, identified fewer than 10 of 100 true most differentially expressed genes"
> — Results, Limitations (perturbation generalization) · bears on: Claim 1, Claim 3 (distribution-level) · even the best model recovers <10/100 true DEGs — distribution/heterogeneity prediction is largely unsolved.

> "Typically, deep learning models in the perturbation effect prediction field are optimized using loss functions that focus more on population-average metrics. This may account for the strong performance of these methods on such metrics and their poorer results regarding population-distribution metrics. However, understanding the heterogeneity within cellular subpopulations in response to perturbations is vital"
> — Discussion · bears on: Claim 1, Claim 3 (distribution-level) · current objectives optimize averages and miss single-cell heterogeneity.

> "advanced models tend to underperform relative to simpler approaches, particularly on small-scale datasets. This finding suggests that complex models may struggle to generalize effectively in low-data regimes."
> — Discussion · bears on: Claim 1 · complex/foundation models fail in low-data regimes.

> "All current methods likely exhibited poor generalizability, especially when predicting perturbation effects in novel cellular contexts. To alleviate this, we propose incorporating prior knowledge through cell-line embeddings, which can improve model generalizability"
> — Discussion · bears on: Claim 1, Claim 7 · poor generalization to novel contexts is the headline limitation; prior knowledge proposed as remedy.

> "our proposed cellular context embedding strategy is currently applicable only to cell-line-derived contexts and cannot be directly applied to patient-derived contexts"
> — Discussion, limitations · bears on: Claim 7 · the context-embedding fix does not yet transfer to real patient contexts (conceded limitation).

> "its current performance demonstrates only limited improvements—mainly in the PCC-delta and Common-DEGs metrics—and does not consistently surpass baseline methods across evaluation metrics on all the evaluated datasets."
> — Discussion, limitations · bears on: Claim 1 · author-conceded: even their proposed remedy does not reliably beat baselines.

> "Our current work does not address the challenge of poor performance on population-distribution metrics, which reflect a model's ability to capture intracellular heterogeneity."
> — Discussion, limitations · bears on: Claim 1, Claim 3 (distribution-level) · capturing intracellular heterogeneity remains unsolved (conceded).

> "it does not capture biological variability in perturbation responses across different cellular contexts or genetic backgrounds. Evaluating robustness to biological variation with simulator tools such as scDesign3 … remains an important and complementary direction"
> — Discussion, limitations · bears on: Claim 7, Claim 10 · robustness analysis covered only technical (noise/sparsity) artifacts, not biological context variability (conceded scope limit).

> "There is an urgent need to establish more diverse and comprehensive single-cell perturbation atlases. … systematically building perturbation-focused cell atlases could catalyze progress … Notably, Rood et al. have proposed the concept of a 'perturbation cell atlas' … Large-scale resources such as Tahoe-100M and X-Atlas have begun to fill this gap by providing comprehensive perturbation datasets, which lay a strong foundation for future benchmarking"
> — Discussion, outlook · bears on: Claim 1, Claim 9 · calls for large standardized perturbation atlases as the data foundation for the field.

> "Future work may further explore the integration of prior biological knowledge—such as gene regulatory networks or pathway information—into model design to enhance generalization across a wide range of cellular contexts. Incorporating biological priors could substantially improve the robustness and interpretability"
> — Discussion, outlook · bears on: Claim 1, Claim 8 · prior biological knowledge (networks/pathways) proposed to improve cross-context generalization.

> "the field of chemical perturbation prediction, especially in the context of chemical combination effects, remains underdeveloped … More dedicated research is needed to develop specialized algorithms capable of accurately modeling chemical combination perturbations"
> — Discussion, outlook · bears on: Claim 10 · combinatorial (chemical) perturbation space is largely unaddressed.

> "For the cellular generalization scenario, we curated 12 single-cell datasets, resulting in 477,677 cells and 73 perturbations. For the perturbation generalization scenario, we curated 17 single-cell datasets, resulting in 1,588,215 cells and 4,874 perturbations. We collected all publicly available datasets that have been used by existing perturbation prediction methods"
> — Reporting Summary, Sample size · bears on: Claim 9 · scale and scope of the benchmark corpus (assembled from all prior public perturbation datasets).

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data is bottleneck; data-driven/foundation models generalize poorly | "many of these methods do not outperform baseline models" / Intro; "no 'one-size-fits-all'" / Intro; "all methods performed poorly, even worse than the baseline models" / Intro; "generalization is more strongly influenced by data quality … than by dataset size" / §Limitations(pert); "complex models may struggle … in low-data regimes" / Discussion | supports |
| Claim 2 — temporal info lost / under-used (Axis B) | "only biolord, scDisInFact and scVIDR utilized these additional metadata" / §cellular ctx; "pressing need to develop high-performing models tailored for multi-condition data" / §cellular ctx summary | nuances |
| Claim 3 — destructive seq → distribution-to-distribution, no paired time | "only about 10% of the true most differentially expressed genes were recovered" / §cellular ctx; "all methods … poorly on population-distribution metrics" / §Limitations(pert); "does not address … population-distribution metrics, which reflect … intracellular heterogeneity" / Discussion | nuances |
| Claim 4 — modalities orthogonal; RNA alone insufficient | "high-level functional and contextual knowledge that is otherwise hard to extract from gene expression data alone" / §Genetic pert | nuances |
| Claim 7 — cellular context / microenvironment changes perturbation response | "neglecting the specificity of perturbation responses across different cellular contexts (… inter-heterogeneity)" / Intro; "highly dependent on the inter-heterogeneity" / §Limitations(cellular ctx); "cannot be directly applied to patient-derived contexts" / Discussion | supports |
| Claim 8 — multimodal/prior-knowledge integration needed | "integration of prior biological knowledge—such as gene regulatory networks or pathway information" / Discussion; "Models that consider covariates … provide more accurate predictions" / §cellular ctx summary | supports |
| Claim 9 — data islands / cross-study incomparability / no standard | "lack of consensus on the most suitable evaluation metrics" / §Eval metrics; "differs from the findings of previous studies—potentially due to differences in data preprocessing" / §Genetic pert; "these conclusions were derived from a single dataset" / §pert gen; "urgent need to establish more diverse and comprehensive … atlases" / Discussion | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "large-scale perturbation screens … infeasible because of the exponential growth in complexity" / Intro; "performance of all methods decreased markedly" with noise/sparsity / §cellular ctx; "chemical combination … remains underdeveloped" / Discussion | supports |
| Axis C — spatial resolution | (paper is RNA-only; no spatial data or argument) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Scope totals | 27 methods (23 published + 4 baselines: baseReg, baseMLP, baseControl, trainMean), 29 datasets, 6 metrics. Cellular context scenario: 14 methods × 12 datasets. Perturbation scenario: 18 methods × 17 datasets. |
| Fig. 1b (Table) | 12 cellular-context datasets: 8 cross-cell-line, 3 cross-patient, 1 cross-species; 7 single-condition, 5 multi-condition (time-point/dosage metadata). |
| Fig. 1c (Table) | 17 perturbation datasets: 13 genetic (9 single, 4 combined) + 4 chemical (3 single, 1 combined); perturbation counts range 25 to 1,618. |
| 6 metrics | Population-average: MSE, E-distance, PCC-delta (prioritized: MSE & PCC-delta). Population-distribution: Wasserstein distance, KL-divergence, Common-DEGs. Computed for all genes and for top-100 DEGs. |
| Sample sizes (Reporting Summary) | Cellular context: 477,677 cells, 73 perturbations. Perturbation: 1,588,215 cells, 4,874 perturbations. |
| ANOVA (line ~391-393) | Effect on MSE: inter-heterogeneity F=45.481, P=9.16e-09 (significant); intra-heterogeneity F=1.628, P=0.207 (n.s.). Effect on PCC-delta: inter-heterogeneity F=8.463, P=0.005; intra-heterogeneity F=0.304, P=0.584 (n.s.). |
| Selected performance numbers | Afriat trainMean: median PCC-delta 0.92, mean 0.85. KaggleCrossCell (all ML models): median PCC-delta 0.54, mean 0.52. Haber top method: mean PCC-delta 0.86 but large distribution mismatch; ~10% of true DEGs recovered. baseMLP recovers <10 of 100 true DEGs in genetic single-perturbation datasets. |
| Preprocessing constants | Cells filtered if <200 genes or >10% mitochondrial fraction; perturbations affecting <30 cells excluded; perturbations >2,000 cells subsampled to 2,000; genes in <3 cells removed; capped to top 5,000 highly variable genes (selected on training split only); normalized to 10,000 counts/cell then log-transformed (Scanpy). |
| Robustness simulation | Poisson noise at levels 0.1/0.3/0.5/0.7/0.9; sparsity (random dropout) at 0/0.1/0.3/0.5/0.7/0.9; generator script adapted from Yuan et al. (ref 50). |

---

## Primary Sources Behind Key Quotes
- "deep learning does not yet beat simple linear baselines" / single-dataset additive-model claim → Ahlmann-Eltze, C., Huber, W. & Anders, S. Nat. Methods 22, 1657–1661 (2025), ref 12.
- Other foundation-model effectiveness concerns → Wu, Y. et al. (PerturBench) arXiv 2408.10609 (2024), ref 10; Bendidi, I. et al. ("one PCA still rules them all") arXiv 2410.13956 (2024), ref 11.
- Metric-selection survey / "optimal distance metrics" basis → Ji, Y. et al. bioRxiv 2023.12.26.572833 (2023), ref 47. (Note: in-text alternately spelled "Jing et al." — see Flags.)
- Harmonized single-cell perturbation data / E-distance → Peidli, S. et al. (scPerturb) Nat. Methods 21, 531–540 (2024), ref 13.
- "Perturbation cell atlas" concept → Rood, J. E., Hupalowska, A. & Regev, A. Cell 187, 4520–4545 (2024), ref 55.
- Large-scale perturbation atlases → Zhang, J. et al. (Tahoe-100M) bioRxiv 2025.02.20.639398 (2025), ref 56; Huang, A. C. et al. (X-Atlas/Orion) bioRxiv 2025.06.11.659105 (2025), ref 57.
- scGen → Lotfollahi, Wolf & Theis, Nat. Methods 16, 715–721 (2019), ref 4. GEARS → Roohani, Huang & Leskovec, Nat. Biotechnol. 42, 927–935 (2024), ref 5. scGPT → Cui, H. et al. Nat. Methods 21, 1470–1480 (2024), ref 7. scFoundation → Hao, M. et al. Nat. Methods 21, 1481–1491 (2024), ref 6.
- Noise/sparsity simulation script → Yuan, Z. et al. Nat. Methods 21, 712–722 (2024), ref 50.

---

## Flags
- [ ] Metadata unverified: Volume, issue and page numbers not present in the source text; only DOI (10.1038/s41592-025-02980-0) and year (2025) confirmed. Venue identified as Nature Methods from the peer-review note ("Nature Methods thanks…", "Nature Methods team") and Springer Nature America 2025 copyright line, not from a formal citation block.
- [ ] No explicit received/accepted/published dates in the text; the only date is "Last updated by author(s): Oct. 31, 2025" from the Nature Portfolio Reporting Summary (not a publication date).
- [ ] Source inconsistency: the evaluation-metric reference is cited in-text as both "Ji et al." (ref 47, line ~37) and "Jing et al." (Methods, lines ~251, 255) — same ref 47 (Ji, Y. et al., bioRxiv 2023.12.26.572833). Treat as a single source.
- [ ] OCR artifacts in cleaned source: quotes retain original spellings such as "efcacy", "efect", "profles", "defned", "diferentially". Verify against the published PDF before quoting in final prose.
- [ ] Out-of-scope (per context file, "do not write specific modeling methods"): the paper's detailed per-tool selection guidance (e.g., GenePert vs CPA vs scGPT vs chemCPA, Fig. 3g / Fig. 5g) was deliberately NOT captured as evidence; only meta-level findings bearing on roadmap claims are indexed.
- [ ] Read at source (worth first-hand): Ahlmann-Eltze et al. 2025 (ref 12, linear-baseline critique), Rood et al. 2024 (ref 55, perturbation cell atlas), Peidli et al. 2024 (ref 13, scPerturb harmonization/standards), Ji et al. 2023 (ref 47, metric benchmark) — these underpin our Claim 1 and Claim 9 ammunition more directly than this benchmark.
