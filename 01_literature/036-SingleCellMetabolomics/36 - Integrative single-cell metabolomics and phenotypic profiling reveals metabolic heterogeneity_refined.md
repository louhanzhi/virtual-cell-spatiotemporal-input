# Integrative single-cell metabolomics and phenotypic profiling reveals metabolic heterogeneity of cellular oxidation and senescence — Source Index

**Authors:** Ziyi Wang, Siyuan Ge, Tiepeng Liao, Man Yuan, Wenwei Qian, Qi Chen, Wei Liang, Xiawei Cheng, Qinghua Zhou, Zhenyu Ju, Hongying Zhu & Wei Xiong (corresponding: Hongying Zhu, Wei Xiong)
**Journal / Venue:** Nature Communications, 2025 (exact volume/article number not printed in body text; see Flags)
**DOI:** doi:10.1038/s41467-025-57992-3
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/36 - Integrative single-cell metabolomics and phenotypic profiling reveals metabolic heterogeneity_cleaned.md

---

## In One Sentence
The authors build SCLIMS — a cross-modality platform pairing live-cell fluorescence imaging (oxidative-stress level via DCFDA) with single-cell mass spectrometry (metabolome) on the same individual cell — and show in HEK293T cells and MEFs that single-cell metabolomic heterogeneity correlates with, predicts, and causally precedes a cell's oxidative/senescent fate, with three depleted metabolites (hypotaurine, phosphocreatine, O-phosphoethanolamine) rescuing oxidative stress, senescence, and extending C. elegans lifespan ~33–50%.

## Orientation (non-binding)
This paper is a single-cell, non-RNA (metabolome) multimodal study and sits on BOTH sides of our thesis. As SUPPORT: it is direct, quantitative evidence that the metabolome is a non-substitutable modality carrying functional, fate-determining information that transcriptome/phenotype alone do not capture (feeds Axis A · modality, Claims 4/5/8) and that single-cell resolution recovers heterogeneity that bulk/homogenate measurement masks. As FOIL/illustration: the method itself is destructive (patch-clamp cytoplasm extraction → MS kills the cell), so it can only reconstruct time via pseudotime and must use a live GSH-dye proxy + FACS to study fate — a concrete instance of "destructive measurement cannot pair-observe the same cell over time" (Claim 3 / Axis B). It operates on dissociated, cultured cells and explicitly defers tissue/spatial application to future work (Axis C). Routing hint only; downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "Despite the pivotal roles of cellular metabolism, a comprehensive elucidation of metabolomic heterogeneity in cells and its connection with cellular oxidative and senescent status remains elusive."
> — Abstract · bears on: Axis A (modality/metabolome), Claim 5 · motivates why a non-RNA modality (metabolome) linked to phenotype is needed.

> "By integrating single-cell live imaging with mass spectrometry (SCLIMS), we establish a cross-modality technique capturing both metabolome and oxidative level in individual cells."
> — Abstract · bears on: Claim 8 (multimodal integration), Axis A · states the cross-modality single-cell integration the perspective argues for.

> "Furthermore, the single-cell metabolome predicted heterogeneous states of cells. Remarkably, the pre-existing metabolomic heterogeneity determines the divergent cellular fate upon oxidative insult."
> — Abstract · bears on: Claim 5 (metabolism indispensable for phenotype), Claim 4 · claims metabolome carries phenotype/fate-determining information.

> "A groundbreaking advancement in single-cell research lies in the seamless integration of multiple features or functions within individual cells, known as cross-modality analysis. This includes integrating single-cell omics with cellular function or phenotype, resulting in a truly remarkable and sophisticated approach."
> — Introduction · bears on: Claim 8, Axis A · frames cross-modality (omics + phenotype) integration as the advance.

> "Metabolism serves as both a reflection and regulator of cellular function."
> — Introduction (ref 15) · bears on: Claim 5, Claim 4 · asserts metabolome is functionally load-bearing, not a downstream readout only.

