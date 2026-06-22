# Zero-shot evaluation reveals limitations of single-cell foundation models — Source Index

**Authors:** Kasia Z. Kedzierska, Lorin Crawford, Ava P. Amini, Alex X. Lu
**Journal / Venue:** Genome Biology, 2025 (article s13059-025-03574-x; volume/issue/pages not printed in extracted text — see Flags)
**DOI:** doi:10.1186/s13059-025-03574-x
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/04 - Zero-shot evaluation reveals limitations of single-cell foundation models_cleaned.md

---

## In One Sentence
The paper benchmarks two popular single-cell foundation models (Geneformer and scGPT) in zero-shot settings — i.e., using their pretrained embeddings with no further training — and finds that on cell-type clustering, batch integration, and gene-expression reconstruction they perform inconsistently and are frequently outperformed by simpler, lighter baselines (highly variable genes, scVI, Harmony).

## Orientation (non-binding)
Sits squarely on our Claim 1 (the data/model bottleneck): it is empirical evidence that scaling foundation models on large RNA-only corpora does not reliably yield transferable, generalizable cell representations, and that "more/larger pretraining data" plateaus. It also strongly feeds Claim 9 (lack of standardized, reserved benchmarks; pretraining/evaluation dataset overlap that makes comparisons untrustworthy) via the authors' explicit proposal for held-out benchmark datasets. It self-concedes the premise of Claim 4 (modality narrowness — "our datasets only include transcriptomic data") and touches Claim 8 (cross-source/batch integration failure) and Claim 5 (need for perturbation/in-vitro ground truth). Can serve both as direct support (foundation-model hype outruns its data foundation) and as a methods-side "modeling paper" we cite to argue the bottleneck is upstream of the model — downstream agent decides.

---

## Load-Bearing Excerpts

> "Our evaluation of the zero-shot performance of Geneformer and scGPT suggests that, in some cases, these models may face reliability challenges and could be outperformed by simpler methods."
> — Abstract · bears on: Claim 1 · the two named foundation models can lose to simpler baselines.

> "we test this claim and show that even with a set of benchmarks representing the most favorable setting where datasets consist of tissues and are generated using technologies similar to those used to pretrain these models (Additional file 2: Figs. S1 and S2), both Geneformer and scGPT underperform simpler methods."
> — Background · bears on: Claim 1 · underperformance holds even under conditions most favorable to the models.

> "We show that zero-shot evaluation of these models exposes vulnerabilities that are not evident if evaluated with fine-tuning alone."
> — Background · bears on: Claim 1, Claim 9 · evaluation mode (zero-shot vs fine-tune) changes the verdict on these models.

> "Both models perform worse than selecting highly variable genes (HVG) and using more established methods such as Harmony and scVI in cell type clustering, as measured by average BIO (AvgBio) score (Fig. 1B, Additional file 1: Table S1)."
> — Results and discussion · bears on: Claim 1 · foundation models lose to HVG/Harmony/scVI on cell-type clustering.

> "Notably, HVG outperforms Geneformer and scGPT across all metrics (Additional file 2: Fig. S4, Additional file 1: Tables S1 and S2)."
> — Results and discussion · bears on: Claim 1 · a trivial gene-selection baseline beats both models on every metric.

> "However, scGPT and Geneformer do not consistently outperform baselines on datasets already seen during pretraining, and the only dataset not seen during pretraining where scGPT outperforms both baselines is the the PBMC 12k study."
> — Results and discussion · bears on: Claim 1, Claim 9 · even on data seen in pretraining, models do not reliably win.

> "Our analysis indicates that pretraining provides a clear improvement in cell-type clustering on the PBMC (12k) dataset, and that the median score, calculated across datasets, for the three scGPT models is greater than that of the random baseline."
> — Results and discussion · bears on: Claim 1 · pretraining does help over a random-init model on aggregate (nuance: some benefit exists).

> "Surprisingly, scGPT human slightly underperforms scGPT blood, even for datasets involving tissue types beyond blood and bone marrow cells (Additional file 2: Fig. S5, Additional file 1: Table S4)."
> — Results and discussion · bears on: Claim 1 · the largest/most-diverse pretrained variant does not dominate a smaller tissue-specific one.

> "Overall, our findings demonstrate that scGPT and Geneformer in zero-shot configurations perform inconsistently compared to cell embeddings derived from HVG or generated using scVI or Harmony."
> — Results and discussion · bears on: Claim 1 · headline result: inconsistent performance vs simple baselines.

> "Evaluating variants of the scGPT model highlights that while pretraining confers some benefit, beyond a certain limit, larger and more diverse datasets may no longer confer additional benefits."
> — Results and discussion · bears on: Claim 1, Claim 10 · diminishing returns to scaling pretraining data of the same kind.

