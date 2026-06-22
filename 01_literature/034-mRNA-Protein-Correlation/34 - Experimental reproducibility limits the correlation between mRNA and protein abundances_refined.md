# Experimental reproducibility limits the correlation between mRNA and protein abundances in tumor proteomic profiles — Source Index

**Authors:** Swathi Ramachandra Upadhya, Colm J. Ryan (School of Computer Science & Systems Biology Ireland, University College Dublin, Dublin, Ireland)
**Journal / Venue:** Cell Reports Methods, 2022, article 100288 (venue name inferred from DOI prefix "crmeth"; not printed verbatim in text — see Flags)
**DOI:** doi:10.1016/j.crmeth.2022.100288
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/34 - Experimental reproducibility limits the correlation between mRNA and protein abundances_cleaned.md

---

## In One Sentence
By analyzing tumor and cell-line datasets that contain replicate proteomic (and transcriptomic) profiles, the paper shows that a large share of the moderate mRNA–protein correlation gap is driven by measurement reproducibility (technical noise) rather than only post-transcriptional biology, builds an aggregate protein-reproducibility rank that explains 10–20% of the variation in mRNA–protein correlation across 13 proteogenomic studies, and argues that some pathways (e.g., metabolic) previously credited with high mRNA–protein correlation may simply be more reproducibly measured.

## Orientation (non-binding)
Sits squarely on **Claim 4** (modalities are non-substitutable / RNA is a poor proxy for protein) and on **Claim 9 / the "standard" axis** (cross-study results are not comparable without standardization; QC/reproducibility is unstandardized). It can serve as **BOTH support and foil**: it supports "mRNA is only a moderate proxy for protein" and "proteomic data is RNA-centric, protein-poor, noisy, and cross-study incomparable," yet it also argues — as a foil to a naive reading of Claim 4 — that much of the apparent mRNA–protein decoupling is *technical measurement error*, not biology, and that error-corrected estimates raise the true agreement. Also feeds Claim 1 (data quality caps data-driven protein prediction), Claim 6 (protein measurement is hard / improving), and Claim 10 (platform/method trade-offs: label-free vs TMT, DDA vs DIA). The downstream agent decides how to deploy this tension.

---

## Load-Bearing Excerpts

> "Because they are easier to measure in high throughput, mRNA abundances are often used as a proxy measurement for protein abundances. However, there is only a moderate correlation between the two, and it is unclear to what extent this moderate correlation reflects post-transcriptional regulation and to what extent it can be attributed to measurement error."
> — Motivation · bears on: Claim 4, Axis A (modality) · frames mRNA as an imperfect proxy for protein and asks whether the gap is biology or noise.

> "However, our ability to quantify protein abundances at scale has lagged behind our ability to sequence genomes and quantify mRNA abundances. Large-scale efforts to molecularly characterize healthy and disease samples from humans have therefore primarily focused on DNA sequence variation and transcriptomic variation."
> — Introduction · bears on: Claim 4, Axis A (protein neglected) · explains why existing data is RNA-centric and protein-poor.

> "the relationship between mRNA abundances and protein abundances is complex and non-linear and varies significantly from protein to protein. Consistent with this, largescale studies in humans and model organisms have revealed that for most genes there is only a moderate correlation between mRNA and protein abundances"
> — Introduction · bears on: Claim 4 · RNA does not predict protein well for most genes.

> "These studies have reported an average mRNA-protein correlation in the range of 0.2–0.5 ... Major biological factors that influence mRNA-protein correlation include translation rates that vary across proteins and conditions, highly variable halflives for both proteins and mRNAs, and post-translational modifications that can alter protein stability and degradation"
> — Introduction · bears on: Claim 4, Axis A (PTM / protein state) · quantifies the weak link in tumors and lists the biological reasons RNA fails to capture protein.

> "subunits of large protein complexes have been shown to have lower-than-average mRNA-protein correlations, suggesting significant post-transcriptional regulation"
> — Introduction · bears on: Claim 4, Axis A (complexes / interactome) · post-transcriptional regulation decouples RNA from protein for complex members.

> "throughout when we discuss mRNA-protein correlations, we are calculating the correlation between the protein and transcript abundance for an individual protein across samples."
> — Introduction · bears on: Claim 9, standard axis · the same term ("mRNA–protein correlation") is computed two incompatible ways across the literature.

