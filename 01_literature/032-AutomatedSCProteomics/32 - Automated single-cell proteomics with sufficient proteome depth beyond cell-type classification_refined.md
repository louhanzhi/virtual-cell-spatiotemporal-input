# Automated single-cell proteomics providing sufficient proteome depth to study complex biology beyond cell type classifications — Source Index

**Authors:** Claudia Ctortecka, Natalie M. Clark, Brian W. Boyle, Anjali Seth, D. R. Mani, Namrata D. Udeshi & Steven A. Carr
**Journal / Venue:** Nature Communications, 2024 (article number unverified; see Flags)
**DOI:** doi:10.1038/s41467-024-49651-w
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/32 - Automated single-cell proteomics with sufficient proteome depth beyond cell-type classification_cleaned.md

---

## In One Sentence
A mass-spectrometry (MS)-based single-cell proteomics (SCP) methods paper presenting a fully automated, label-free workflow (proteoCHIP EVO 96 + Evosep One + Bruker timsTOF Ultra) that quantifies up to 4000 (average ~3500) protein groups per single HEK-293T cell without a carrier or match-between-runs, and applies it to detect LPS-induced proteome changes in single THP-1 cells.

## Orientation (non-binding)
Primarily ammunition for the **modality axis (A) / protein** and for **claim 6 (high-throughput proteomics now feasible/deep at single-cell scale)** and **claim 10 (throughput × depth × input-amount trade-off)**: it documents that single-cell *proteome* depth has reached thousands of proteins, and quantifies the cost of pushing throughput. It also argues the protein modality measures *function/identity* "beyond cell-type classifications" — a foil to RNA-only, classification-oriented scRNA paradigms (claim 5). Note it can ALSO serve as a foil for the temporal/spatial axes: the method is destructive (cells lysed/digested) and dissociated, i.e. it adds the protein modality while still producing space- and time-blind snapshots; two of its cited primary sources (spatial proteome zonation; an LPS time-course bulk study) are leads for the spatial/temporal axes. Downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "Mass spectrometry (MS)-based proteomics is ideally suited to study cellular identity and functionality as those are mostly driven by proteins or their post-translational modifications (PTMs)."
> — Introduction · bears on: claim 4, claim 5, Axis A (modality/protein, PTM) · asserts identity/function are protein-driven, motivating the protein modality.

> "In the past few years, single-cell proteomics (SCP) has developed into a viable complement to other sequencing-based omics techniques."
> — Introduction · bears on: claim 4, claim 8, Axis A · frames proteomics as a complement to sequencing-based omics.

> "Currently, most single-cell approaches aim at resolving biological heterogeneity by describing diverse sub-populations or unexpected cell types within a given sample."
> — Introduction · bears on: claim 1, claim 5 · characterizes prevailing single-cell use as cell-type/sub-population description.

> "This study demonstrates that the proteoCHIP EVO 96-based sample preparation with the timsTOF Ultra provides sufficient proteome depth to study complex biology beyond cell-type classifications."
> — Abstract · bears on: claim 5, claim 6, Axis A · claims protein-level depth enables biology beyond cell-type classification.

> "the newest generation timsTOF Ultra identifies up to 4000 with an average of 3500 protein groups per single HEK-293T without a carrier or match-between runs."
> — Abstract · bears on: claim 6, Axis A · headline single-cell proteome depth figure.

> "Until recently, the limited protein content of most mammalian cells, which is only about 50–300 pg, represented a significant challenge to MS-based SCP. Even though this is over 1000 times lower than standard input of current MS-based proteomics studies, the latest advances in dedicated workflows and liquid chromatography tandem mass spectrometry (LC-MS/MS) instrumentation have begun to overcome these sensitivity limitations."
> — Introduction · bears on: claim 6, claim 10, Axis A · states the low-input sensitivity barrier (50–300 pg) and that it is now being overcome.

> "stochastic precursor selection in DDA results in missing data when analyzing large numbers of single cells in multiple TMT plexes."
> — Introduction · bears on: claim 9 · names a source of missing data / incompleteness in SCP acquisition.

> "While label-free quantification of individual cells does not suffer from interferences related to isobaric labeling, measurement throughput is significantly decreased."
> — Introduction · bears on: claim 10 · states a label-free vs throughput trade-off.