> "Additionally, models did not perform well on datasets seen during pretraining, indicating an unclear relationship between the pretraining objective and cell type clustering."
> — Results and discussion · bears on: Claim 1 · the pretraining objective does not cleanly transfer to the downstream task.

> "While Geneformer and scGPT-human can integrate different experiments conducted with the same experimental technique, they generally fail to correct for batch effects between techniques."
> — Results and discussion · bears on: Claim 8, Claim 9 · models fail at cross-technology integration (a comparability/integration failure).

> "Qualitatively, Geneformer's cell embedding space fails to retain information about cell type, and any clustering is primarily driven by batch effects."
> — Results and discussion · bears on: Claim 8, Claim 9 · embeddings dominated by batch (technical) rather than biological structure.

> "Geneformer's embeddings across all datasets show a higher proportion of variance explained by batch effects compared to the original data, indicating inadequate batch mixing (Additional file 2: Fig. S6B)."
> — Results and discussion · bears on: Claim 8, Claim 9 · the model worsens batch separation relative to raw data.

> "Surprisingly, the best batch integration scores for all datasets were achieved by selecting HVG (Additional file 1: Table S2)."
> — Results and discussion · bears on: Claim 1, Claim 8 · HVG also wins on batch integration.

> "Notably, scGPT without embeddings underperforms against a naive baseline of predicting the mean, and only marginally improves with the cell embeddings (Fig. 2D)."
> — Results and discussion · bears on: Claim 1 · on its own reconstruction task, scGPT can lose to predicting the mean.

> "Geneformer's gene ranking exhibits modest correlations with the actual true rankings, with median and best correlations of 0.56 and 0.95, respectively, across datasets (Fig. 2E, Additional file 2: Fig. S7)."
> — Results and discussion · bears on: Claim 1 · quantifies weak-to-moderate reconstruction fidelity (median r=0.56).

> "Our findings raise questions about the general suitability of MLM for learning single-cell embeddings."
> — Conclusions · bears on: Claim 1 · doubts the core self-supervised pretraining objective for single-cell.

> "Our findings indicate that both models, in their current form, do not consistently outperform simpler baselines and face challenges in dealing with batch effects."
> — Conclusions · bears on: Claim 1, Claim 8 · summary verdict.

> "This is in spite of these models reporting strong performance when fine-tuned, as exhibited in their original papers, demonstrating that zero-shot evaluation can reveal vulnerabilities that are not evident if models are exclusively evaluated with fine-tuning."
> — Conclusions · bears on: Claim 1, Claim 9 · published (fine-tuned) results overstate generalization; evaluation protocol matters.

> "Additionally, we demonstrate that larger pretraining datasets do not always increase the performance of scGPT, and that datasets seen in pretraining still have poor cell type clustering performance."
> — Conclusions · bears on: Claim 1, Claim 10 · data scaling is not a guaranteed fix; restates the plateau.

> "We concentrated on specific models and selected a limited array of datasets that do not exhaustively represent all applications of single-cell analysis (for example, our datasets only include transcriptomic data)."
> — Conclusions · bears on: Claim 4 · author-conceded scope limit: transcriptome-only data (the RNA-only paradigm).

> "In fact, some more recent advances occurring at time of our work have already sought to address limitations exposed by our analysis, for example, in improving the representation of genes by transferring knowledge from proteins [11]."
> — Conclusions · bears on: Claim 4 · points to protein information as a fix for transcriptome-only gene representations.

> "However, in many cases methods do not make their pretraining code publicly available [11, 12]."
> — Conclusions · bears on: Claim 9 · reproducibility/transparency gap across methods.

> "One limitation of our analyses was that some of our evaluation datasets were used in pretraining, confounding our ability to say if performance trends are general or due to prior exposure to specific datasets."
> — Conclusions · bears on: Claim 9 · pretraining/evaluation data overlap confounds benchmarking.

> "To tackle this, we propose the creation of benchmark tasks and datasets reserved exclusively for model evaluation that should never be used to pretrain any future model, as has been done for large language models (LLMs) [26–29]."
> — Conclusions · bears on: Claim 9 · explicit call for held-out, standardized benchmark datasets (LLM-style).

> "These datasets should be a representative yet separate subset of the broader available data, ensuring an unbiased and effective assessment of model performance. The curation of biologically grounded, standalone benchmark datasets would provide a substantial advancement towards more reliable and robust evaluation methods."
> — Conclusions · bears on: Claim 9 · what a proper benchmark standard should look like.