> "However, it is not meaningful to directly compare the reported correlations because the methods used to quantify the mRNA-protein correlation have varied across studies—different studies have used different summary statistics (mean versus median), different correlation metrics (Pearson versus Spearman), and different criteria for protein inclusion (e.g., no missing values, at least 30% measured values, only the 10% most variable proteins)"
> — Results, "A standardized pipeline reveals differences…" · bears on: Claim 9, standard axis · cross-study reported numbers are not directly comparable.

> "To enable a more direct comparison across studies, we calculated the mRNA-protein correlation for thirteen proteomic studies using a standardized pipeline. ... Within each study, we calculated the median Spearman correlation between mRNA and protein for all proteins that were measured in at least 80% of samples"
> — Results · bears on: Claim 9, standard axis · a standardized pipeline is required to make 13 datasets comparable.

> "the recalculated correlation for colon cancer was much lower than that reported by the authors (0.27 versus 0.48) ... This is because the colon cancer study reported the mean mRNA-protein correlation for only the 10% most variable proteins rather than the full set of proteins. These highly variable proteins have higher than average mRNA-protein correlations."
> — Results · bears on: Claim 9, standard axis · protein-inclusion criteria alone can swing a reported correlation by ~0.2.

> "we observe a mean of 0.49 for studies published after 2019 versus 0.35 for studies published in 2016 or earlier ... improvements in either technology or experimental protocols have resulted in improved mRNA-protein correlations over time."
> — Results · bears on: Claim 6, Claim 1 · technical/experimental improvement raises apparent data quality over time.

> "for ovarian cancer, the same tumor sample was profiled in two different laboratories, for the cancer cell lines, biological replicates were performed within the same lab 1 year apart, while for colon cancer, the same tumor samples were profiled with two different mass spectrometry (MS) techniques, i.e., isotopebased protein quantification (TMT-10) and label-free spectral counting MS."
> — Results, "The correlation across replicate proteomic profiles…" · bears on: Claim 9, Claim 10, standard axis · replicate design spans labs, sites, and platforms.

> "The median protein-protein reproducibility for the replicate proteomic profiles from the CCLE dataset was 0.72 ... ovarian tumors was 0.57 ... The replicate protein-protein reproducibility for the colon study (median 0.28) was much lower ... Overall, we can conclude that although protein-protein reproducibility is consistently higher than mRNA-protein correlations, the protein-protein reproducibility is still only moderate."
> — Results · bears on: Claim 6, Claim 9, Axis A · even repeat protein measurements of the same sample agree only moderately (0.28–0.72).

> "One reason for the colon study to have a low median protein-protein reproducibility is that one of the two replicate proteomic profiles is quantified using label-free/spectral counting MS, which is not as accurate as the stable isotope-based protein quantification methods"
> — Results · bears on: Claim 10, Claim 9 · the choice of quantification method materially changes data quality and comparability.

> "We found, for all three studies, that the median mRNAprotein correlation increases with protein-protein reproducibility ... The colon cancer study shows a difference in the median mRNA-protein correlation of 0.33 between the first and last deciles of protein reproducibility. Similarly, ovarian cancer data show a difference of 0.35, and the CCLE data show a difference of 0.37."
> — Results, "Proteins with higher reproducibility…" · bears on: Claim 4 (nuance/foil), Claim 9 · measurement reproducibility, not only biology, drives the weak mRNA–protein link.

> "This suggests that noise in the quantification of protein abundances explains much more (on average 3 times) of the variance in mRNA-protein correlation than the most predictive previously identified factor."
> — Results · bears on: Claim 4 (foil), Claim 9 · reframes apparent biological decoupling as substantially technical; reproducibility explains ~3× the variance of protein-complex membership.

> "In general, proteins that are highly reproducible in one study tend to be highly reproducible in others, while proteins that show poor reproducibility in one study tend to show poor reproducibility in others"
> — Results, "Proteins with high reproducibility in one study…" · bears on: Claim 9 · reproducibility is a partly platform-independent property of each protein.

> "For all these studies, we find that proteins with more reproducible measurements tend to have higher mRNA-protein correlations. Although the aggregated ranks are based on data from cancer studies, we observe the same trend in healthy tissues obtained from the GTEx project ... we observed the same trend for a study that quantified proteins using data-independent acquisition (DIA)-based proteomics (sequential window acquisition of all theoretical mass spectra [SWATH-MS]) ... irrespective of the proteomic quantification approach."
> — Results, "An integrated ranking…" · bears on: Claim 4 (nuance), Claim 9 · the reproducibility effect generalizes across health state and across DDA/DIA platforms.