> "The manually transferred samples yielded a median of 582 protein groups per analytical run, while the direct loading of the Evotips resulted in a median of 812 proteins per single cell. This indicated that automated transfer of the sample increased protein groups by 29% in comparison to the manually pipetted ones."
> — Results (proteoCHIP EVO 96 minimizes adsorptive peptide losses) · bears on: claim 9 · sample-handling reproducibility quantitatively changes identifications.

> "Using the modified diaPASEF acquisition method, together with the 40SPD method, we identified 3000 proteins per single HEK-293T cell ... recovered about 2-fold more proteins and increased sample throughput by 30% in contrast to the 30-min effective gradient on the nanoElute."
> — Results (Fig. 1) · bears on: claim 6, claim 10, Axis A · depth and throughput gains from the optimized workflow.

> "the identification of over 3500 proteins per single cell with the 40SPD method, which is 15% higher compared to single cells acquired on the timsTOF SCP."
> — Results (Doubling throughput still yields 3500 proteins) · bears on: claim 6, Axis A · instrument-driven depth figure.

> "For our comparative studies, we combine only single cells without the usage of a carrier sample for data analysis to eliminate the possibility of identification transfer without controlling the false discovery rate across the entire dataset."
> — Results (Doubling throughput) · bears on: claim 9 · methodological choice to avoid FDR-uncontrolled identification transfer.

> "with the short 80SPD separation method, the median number of proteins identified decreased to 1200 per single cell, representing a drop of ~60% compared to 40SPD."
> — Results (Doubling throughput) · bears on: claim 10 · quantifies depth lost when throughput is doubled.

> "The increased throughput using the 80SPD separation method reduced the dynamic range of single-cell analysis by one order of magnitude."
> — Results (Doubling throughput) · bears on: claim 10 · throughput cost on dynamic range.

> "using the 40SPD method, we identify over 50 E3 ubiquitin-protein ligases in single cells while 13 are recovered using the 80SPD method ... the rank order of abundance remained the same between the two methods."
> — Results (Doubling throughput, Fig. 2c) · bears on: claim 5, claim 10 · depth determines whether low-abundance functional proteins are recovered; relative quantitation preserved.

> "This demonstrates that 2-fold higher single-cell analysis throughput is feasible, at decreased analysis depth. Therefore, the experimental design must take into consideration whether the acquisition of hundreds or thousands of single cells are required for statistical significance and if the proteins of interest can still be reliably quantified to address a specific biological question."
> — Results (Doubling throughput) · bears on: claim 10 · explicit articulation of the throughput-vs-depth design trade-off.

> "We identified up to 1537 protein groups with a median of 1149 protein groups per single cell ... The nominal decrease in identifications per single cell compared to the HEK-293T cells ... suggests that this is due to the 2-fold decreased cell size."
> — Results (LPS-induced proteome changes) · bears on: claim 10, Axis A · proteome depth scales with cell size / protein input.

> "Compared to bulk data, SCP datasets exhibit distinct considerations for normalization, due to technical variability throughout the sample processing, or differences in cell size (Supplementary Fig. 3; HEK-293T – 26.7 µm, THP-1 – 13.7 µm)."
> — Results (LPS) · bears on: claim 9 · SCP needs distinct normalization; technical variability and cell-size confounds.

> "we normalized our SCP data using SCnorm, which is an approach originally developed for single-cell transcriptomics studies."
> — Results (LPS) / Methods · bears on: claim 8, claim 9 · cross-modal transfer of a transcriptomics normalization method into proteomics.

> "approximately 9.28% of the variance can be explained by this batch effect. We therefore batch-corrected our data using the limma package ... to reduce this technical variability while conserving biological effects."
> — Results (LPS) · bears on: claim 9 · quantifies and corrects technical batch variance.

> "We identified 214 proteins as significantly upregulated in the LPS-treated cells while 15 were significantly downregulated compared to the DMSO vehicle control."
> — Results (LPS, Fig. 3d) · bears on: claim 5 · single-cell proteomics resolves a perturbation response at the protein level.

> "Mulvey and co-authors profiled the effects of LPS treatment across a 24-hour time course and identified 4882 proteins. We found 26% of those quantified proteins also in our single cell THP-1 dataset, while the bulk study identified 3009 additional proteins."
> — Results (LPS) · bears on: claim 10, Axis B · bulk depth (4882) vs single-cell coverage (26% overlap); references a temporal (time-course) proteomics study.