> "Determining how effectively these models adjust for batch variations is a challenging yet an important investigation—particularly since correlating their batch correction efficacy with performance in downstream applications, such as perturbation predictions, could provide deeper insights into the practical utility of the proposed foundation models."
> — Conclusions · bears on: Claim 5, Claim 8 · links batch correction to perturbation-prediction utility (phenotype grounding).

> "Careful evaluation of this aspect [gene-gene interactions] is essential but requires thoughtful consideration and ideally should be paired with targeted in vitro lab experiments. These experiments are crucial for establishing a ground truth, which, in turn, enables an accurate assessment of the models' true capabilities in unraveling complex biological interactions."
> — Conclusions · bears on: Claim 5 · calls for in-vitro experiments as ground truth (paired/grounded supervision signal).

> "We chose these models because they offer pretrained weights and have been trained using unsupervised objectives on extensive datasets (ca. 30M single-cell transcriptomes)."
> — Methods (Models and baselines) · bears on: Claim 4 · the paradigm under test is pretrained on ~30M RNA-only transcriptomes.

> "Geneformer was pretrained on 27.4M human single-cell transcriptomes (excluding malignant and immortalized cells)."
> — Methods (Models and baselines) · bears on: Claim 4 · quantifies Geneformer's RNA-only pretraining corpus.

> "While this means that we deploy scGPT and Geneformer zero-shot but train scVI and Harmony on target data, we reason this set-up reflects practical settings where resources are often more readily available to train lightweight models than to fine-tune larger ones."
> — Methods (Models and baselines) · bears on: Claim 1 · framing: lightweight task-trained models are the practical comparator that the foundation models lose to.

> "Importantly, both Harmony's and scVI's design inherently incorporates batch labels in its training process... In contrast, Geneformer and scGPT are not explicitly pretrained with batch labels. Instead, they aim to learn to mitigate batch effects indirectly through exposure to a vast diversity of cells during their pretraining phase."
> — Methods (Models and baselines) · bears on: Claim 8, Claim 1 · explains why the implicit "diversity of cells" route to batch correction underperforms explicit batch-aware methods.

> "Among the selected datasets, the Pancreas dataset partially overlapped with the data used to pretrain Geneformer... The Tabula Sapiens and Immune were included in the CellxGene collection [4] (May 2023 census) used for scGPT pretraining."
> — Methods (Datasets) · bears on: Claim 9 · concrete instance of evaluation/pretraining overlap.

> "Despite its criticality for potential applications, zero-shot evaluation remains infrequent among single-cell foundation models."
> — Background · bears on: Claim 1, Claim 9 · evaluation practice in the field is immature/incomplete.

> "recent research in protein language models has exposed numerous trivial mechanisms in which transfer learning can appear to boost performance on downstream tasks, but does not actually rely upon sophisticated learning from pretraining [17]."
> — Background · bears on: Claim 1 · prior-art caution that apparent transfer-learning gains can be illusory.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — Data is the bottleneck; pure data-driven foundation models generalize poorly | "both Geneformer and scGPT underperform simpler methods" / Background; "perform inconsistently compared to cell embeddings derived from HVG" / Results; "larger pretraining datasets do not always increase the performance" / Conclusions | supports |
| Claim 4 — Modality too narrow (RNA-only); modalities mutually irreplaceable | "our datasets only include transcriptomic data" / Conclusions; "improving the representation of genes by transferring knowledge from proteins [11]" / Conclusions; "ca. 30M single-cell transcriptomes" / Methods | supports |
| Claim 5 — Protein/phenotype/perturbation modalities indispensable; need grounded supervision | "paired with targeted in vitro lab experiments... crucial for establishing a ground truth" / Conclusions; "downstream applications, such as perturbation predictions" / Conclusions | nuances |
| Claim 8 — Multi-source/multi-modal data need integration | "they generally fail to correct for batch effects between techniques" / Results; "Geneformer consistently ranks at the bottom across all metrics" / Results | supports |
| Claim 9 — Data islands / cross-paper incomparability / lack of standards | "we propose the creation of benchmark tasks and datasets reserved exclusively for model evaluation" / Conclusions; "some of our evaluation datasets were used in pretraining, confounding our ability" / Conclusions | supports |
| Claim 10 — Resolution × throughput × destructiveness trade-offs / diminishing scaling | "beyond a certain limit, larger and more diverse datasets may no longer confer additional benefits" / Results | nuances |
| Axis B — Temporal | (not addressed; datasets are static dissociated single-cell snapshots) | — |
| Axis C — Spatial | (not addressed; datasets are dissociated, no spatial information) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Evaluation of cell-embedding space. A: setup — Geneformer & scGPT vs scVI, Harmony, HVG on five datasets. B: AvgBIO scores (cell-type clustering). C–D: UMAP of Pancreas (16k) colored by cell type (C) and batch (D). E: Average batch score (batch integration). Dashed lines = median across datasets. |
| Fig. 2 | Gene-expression reconstruction. A: scGPT GEP (MLM). B: scGPT GEPC (from cell embeddings). C: Geneformer predicted vs true expression ranking. D: MSE for scGPT objectives, with median MSE of mean-based reconstruction as dashed line (scGPT underperforms it). E: Pearson correlation of input vs predicted ranking for Geneformer and for average ranking. |
| Datasets (n=5, all human, transcriptomic) | Pancreas (16k) [25]; PBMC 12k [30]; PBMC 95k [31]; cross-tissue Immune cell atlas (~330k) [32]; Tabula Sapiens multi-organ atlas [33]. |
| Model scale — Geneformer | Pretrained on 27.4M human single-cell transcriptomes (excluding malignant/immortalized); BERT-style, 6 Transformer layers, 4 attention heads; outputs gene rankings; cell embedding = mean of gene embeddings. |
| Model scale — scGPT | 50 equidistant expression bins; MLM with learned cell embedding; 12 Transformer layers, 8 attention heads, ~3× Geneformer parameters. Variants: scGPT kidney (814k cells), scGPT blood (10.3M blood + bone marrow cells), scGPT human (33M non-cancerous human cells). |
| Key reconstruction numbers | Geneformer ranking correlation vs truth: median 0.56, best 0.95 across datasets. scGPT (no embeddings) underperforms predicting-the-mean baseline; marginal improvement with cell embeddings. |
| Baselines | HVG standardized to 2000 genes across all experiments; scVI and Harmony trained per-dataset (incorporate batch labels); foundation models deployed zero-shot. |
| Metrics | Biological preservation: ASW, AvgBIO (= mean of ASW, NMI, ARI). Batch mixing: batch integration score (ASW-for-batch) and PCR score; Average Batch Score = mean of the two. Framework follows Luecken et al. [25] (scib v1.0.4). |