> "While the lowest decile has a correlation of 0.35 between the measurements and predictions, the highest decile has a correlation of 0.7."
> — Results · bears on: Claim 1, Claim 4 · machine-learning prediction of protein from RNA is far better for reproducibly measured proteins.

> "This quantification is a stochastic process, and there is no guarantee that every peptide in a given sample will be detected by the mass spectrometer. The quantification of proteins that have low abundance, and hence fewer detectable peptides, is especially likely to be subject to substantial stochastic variation."
> — Results, "Protein measurement reproducibility is influenced by abundance…" · bears on: Claim 6, Claim 9 · bottom-up MS proteomics has fundamental sampling noise, worst for low-abundance proteins.

> "We found a clear relationship between the mean protein abundance and the aggregated protein reproducibility rank—more abundant proteins are more reproducibly measured"
> — Results · bears on: Claim 6, Claim 9 · low-abundance proteins are measured unreliably (a sensitivity/coverage limit).

> "mRNAs typically have a half-life of 2.6–7 h, while proteins have half-lives ranging from a few seconds to a few days"
> — Results · bears on: Claim 4, Axis B (temporal) · RNA and protein operate on different timescales, contributing to their decoupling.

> "We find that the median gene-wise Spearman correlation across studies was 0.75 ... this varied significantly across transcripts, ranging from 0.05 to 0.96. As with protein reproducibility, we find that transcriptomic reproducibility is influenced by both mRNA abundance and variance."
> — Results, "Transcriptomic reproducibility also contributes…" · bears on: Claim 9, Claim 1 · even RNA measurements are only moderately reproducible across separate profiling efforts.

> "These observations suggest that the reproducibility in transcriptomic and proteomic data contribute strongly and somewhat independently to the variability observed in mRNA-protein correlation."
> — Results · bears on: Claim 9, Claim 4 (nuance) · measurement error on both modalities limits cross-modal correlation.

> "the higher-thanaverage mRNA-protein correlation previously observed for metabolic pathways may simply reflect more reproducible measurements of their constituent proteins and transcripts."
> — Results, "Metabolic pathways with higher-than-average…" · bears on: Claim 4, Claim 5 (foil) · cautions that apparent modality-specific biology can be a measurement artifact.

> "we suggest that conclusions about functional groups with higher or lower mRNA-protein correlations, especially with regard to the potential role played by post-transcriptional regulation, should be made only after accounting for variation in the measurement reproducibility of their constituent proteins."
> — Discussion · bears on: Claim 9, Claim 4 (foil) · methodological caution: control for reproducibility before making biological claims.

> "We found here that proteins that are more reproducibly measured across experimental replicates are better predicted using machine-learning. This suggests that one of the factors limiting the accuracy of machine-learning methods to predict protein abundances is that the protein abundance measurements themselves are not reproducible. It may therefore be worth evaluating future methods on the subset of proteins that can be reproducibly measured."
> — Discussion · bears on: Claim 1, Claim 4 · data-driven prediction of protein from RNA is capped by the (ir)reproducibility of the training data.

> "there have been a number of attempts to predict protein abundances from transcriptomic data that have achieved modest success"
> — Discussion · bears on: Claim 1, Claim 4 · predicting protein from RNA works only modestly.

> "we have generated an aggregate protein reproducibility rank for each protein that can explain a significant amount of the variance across multiple proteogenomic studies and that may be useful for identifying those proteins that can be reliably and reproducibly measured by mass spectrometry. Such proteins may be more useful to assay in, e.g., diagnostic panels."
> — Discussion · bears on: Claim 6, Claim 9, standard axis · proposes a QC/standard resource for picking reliably measurable proteins.

> "we note also that our analyses do not reflect the best possible reproducibility of proteomic and transcriptomic measurements, but rather they reflect the reproducibility observed in existing large-scale proteogenomic datasets. Indeed, we see that more recent proteogenomic studies have higher mRNA-protein correlations, suggesting that methodological improvements are already reducing the sources of noise in these approaches."
> — Limitations · bears on: Claim 6, Claim 9 · current public-data quality is a floor, improvable through better methods/standards.

> "These include real biological variation (e.g., tumor heterogeneity resulting in two samples of the same tumor having different profiles) and technical variation (e.g., variation in sample preparation between different runs of the same sample). ... It is likely that reducing these sources of global variation, e.g., through automated sample preparation, will improve the overall reproducibility of protein measurements."
> — Limitations · bears on: Claim 9, Claim 10 · sample-prep standardization/automation as a route to comparable, higher-quality data.