> "Currently, most metabolomics research remains confined to homogenate-level analysis involving the preparation of samples using bulk tissue or cell suspension. Consequently, the enigmatic metabolic heterogeneity exhibited by cells during biological processes and the underlying mechanisms at the single-cell level remain shrouded in ambiguity."
> — Introduction · bears on: Claim 10 (resolution trade-off), Axis A · concedes bulk/homogenate metabolomics masks single-cell heterogeneity → motivates single-cell resolution.

> "Recently, our laboratory and others have pioneered the development of cutting-edge single-cell mass spectrometry techniques, enabling us to unveil the intricate metabolic heterogeneity at an unprecedented resolution."
> — Introduction (refs 16–18) · bears on: Axis A (modality feasibility), Claim 6 (non-RNA modality already measurable at single-cell) · states single-cell metabolomics is technically feasible.

> "These new techniques mainly focused on the interpretation of the metabolome without the phenotype of single cells, omitting cross-modality features important for the better understanding of cellular metabolism and function. However, the integration of metabolic heterogeneity with phenotypic heterogeneity, such as distinct levels of oxidative or senescent states within individual cells, remains a formidable technical challenge."
> — Introduction · bears on: Claim 8, Claim 10 · names cross-modality (metabolome + phenotype) integration as an unsolved technical challenge.

> "In m/z ranging from 67 to 1000, a total of more than 500 ion signals, with signal-to-noise ratio greater than 3 and detected at a frequency greater than 20% in all single cells were used in subsequent analysis. Among these signals, 162 matched annotations in the HMDB database through MS spectra. The annotated metabolites underwent further scrutiny via MS/MS, resulting in confirmation of 83 metabolites that were subsequently employed for pathway enrichment analysis."
> — Results / Integration of live-cell imaging and SCMS · bears on: Axis A (modality depth), Claim 10 (identification trade-off) · quantifies how many single-cell metabolite features survive QC and confident MS/MS identification.

> "Among the whole metabolome, we observed a total of 254 metabolites significantly correlated with OS level (P < 0.05). The majority (61.4%) of the metabolites correlated with OS level (P < 0.05) exhibited an inverse correlation, which is nearly double the number of metabolites that showed a positive correlation with cellular OS."
> — Results / SCLIMS reveals correlation between metabolism and oxidative levels · bears on: Claim 5, Axis A · quantifies metabolome–phenotype coupling at single-cell level.

> "We then performed a pseudotime analysis using single-cell metabolomics data and generated a trajectory of the six subtypes... These findings suggest a metabolism-guided stepwise progression of cellular OS."
> — Results / Cell types identified by the SCLIMS · bears on: Axis B (temporal), Claim 3 · temporal ordering is INFERRED via pseudotime from a snapshot, not measured as a real time course (destructive assay).

> "We employed discriminant analysis algorithms to train classification models using single-cell metabolic features... no variable selection is performed before the model was trained... In multiclassification, the ROC curve had an average area under curve (AUC) of 0.98... the model achieved an accuracy ranging from 77.8% to 100%... These results demonstrate that the single-cell metabolic profiles can directly predict metabolic subtypes."
> — Results / SCLIMS reveals capability of the single-cell metabolome in predicting cellular OS status · bears on: Claim 5, Claim 4, Claim 1 · metabolome alone predicts phenotypic subtype with high accuracy.

> "The model was trained on the training dataset to predict single-cell OS levels, as manifested by DCFDA intensity, based on single-cell metabolic features... The correlation coefficient (r) was 0.88, indicating a good predictive power of the model."
> — Results / SCLIMS reveals capability... · bears on: Claim 5, Axis A · metabolome regresses onto a continuous phenotypic (oxidative) state.

> "we have successfully demonstrated a link between single-cell metabolome and cellular OS states in two different cell types for the very first time, suggesting the potential role of metabolome in determining cellular phenotype."
> — Results / SCLIMS reveals capability... · bears on: Claim 5, Claim 4 · explicit claim that metabolome modality determines phenotype.