> "This and the regulation of other key LPS response proteins corroborates previous findings that even though fold changes between bulk and single cell proteomics datasets do not scale, the biological regulation correlates."
> — Results (LPS) · bears on: claim 9, claim 10 · bulk and single-cell proteomics are concordant in regulation direction but not in absolute fold-change magnitude.

> "We demonstrate that including a single manual sample transfer step reduces protein identifications by 29%, and those losses are increased to over 49% when a standard HPLC vial is used for sample injection compared to the Evotip."
> — Discussion · bears on: claim 9 · reproducibility/recovery is highly sensitive to handling at single-cell input.

> "shorter chromatographic gradients directly scale with decreased sensitivity, which retrospectively might impact the ability to make biologically relevant conclusions. We demonstrate that protein identifications are reduced by close to 60% when decreasing the gradient length by 50%. This additionally reduces the overall protein abundance and decreases detection limits by an order of magnitude."
> — Discussion · bears on: claim 10 · throughput-depth-sensitivity trade-off restated with numbers.

> "single HEK-293T cells acquired on the timsTOF Ultra with the 40SPD chromatographic separation yield up to 4000 protein groups and on average 3500 protein groups spanning 4 orders of magnitude in abundance. This allows us to confidently quantify biologically relevant proteins, such as over 50 E3 ubiquitin-protein ligases."
> — Discussion · bears on: claim 5, claim 6, Axis A · depth + dynamic range claim tied to functional protein coverage.

> "along with sample preparation capabilities and instrument sensitivity, the cell size highly impacts proteome depth."
> — Discussion · bears on: claim 10, Axis A · proteome depth is input-amount-limited.

> "data analysis across all samples has been performed with a publicly available pan-human library, overcoming the need to generate an experiment-specific library for every project. We consider this specifically important in the analysis of unknown sub-populations or cell-types, which might not be accurately reflected in dedicated libraries."
> — Discussion · bears on: claim 9 · use of a shared/standardized reference library rather than per-experiment libraries.

> "the analysis of single cells in combination with higher input samples might impact identification accuracy due to the lack of false discovery rate filtering post-match between runs. In this case, identifications are heavily influenced by the representation of sub-populations within higher input samples."
> — Discussion · bears on: claim 9 · conceded accuracy caveat when mixing single cells with higher-input samples.

> "Deep proteomics data acquisition and analysis with high reproducibility was obtained by directly connecting efficient and reproducible chromatography with dedicated MS instrument acquisition parameters and single-cell normalization approaches."
> — Discussion (conclusion) · bears on: claim 6, claim 9 · positions reproducibility + depth as the joint achievement.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 (data is bottleneck; classification-oriented use) | "most single-cell approaches aim at resolving... sub-populations or unexpected cell types" / Intro | nuances |
| Claim 4 (modalities orthogonal / non-substitutable) | "proteomics is ideally suited to study cellular identity and functionality as those are mostly driven by proteins" / Intro | supports |
| Claim 5 (protein/non-RNA modalities indispensable to function & phenotype) | "sufficient proteome depth to study complex biology beyond cell-type classifications" / Abstract; "214 proteins... significantly upregulated" / Results | supports |
| Claim 6 (high-throughput proteomics feasible at single-cell scale) | "up to 4000... average of 3500 protein groups per single HEK-293T" / Abstract & Discussion | supports |
| Claim 8 (multi-modal complementarity / integration) | "SCP has developed into a viable complement to other sequencing-based omics"; "SCnorm... originally developed for single-cell transcriptomics" / Intro & Results | supports |
| Claim 9 (data islands / comparability / standards / QC) | "missing data when analyzing large numbers of single cells"; "29%... 49%" handling loss; "pan-human library"; batch effect 9.28% / Intro, Results, Discussion | supports / nuances |
| Claim 10 (resolution × throughput × destructiveness trilemma) | "decreased to 1200... drop of ~60%"; "reduced the dynamic range... by one order of magnitude"; "cell size highly impacts proteome depth" / Results & Discussion | supports |
| Axis A · modality (protein, PTM) | protein-driven identity/function; depth figures; E3 ligase coverage / throughout | supports |
| Axis B · temporal | method is destructive snapshot; cites bulk "24-hour time course" (Mulvey) / Results | challenges (foil) / lead |
| Axis C · spatial | dissociated single cells, no spatial context; cites spatial proteome zonation (ref 5) / Intro | challenges (foil) / lead |
| Standard / integration | reproducibility, shared library, single-cell normalization & batch correction / Discussion | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Direct (Evotip/Evosep) vs manual (HPLC vial/nanoElute) sample transfer. Manual median 582 vs direct 812 protein groups (+29%); 99% unique-peptide overlap; nanoElute 1547 vs 40SPD diaPASEF 3000 proteins/cell; 12% greater data completeness for Evosep; ~5 orders of magnitude dynamic range. |
| Fig. 2 | timsTOF Ultra 40SPD vs 80SPD on HEK-293T (n=48 each). 40SPD ~3500 vs 80SPD median 1200 proteins/cell (~60% drop); dynamic range reduced by one order of magnitude; 51 E3 ubiquitin-protein ligases ranked, 50+ at 40SPD / 13 at 80SPD; proteins with MS1 abundance <1e3 in 40SPD drop below detection at 80SPD. |
| Fig. 3 | THP-1 + LPS (200 ng/mL, 12 h, n=77/84) vs DMSO control, 40SPD timsTOF Ultra. Median 1149 (up to 1537) protein groups/cell; PCA PC1 75.8% / PC2 6.8%; 214 up / 15 down (adj. p ≤ 0.05, 229 significant); GSEA Reactome: Interferon, Interleukin (IL-12 family) signaling enriched. |
| Supplementary Fig. 6 | Comparison to bulk THP-1 LPS study (Mulvey, ref 57): bulk 4882 proteins, 26% overlap with single-cell set, 3009 bulk-only; concordant fold-change direction for CD44, DDX21, etc. |
| Cell-size note | HEK-293T 26.7 µm vs THP-1 13.7 µm; batch effect explains ~9.28% of variance. |