> "Previous work has demonstrated that statistical modeling that integrates multiple mRNA and protein datasets and explicitly takes into account different sources of noise and error can be used to provide improved estimates of mRNA-protein correlation within samples (Csa´ rdi et al., 2015)."
> — Discussion / Limitations · bears on: Claim 4 (foil) · counter-line: error-corrected modeling can raise the apparent mRNA–protein agreement (cf. yeast result that mRNA largely determines steady-state protein after noise correction).

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data is the bottleneck; data-driven models generalize/predict poorly | "one of the factors limiting the accuracy of machine-learning methods…" / Discussion; "modest success" | supports |
| Claim 4 — modalities orthogonal / RNA can't substitute for protein | "only a moderate correlation between mRNA and protein…" (0.2–0.5) / Intro; biological factors / Intro | supports |
| Claim 4 — (foil) decoupling partly = measurement error, not biology | "noise … explains much more (on average 3 times) …" / Results; "statistical modeling … improved estimates … within samples" / Discussion | challenges |
| Claim 5 — protein/metabolism modalities indispensable for function/phenotype | "higher-than-average mRNA-protein correlation … may simply reflect more reproducible measurements" / Results | nuances |
| Claim 6 — high-throughput / high-quality proteomics feasible & improving | "protein-protein reproducibility is still only moderate" (0.28–0.72); "more recent … higher mRNA-protein correlations" | nuances |
| Claim 9 — data islands / cross-paper incomparable / no standard | "not meaningful to directly compare the reported correlations …" / Results; "standardized pipeline" | supports |
| Claim 10 — measurement trade-offs (platform/method) | "label-free … not as accurate as … stable isotope-based"; TMT vs label-free; DDA vs DIA | supports |
| Axis A — modality (protein neglected, RNA-centric data) | "our ability to quantify protein abundances at scale has lagged behind …" / Intro | supports |
| Axis B — temporal (different RNA vs protein half-lives) | "mRNAs … half-life of 2.6–7 h, while proteins … seconds to … days" / Results | nuances |
| Standard axis — QC / reproducibility / cross-lab comparability | "aggregate protein reproducibility rank … reliably and reproducibly measured" / Discussion | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 | 13 proteogenomic studies: published year, originally reported correlation, protein-inclusion criterion, and recalculated median Spearman & Pearson correlations under a standardized pipeline. Recalculated median Spearman = 0.43 overall; max 0.55 (LUAD, Gillette 2020), min 0.21 (CRC, Zhang 2014). Notable mismatch: colon recalculated 0.27 vs reported 0.48 (Vasaikar 2019). |
| Figure 1 | Histograms of protein–protein reproducibility (Spearman, per protein) across replicates in three studies; median lines: CCLE 0.72, ovarian 0.57, colon 0.28. CCLE individual-protein range 0.2–1.0; ovarian 0.6–1.0; colon 0.2–0.8. |
| Figure 2 | mRNA–protein correlation rises with protein reproducibility decile; decile-1→10 median gain: colon 0.33, ovarian 0.35, CCLE 0.37. Reproducibility explains ~14% (ovarian), 17% (CCLE), 23% (colon) of variance (R²). |
| Figure 3 | Cross-study agreement of protein reproducibility: ovarian–colon 0.38, colon–CCLE 0.31, ovarian–CCLE 0.24. Example proteins: GBP1 (consistently high), RPS29 (consistently low). |
| Figure 4 | Aggregate reproducibility rank (5,211 proteins quantified in ≥2 of 3 studies) explains 10–20% (median 14%) of mRNA–protein correlation variation across 10 additional studies; trend holds in GTEx healthy tissue (4J) and DIA/SWATH NCI-60 (4I). |
| Figure 5 | Reproducibility increases with mean protein abundance (5A), abundance variance (5B; variance alone explains 20% of reproducibility-rank variation), and number of unique peptides (5C); long-half-life proteins have higher median reproducibility (5D; p = 9.70e−25, Mann-Whitney U). |
| Figure 6 | Transcriptomic reproducibility: median gene-wise Spearman 0.75 (range 0.05–0.96) across 382 cell lines (CCLE Ghandi 2019 vs Klijn 2015). mRNA reproducibility explains median 15% of mRNA–protein variation; CCLE outlier 40%. Protein+mRNA reproducibility jointly explain 14–26% (12 studies) and 48% (CCLE). |
| Figure 7 / S7 | KEGG pathway enrichment of mRNA–protein correlation before vs after regressing out protein- and mRNA-reproducibility: housekeeping complexes (e.g., ribosome) stay enriched in LOW correlation; metabolic / environmental-information pathways lose their high-correlation enrichment after correction. |
| Figures S1–S6 (numbers cited in text) | Protein-complex membership explains ~3% (ovarian), 8% (CCLE), 6.7% (colon); combined with reproducibility ~17/23/26%. ML prediction (DREAM challenge): low vs high decile prediction correlation 0.35 vs 0.7; aggregate ranks explain 25% (breast), 26% (ovarian) of prediction scores. Factor-only model (abundance+variance+peptides+half-life) explains 3–17% of mRNA–protein correlation. CCLE replicate-pair correlations R1-R2 0.7, R1-R3 0.71, R2-R3 0.88. CCLE: 18 samples with replicate proteomes, 382 with replicate transcriptomes, only 8 with both. |