---

## Primary Sources Behind Key Quotes
- Geneformer (model under evaluation) → Theodoris CV, et al. Nature. 2023;618(7965):616–24. (ref #6)
- scGPT (model under evaluation) → Cui H, et al. Nat Methods. 2024;21(8):1470–80. (ref #7)
- scVI baseline → Lopez R, et al. Nat Methods. 2018;15(12):1053–8. (ref #20)
- Harmony baseline → Korsunsky I, et al. Nat Methods. 2019;16(12):1289–96. (ref #21)
- Benchmarking framework / metrics (atlas-level integration) → Luecken MD, et al. Nat Methods. 2022;19(1):41–50. (ref #25)
- "Transfer learning can appear to boost performance... trivial mechanisms" (protein LMs) → Li FZ, Amini AP, Yue Y, Yang KK, Lu AX. bioRxiv. 2024 (Feature reuse and scaling). (ref #17)
- "Transferring knowledge from proteins" to improve gene representation (UCE) → Rosen Y, et al. bioRxiv. 2023 (Universal cell embeddings). (ref #11)
- Held-out benchmarks "as done for LLMs" → refs #26–29 (Hendrycks MMLU; Rein GPQA; Zellers HellaSwag; Wang GLUE).
- CELLxGENE data platform (pretraining data source) → Program CSCB, et al. bioRxiv. 2023. (ref #4)

---

## Flags
- [ ] Metadata unverified: Journal name "Genome Biology" is inferred from the DOI prefix 10.1186/s13059 (the Genome Biology journal code) and from in-paper self-citations to "Genome Biol" — the journal name is not printed verbatim in the extracted body. Volume/issue/page numbers are not present in the extracted text.
- [ ] Source OCR artifacts: the cleaned MD systematically drops ligatures (e.g., "fndings", "efects", "Te", "confgurations", "diferent", "fne-tuning"). Quotes above have these obvious scan errors normalized to standard English spelling; wording is otherwise unaltered and verbatim. Verify against the publisher PDF if exact glyphs matter.
- [ ] Read at source: Geneformer (ref #6, Nature 2023) and scGPT (ref #7, Nat Methods 2024) — the two models this paper critiques; read first-hand for their original (fine-tuned) performance claims. Luecken et al. (ref #25, Nat Methods 2022) for the benchmarking/comparability framework directly relevant to our Claim 9. Rosen et al. UCE (ref #11) for the protein-knowledge-transfer angle relevant to Claim 4.
- [ ] Scope note: paper addresses only the modeling/evaluation layer of dissociated single-cell transcriptomics; it does not discuss spatial or temporal data (our Axis B/Axis C). Its value to us is as evidence for the data/benchmark-standard side (Claims 1, 9) and as a self-conceded instance of RNA-only narrowness (Claim 4), not as a spatial/temporal source.