> "We surprisingly found that while there was minimal heterogeneity in cellular OS levels among the initial cells... there existed heterogeneity in their single-cell metabolome."
> — Results / SCLIMS unveils the causal relationship between metabolic heterogeneity and OS status · bears on: Claim 4, Claim 5 · metabolome resolves heterogeneity invisible to the phenotypic (OS) readout — i.e. orthogonal/non-substitutable information.

> "this metabolic diversity in initial cells mirrored that observed in cells with varying OS levels, suggesting that it may be the root cause of heterogeneous OS levels within cells."
> — Results / SCLIMS unveils the causal relationship... · bears on: Claim 5, Axis B · baseline metabolome causally precedes (predicts) later phenotypic divergence.

> "To isolate the MROR and MROS cells, we employed a live-cell GSH fluorescent dye (monochlorobimane, mClB) and fluorescence activated cell sorting (FACS)... the data from the SCLIMS suggest that the metabolic features of an initial cell may dictate its destiny under OS and OS-induced senescence."
> — Results / The metabolic heterogeneity of cells determines their senescence fate under OS · bears on: Claim 3 (destructive measurement workaround), Claim 5 · because MS is destructive, a LIVE proxy (GSH dye) had to substitute for the metabolome to track the same cells' fate.

> "Another possibility may be attributed to differences in cellular contact, micro-environmental development, or potential transport of certain metabolites between neighboring cells that has gone undetected."
> — Discussion (ref 86) · bears on: Claim 7 (spatial microenvironment / neighborhood effect), Axis C · authors speculate neighbor-to-neighbor metabolite exchange / microenvironment as a source of single-cell metabolic heterogeneity.

> "previous studies on cellular metabolism have predominantly been performed at the homogenate level, potentially disregarding the metabolic heterogeneity and intricate metabolic changes of individual cells."
> — Discussion · bears on: Claim 10, Axis A · restates that bulk averaging discards single-cell metabolic information.

> "the identification of metabolites at the single-cell level poses a significant challenge due to the complexity of MS/MS analysis. Acquiring MS/MS spectra for hundreds of m/z in the metabolome is indeed arduous."
> — Discussion / limitations · bears on: Claim 10 (resolution × throughput × identification trade-off) · author-conceded limitation of single-cell metabolite identification.

> "the SCLIMS utilized in this current study was meticulously designed to incorporate cultured cells and cellular models of OS. The versatility of SCLIMS extends to tissue-embedded cells... However, the potential application of SCLIMS in tissue-embedded cells remains an intriguing area for future exploration and investigation."
> — Discussion / limitations · bears on: Axis C (spatial), Claim 2 · concedes the method currently operates on dissociated/cultured cells; tissue (spatial-context) application is unrealized future work.

> "one must acknowledge the challenges associated with analyzing fixed cells when employing the SCLIMS technique."
> — Discussion / limitations · bears on: Claim 10, Claim 8 · conceded difficulty integrating with fixed-cell phenotypic assays.

> "The cells were patched with a high-quality seal (>1 GΩ) and the cell membrane was disrupted by rapid application of negative pressure. Mild negative pressure was then applied to the pipette to obtain cytoplasmic chemical constituents, which were subsequently analyzed using mass spectrometry after removal of the pipette from the bath solution."
> — Methods / The workflow and experimental setting of SCLIMS · bears on: Claim 3, Claim 10 · the measurement is destructive (membrane disrupted, cytoplasm aspirated) — one cell, one terminal readout.

> "Subsequently, the cells were captured using a fluorescent microscope to record their spatial distribution."
> — Methods / The workflow and experimental setting of SCLIMS · bears on: Axis C (spatial) · spatial position is recorded only to pair imaging with the sampled cell, not as spatial-omics / tissue context.

---