---

## Primary Sources Behind Key Quotes
- Spatial single-cell mass-spectrometry proteome zonation (lead for spatial axis) → Rosenberger, F. A. et al. "Spatial single-cell mass spectrometry defines zonation of the hepatocyte proteome." Nat. Methods 20, 1530–1536 (2023) — ref 5.
- Bulk LPS time-course proteomics in THP-1 (lead for temporal axis; the bulk comparator) → Mulvey, C. M. et al. "Spatiotemporal proteomic profiling of the proinflammatory response to lipopolysaccharide in the THP-1 human leukaemia cell line." Nat. Commun. 12, 5773 (2021) — ref 57.
- Bulk vs single-cell fold-changes do not scale but regulation correlates → Specht, H. et al. "Single-cell proteomic and transcriptomic analysis of macrophage heterogeneity using SCoPE2." Genome Biol. 22, 50 (2021) — ref 17.
- Low mammalian-cell protein content (50–300 pg) baseline → Wiśniewski, J. R., Hein, M. Y., Cox, J. & Mann, M. "A 'Proteomic Ruler'..." Mol. Cell Proteom. 13, 3497–3506 (2014) — ref 14.
- SCnorm normalization (transcriptomics method reused for proteomics) → Bacher, R. et al. "SCnorm: robust normalization of single-cell RNA-seq data." Nat. Methods 14, 584–586 (2017) — ref 62.

---

## Flags
- [ ] Metadata unverified: Journal confirmed as Nature Communications (2024) and DOI 10.1038/s41467-024-49651-w from the article text/Additional information; exact article number, volume, and page/article-number are not printed in the cleaned text — listed as unverified.
- [ ] Metadata not found: Received / accepted / first-published dates are not present in the cleaned source; only "© The Author(s) 2024" is stated.
- [ ] Scope note: This paper is an MS-based proteomics METHODS paper; instrument/sample-prep specifics (hexadecane, master-mix recipes, Evotip handling, gradient programs) were deliberately NOT captured as off-roadmap. Captured lines are limited to those bearing on the context-file claims (modality/protein, depth-feasibility, throughput-depth trade-off, comparability/standards).
- [ ] Direction caveat: This work supports the protein-modality and proteomics-feasibility claims, but it is itself a dissociated, destructive (cells lysed/digested) single-cell snapshot with no spatial or temporal-trajectory readout — usable by the downstream agent BOTH as evidence proteomics is ready AND as an instance of the space/time-blind paradigm the thesis critiques. Do not sanitize into all-support.
- [ ] Read at source: Rosenberger 2023 (ref 5, spatial proteome zonation) and Mulvey 2021 (ref 57, spatiotemporal/time-course bulk proteomics) are worth reading first-hand for the spatial and temporal axes rather than via this paper.