---

## Primary Sources Behind Key Quotes
- "only a moderate correlation between mRNA and protein" (review framing) → Buccitelli & Selbach, 2020, Nat. Rev. Genet. 21:630–644; Vogel & Marcotte, 2012, Nat. Rev. Genet. 13:227–232.
- Tumor average mRNA–protein correlation 0.2–0.5 → Mertins et al., 2016, Nature 534:55–62; Zhang et al., 2014, Nature 513:382–387; Zhang et al., 2016, Cell 166:755–765.
- Protein-complex subunits have lower mRNA–protein correlation (post-transcriptional attenuation) → Gonçalves et al., 2017, Cell Syst. 5:386–398; Ryan et al., 2017, Cell Syst. 5:399–409.
- Replicate proteomic datasets analyzed → CCLE: Nusinow et al., 2020, Cell 180:387–402; ovarian: Zhang et al., 2016, Cell 166:755–765; colon: Vasaikar et al., 2019, Cell 177:1035–1049.
- Transcriptomic replicate comparison → Ghandi et al., 2019, Nature 569:503–508 (CCLE) vs Klijn et al., 2015, Nat. Biotechnol. 33:306–312.
- ML prediction of protein from mRNA / DREAM challenge → Fortelny et al., 2017, Nature 547:E19–E20; Li et al., 2019, BMC Biol. 17:107; Yang et al., 2020, Cell Syst. 11:186–195.
- Noise-corrected within-sample estimate that mRNA largely determines protein (yeast) → Csárdi et al., 2015, PLoS Genet. 11:e1005206.
- Protein half-lives source → Zecha et al., 2018, Mol. Cell. Proteomics 17:974–992.
- GTEx human proteome map (abundance/variance/peptide factors) → Jiang et al., 2020, Cell 183:269–283.

---

## Flags
- [ ] Metadata unverified: Journal/venue NAME is not printed verbatim in the cleaned text. "Cell Reports Methods" is inferred from the DOI prefix `10.1016/j.crmeth.2022.100288` and the Cell-Press "In brief / Motivation / Highlights" article format; volume/issue not stated (article number 100288, year 2022 from "Published: September 8, 2022").
- [ ] Dates confirmed in text: Received Feb 12, 2022; Revised July 14, 2022; Accepted Aug 16, 2022; Published Sept 8, 2022.
- [ ] Author names fully present in source (not reconstructed): Swathi Ramachandra Upadhya; Colm J. Ryan. Corresponding/lead contact: colm.ryan@ucd.ie.
- [ ] Read at source (worth first-hand for our thesis): Csárdi et al., 2015 (PLoS Genet — noise-correction reverses the "RNA ≠ protein" conclusion in yeast; key foil for Claim 4); Buccitelli & Selbach, 2020 and Vogel & Marcotte, 2012 (canonical reviews on mRNA–protein decoupling for Claim 4); Liu, Beyer & Aebersold, 2016, Cell 165:535–550 (dependency of protein levels on mRNA abundance).
- [ ] Scope note: STAR Methods regression equations and software versions (Python/Pandas/etc.) read but not captured — off-roadmap.
- [ ] Source artifact: OCR garbling in some cited author names (e.g., "Gonc¸ alves", "Csa´ rdi", "Osz") — corrected spellings used where confidently inferable; verify against the journal if cited directly.