## Claim Touchpoints (router)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 4 — modalities orthogonal / non-substitutable | "minimal heterogeneity in cellular OS levels... there existed heterogeneity in their single-cell metabolome" / §causal relationship | supports |
| Claim 5 — protein/metabolism indispensable for function & phenotype | "the pre-existing metabolomic heterogeneity determines the divergent cellular fate" / Abstract; "metabolic features of an initial cell may dictate its destiny" / §fate | supports |
| Claim 8 — multimodalities need integration | "integrating single-cell omics with cellular function or phenotype" / §Introduction; "remains a formidable technical challenge" / §Introduction | supports |
| Axis A — modality (metabolome at single-cell) | "pioneered the development of cutting-edge single-cell mass spectrometry techniques" / §Introduction; "83 metabolites... confirmed... by MS/MS" / §Results | supports |
| Claim 1 — metabolome can predict phenotype (ML) | "average area under curve (AUC) of 0.98"; "correlation coefficient (r) was 0.88" / §predicting cellular OS status | supports |
| Claim 3 — destructive measurement cannot pair-observe over time | "membrane was disrupted... to obtain cytoplasmic chemical constituents" / §Methods SCLIMS; "live-cell GSH fluorescent dye... and FACS" / §fate | supports (premise) |
| Axis B — temporal | "pseudotime analysis... generated a trajectory"; "metabolism-guided stepwise progression" / §Cell types identified | nuances (inferred, not real time course) |
| Claim 7 — spatial microenvironment / neighborhood effect | "transport of certain metabolites between neighboring cells" / §Discussion | nuances (speculative) |
| Axis C — spatial | "designed to incorporate cultured cells... tissue-embedded cells remains... future exploration" / §Discussion; "record their spatial distribution" / §Methods | challenges (dissociated; spatial deferred) |
| Claim 10 — resolution × throughput × destructiveness trilemma | "identification of metabolites at the single-cell level poses a significant challenge"; "homogenate level... disregarding the metabolic heterogeneity" / §Discussion | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | SCLIMS workflow: DCFDA imaging → patch-clamp single-cell sampling → SCMS; PCA/UMAP/t-SNE show no metabolome difference between DCFDA-incubated (n=257) and non-incubated (n=325) cells; metabolite–metabolite correlation heatmaps preserved. |
| Fig. 2 | Single-cell metabolome vs OS correlation: 254 metabolites significantly correlated with OS (P<0.05), 61.4% inverse; ATP, PCr, UTP, GTP, hypotaurine, and single-cell energy charge decline with OS; MSEA of inversely-correlated metabolites (n=190 cells). |
| Fig. 3 | k-medoids clustering → six metabolic subtypes (C1–C6; n=55,34,14,41,29,17) with distinct OS levels (one-way ANOVA P=4.57e−5); pseudotime trajectory C1→C2/3, C4, C5/6; subtype marker-metabolite heatmap; C1 vs C6 MSEA (148 down / 64 up). |
| Fig. 4 | Machine learning on full single-cell metabolome (2:1 train/test, no feature selection): classification average AUC 0.98, accuracy 77.8–100%; regression of OS level r=0.88 (P=1.45e−20, n=61 test). |
| Fig. 5 | Initial (pre-OS) cells: minimal OS heterogeneity but two metabolic subtypes (Cluster-I n=43, Cluster-II n=183; Wilcox W=58627, P<2.2e−16 for DCFDA over 1740 initial vs 960 OS cells); GSH/ATP/hypotaurine 82%/42%/87% lower in Cluster-II; GSH most-rewired metabolite (DyNet); GSH correlated with 15 metabolites in Cluster-I vs 5 in Cluster-II. |
| Fig. 6 | GSH live-dye + FACS isolates top/bottom 5% (MROR vs MROS); only 3% DCFDA difference at baseline but 2.7-fold higher OS in MROS after induction (two-way ANOVA P=0.0262); SA-β-Gal confirms MROS senescence sensitivity (P=0.0163). |
| Fig. 7 | Hypotaurine (1 mM) + phosphocreatine (0.5 mM) + O-phosphoethanolamine (40 µM): ~67% OS reduction (DCFDA), ~48% SA-β-Gal reduction, growth-arrest rescue, mitochondrial membrane potential (TMRE) recovery. |
| Fig. 8 | C. elegans: three metabolites extend lifespan ~33–50% (log-rank P<2.2e−16); DHE OS reduced ~16%; thrashing rescued (elderly worms had 43% decline); free-moving speed 1.4–1.8× higher at Day 9. |
| MEFs (Supp. Figs. 3,6,9,10,14) | All key HEK293T findings replicated in MEFs (six subtypes M1–M6; classification AUC 0.99, accuracy 88.42%; regression r=0.6, P<0.0001; metabolite rescue). |

---

## Primary Sources Behind Key Quotes
- Metabolism as reflection AND regulator of cell function → Ghosh-Choudhary, S., Liu, J. & Finkel, T., Trends Cell Biol. 30:201–212 (2020), ref 15.
- Own-lab single-cell MS metabolomics technique → Zhu, H. et al., PNAS 114:2586–2591 (2017), ref 17; Zhu, H. et al., Cell 173:1716–1727 (2018), ref 18.
- Cross-modality exemplar (Patch-seq, transcriptome + electrophysiology) → Camunas-Soler, J. et al., Cell Metab. 31:1017–1031 (2020), ref 11.
- Cross-modality exemplar (CITE-seq, epitope + transcriptome) → Stoeckius, M. et al., Nat. Methods 14:865–868 (2017), ref 9; Peterson, V. M. et al., Nat. Biotechnol. 35:936–939 (2017), ref 10.
- Multi-omics + immune-cell function (COVID) → Lee, J. W. et al., Nat. Biotechnol. 40:110–120 (2022), ref 13.
- Temporal multi-omics (EV lipidomics + proteomics) → Lam, S. M. et al., Nat. Metab. 3:909–922 (2021), ref 12.
- Spatial multimodal transcriptomes + metabolomes in tissues → Vicari, M. et al., Nat. Biotechnol. 42:1046–1050 (2024), ref 73. [high value for Axis C + Axis A integration]
- Integration of spatial and single-cell data across modalities → Chen, S. et al., Nat. Biotechnol. 42:1096–1106 (2024), ref 74. [high value for Axis C + standard/integration]
- Cell–cell metabolite exchange / microenvironment extends lifespan → Correia-Melo, C. et al., Cell 186:63–79 (2023), ref 86. [Claim 7]

---

## Flags
- [ ] Metadata unverified: exact Nature Communications volume / article number not printed in the cleaned body; only DOI (10.1038/s41467-025-57992-3) and "© The Author(s) 2025" are in-text. Year (2025) and venue confirmed from text (Additional information / supplementary DOI line and peer-review note naming "Nature Communications").
- [ ] Read at source: refs 73 (Vicari, spatial transcriptomes + metabolomes) and 74 (Chen, spatial + single-cell integration) are first-hand sources for our spatial-multimodal and integration claims (Axis C / Claim 8) — read directly rather than via this paper.
- [ ] Read at source: ref 86 (Correia-Melo, cell–cell metabolite exchange) for Claim 7 (microenvironment/neighborhood effects) — cited here only as a speculative aside.
- [ ] Scope note: most of the paper (oxidative-stress/senescence biology, specific metabolite mechanisms, C. elegans lifespan) is out-of-scope disease/biology detail per the context file; captured only the lines bearing on data-foundation claims (modality, temporal, spatial, resolution/destructiveness, integration). The metabolite-rescue and lifespan results are recorded in the Numbers table as factual context, not as roadmap evidence.
- [ ] Ligature/OCR artifacts (e.g. "pro<sup>fi</sup>ling", "<sup>fl</sup>uorescent") in the cleaned source were normalized to plain text ("profiling", "fluorescent") inside quotes; wording and all numbers are otherwise verbatim.
