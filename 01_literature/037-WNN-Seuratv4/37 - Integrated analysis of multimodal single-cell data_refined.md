# Integrated analysis of multimodal single-cell data — Source Index

**Authors:** Not printed as a byline in the cleaned source. Author initials appear in Author Contributions: P.S., R.S. (conceived); Y.H., S.Z., A.B., C.D., M.Z., P.H., J.J., A.S., T.S. (computational); R.G., R.S. (supervised computational); S.H., E.A.-N., W.M.M., M.J.L., A.J.W., M.S., E.P., E.P.M., L.B.F., B.Y., A.J.R. (experimental); J.M.E., C.A.B., P.S. (supervised experimental). See Flags.
**Journal / Venue:** Cell, 2021 (article type "Cell Resource"; volume/issue/pages not printed in cleaned source — see Flags)
**DOI:** doi:10.1016/j.cell.2021.04.048
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/37 - Integrated analysis of multimodal single-cell data_cleaned.md

---

## In One Sentence
The paper introduces "weighted-nearest neighbor" (WNN) analysis, an unsupervised computational framework that learns cell-specific weights for each measured modality and integrates them into a joint definition of cellular state, and applies it to a CITE-seq atlas of ~211,000 human PBMCs (up to 228 surface-protein antibodies + transcriptome) to resolve immune cell states, build a multimodal reference, and map new scRNA-seq queries onto it.

## Orientation (non-binding)
This is a landmark single-cell *multimodal integration* methods/resource paper. It is strong ammunition for the roadmap claim that modalities are non-substitutable (it repeatedly states the transcriptome alone cannot separate functionally distinct cells, and that protein/ATAC carry information RNA misses) and for the claim that multimodal data require integration. It can ALSO serve as a foil/exemplar of the dissociated single-cell paradigm our thesis critiques: the atlas is built from *dissociated PBMCs* (no spatial/tissue context), its "time course" uses different cells per time point (destructive, non-paired), and spatial location and lineage are explicitly named as future, not-yet-integrated modalities. One notable counter-line for caution: it shows transcriptome-only queries can recover high-resolution multimodal states by mapping onto a multimodal reference — a writer should be ready for that nuance.

---

## Load-Bearing Excerpts

> "transcriptomics alone is often incapable of separating molecularly similar, but functionally distinct, categories of immune cells."
> — INTRODUCTION · bears on: Claim 4 (modalities non-substitutable), Axis A (modality) · the paper claims the transcriptome by itself cannot distinguish some functionally distinct cell types.

> "Despite tremendous functional diversity, distinct populations of T cells such as effector, regulatory, gd, and mucosal associated invariant T (MAIT), often cannot be effectively separated by scRNA-seq alone, even when using the most sensitive and cutting-edge technologies"
> — INTRODUCTION · bears on: Claim 4, Claim 5 (protein essential for function) · scRNA-seq fails to separate several T-cell subsets even at best-in-class quality.

> "More broadly, this exhibits the challenge of defining cell states based on the transcriptome alone, because important sources of cellular heterogeneity may not correlate strongly with transcriptomic features despite being identifiable in other modalities."
> — INTRODUCTION · bears on: Claim 4 (core), Claim 8 (orthogonal multimodal info) · heterogeneity present in other modalities need not be reflected in the transcriptome.

> "Each of these approaches offers an exciting solution to overcome the inherent limitations of scRNA-seq and to explore how multiple cellular modalities affect cellular state and function"
> — INTRODUCTION · bears on: Claim 4, Claim 8 · multimodal measurement is framed as overcoming intrinsic scRNA-seq limits.

> "The maturation of multimodal single-cell technologies also necessitates the development of new computational methods to integrate information across different data types"
> — INTRODUCTION · bears on: Claim 8 (integration needed) · new technologies create a need for integration methods.

> "these strategies must be robust to potentially large differences in the data quality and information content for each modality... The varying information content of each modality, even across cells in the same dataset, represents a pressing challenge for the analysis and integration of multimodal datasets."
> — INTRODUCTION · bears on: Claim 8, Axis-standard (integration/QC) · modalities differ in quality/information content; integration must account for this.

> "the increased copy number of protein molecules compared to RNA molecules typically leads to more robust detection of protein features. The protein data in CITE-seq may therefore represent the most informative modality"
> — RESULTS, Quantifying the relative utility of each modality · bears on: Claim 4, Claim 5 · protein can be the more robustly detected / more informative modality than RNA.

> "CD8+ and CD4+ T cells were partially blended together when analyzing the transcriptome but separated clearly in the protein data. Contrastingly, conventional dendritic cells (cDCs)... formed distinct clusters when analyzing RNA but were intermixed with other cell types based on surface protein abundance."
> — RESULTS, Quantifying the relative utility of each modality · bears on: Claim 4 (modality-specific, orthogonal information) · each modality resolves cell types the other misses, in both directions.

> "for CD8+ T cells, the most similar RNA neighbors often reflected a mix of CD8+ and CD4+ T cells (in the RNA KNN graph, there are a total of 944 incorrect edges that connect CD8+ to CD4+ T cells). By contrast, protein neighbors were predominantly correctly identified as CD8+ T cells (in the protein KNN graph, 12 CD8+/CD4+ edges were identified)."
> — RESULTS, Quantifying the relative utility of each modality · bears on: Claim 4 (quantitative) · protein neighborhoods are far more accurate than RNA for these T cells (944 vs 12 wrong edges; WNN = 20).

> "the relative utility of each modality to define cell states may vary across individual cells."
> — RESULTS, Quantifying the relative utility of each modality · bears on: Claim 4, Claim 8 · informativeness of a modality is cell-specific, not global.

> "the statistical power in unsupervised analysis of either modality separately was insufficient to identify these populations, demonstrating the importance of joint analysis."
> — RESULTS, WNN is a robust and flexible approach · bears on: Claim 8 (integration > single modality) · single-modality analysis lacked power that joint analysis provided.

> "T cell groups—and in particular, populations that were masked in scRNA-seq analyses—all received higher protein modality weights"
> — RESULTS, WNN is a robust and flexible approach · bears on: Claim 4, Claim 5 · cell states hidden in scRNA-seq are recovered via protein.

> "integrated WNN analysis can provide necessary flexibility and allow one data type to compensate for weaknesses in another."
> — RESULTS, WNN is a robust and flexible approach · bears on: Claim 8 · explicit statement that modalities compensate for each other's weaknesses.

> "WNN analysis identified a novel population of Basal cells that exhibits distinct chromatin accessibility profiles, but does not exhibit unique transcriptomic characteristics... cells that exhibit a primed chromatin state preceding transcriptomic shifts may differ in their proliferative and regenerative potential."
> — RESULTS, WNN is a robust and flexible approach (SHARE-seq) · bears on: Claim 4 · a state defined by chromatin alone, invisible to the transcriptome.

> "the ability of WNN to identify subpopulations that are masked by scRNA-seq alone is not limited to immune or CITE-seq datasets. We conclude that WNN analysis is capable of sensitively and robustly characterizing populations that cannot be identified by a single modality"
> — RESULTS, WNN is a robust and flexible approach · bears on: Claim 4, Claim 8 · generalized claim that single-modality analysis misses populations.

> "we found that the increasing ADT noise led to a decrease in protein weights for all cell types, in a dose-dependent manner. Moreover, protein modality weights were assigned to 0 after a sufficient amount of protein noise was added, correctly instructing downstream analyses to focus only on scRNA-seq data."
> — RESULTS, WNN is a robust and flexible approach (noise simulation) · bears on: Claim 8, Axis-standard (data-quality robustness) · the method down-weights a degraded modality automatically.

> "We applied WNN analysis to a dataset of 11,351 paired PBMC profiles generated by the 10x Genomics Multiome ATAC+RNA kit... we found that ATAC-seq data were more capable of separating naive CD8+ and CD4+ T cell states due to reliable detection of cell-type-specific open chromatin regions"
> — RESULTS, WNN is a robust and flexible approach · bears on: Claim 4, Claim 8 · chromatin accessibility resolves states RNA blends (RNA KNN 984, ATAC KNN 373, WNN 322 wrong edges).

> "for each subject, PBMCs were collected at three time points: immediately before (day 0), 3 days, and 7 days following administration of a VSV-vectored HIV vaccine"
> — RESULTS, A multimodal atlas of the human PBMCs · bears on: Claim 3 (temporal; destructive non-paired sampling), Axis B (temporal) · the "time course" samples different cells at each time point (no same-cell tracking).

> "We identified 57 clusters in WNN analysis, encapsulating all major and minor immune cell types and revealing striking cellular diversity particularly within lymphoid lineages."
> — RESULTS, A multimodal atlas of the human PBMCs · bears on: Claim 4, Claim 8 · multimodal integration yields 57 resolved cell states.

> "our ability to identify these groups was substantially reduced without WNN analysis, as multiple clusters blended together when performing separate analysis of either RNA or protein data. We conclude that multimodal integration is essential for the unsupervised discovery and annotation of immune cell states"
> — RESULTS, A multimodal atlas of the human PBMCs · bears on: Claim 8 (core) · integration declared "essential" for unsupervised state discovery.

> "we identified distinct subpopulations defined by bimodal and mutually exclusive expression of the integrin proteins CD49a and CD103... CD8+ CD103+ T cells expressed high surface protein levels of the heterodimeric co-binding partner integrin beta-7... while expression was absent in CD8+ CD49a+ groups."
> — RESULTS, Multimodal heterogeneity within lymphoid populations · bears on: Claim 4, Claim 5 · functional protein markers define states resolvable at the protein level.

> "within B cells, we identified a continuous trajectory connecting naive to memory cells defined by the canonical protein markers immunoglobulin D (IgD) and CD27"
> — RESULTS, Multimodal heterogeneity within lymphoid populations · bears on: Claim 3 (trajectory is inferred from a snapshot, not lineage-tracked), Axis B · a "trajectory" derived from one destructive snapshot, not paired observation.

> "We mapped this dataset onto our reference using only the transcriptome data and transferred our level 2 annotations, revealing the presence of multiple high-resolution lymphoid subsets... We verified the accuracy of our predictions using the query protein data, which was held out of the reference mapping procedure, yet revealed expression patterns based on our predicted annotations that were fully concordant with our reference dataset."
> — RESULTS, Mapping query datasets to multimodal references · bears on: Claim 4 (COUNTER/nuance), Claim 9 (reference/standard) · transcriptome-only queries recover multimodal states via a multimodal reference — a caution against "RNA can never substitute."

> "this supervised mapping procedure dramatically improved our ability to analyze and interpret query scRNA-seq datasets compared to unsupervised analysis."
> — RESULTS, Mapping query datasets to multimodal references · bears on: Claim 9 (comparability via shared reference) · reference-based mapping outperforms unsupervised per-dataset analysis.

> "we observed a depletion of MAIT cells in COVID-19 samples compared to healthy controls... We observed strong quantitative agreement (R = 0.911) in the fraction of MAIT cells predicted by scRNA-seq and measured by CyTOF"
> — RESULTS, Mapping query datasets to multimodal references · bears on: Claim 9 (cross-platform agreement), Claim 5 · cross-platform (scRNA-seq vs CyTOF) quantitative concordance R=0.911.

> "the modality weights learned in our procedure serve not only as a proxy for the technical quality of a measurement type, but may also reflect the biological importance of each modality in determining cellular identity."
> — DISCUSSION · bears on: Claim 4, Claim 8 · modality weighting reflects both technical quality and biological importance.

> "our analyses of human bone marrow demonstrated that progenitor cells and differentiated cells exhibited divergent modality weights."
> — DISCUSSION · bears on: Claim 4, Claim 8 · different cell types rely on different modalities for identity.

> "As future technologies enable the simultaneous measurement of modalities spanning the central dogma including chromatin state, DNA methylation, transcription, lineage, spatial location, and protein levels—WNN analysis may help to reveal how subpopulations of cells differentially utilize these modalities"
> — DISCUSSION · bears on: Claim 2 (spatial — conceded as not-yet-integrated), Claim 3 (lineage — conceded as future), Axis A/B/C · spatial location and lineage are named as future modalities not measured here.

> "Integrative multimodal analysis therefore provides a path forward to move beyond the partial and transcriptome-focused view of a cell and toward a unified definition of cellular behavior, identity, and function."
> — DISCUSSION · bears on: Claim 4, Claim 8 · explicit framing that a transcriptome-only view of the cell is "partial."

> "to look beyond the transcriptome toward a unified and multimodal definition of cellular identity."
> — SUMMARY · bears on: Claim 4, Claim 8 · headline statement that cell identity needs more than the transcriptome.

> "WNN assumes that modalities do not define conflicting sets of cell states. Although we have not observed this when using molecular data such as chromatin state, gene expression, and surface protein abundance, this assumption may be problematic when integrating morphological, functional, and molecular data."
> — Limitations of the study · bears on: Claim 8 (integration limits), Axis A (imaging/morphology), Axis-standard · author-conceded limit: integration may fail when modalities (e.g., morphology) disagree.

> "our circulating immune atlas was constructed from PBMCs and therefore contains few cells with no nuclei (erythrocytes) or multi-lobed nuclei (granulocytes)."
> — Limitations of the study · bears on: Claim 2 (dissociated blood; no tissue/spatial context) · the atlas is dissociated blood, not tissue in situ.

> "WNN requires a dimensional reduction to describe the neighborhood structure between cells. This requirement is not compatible with categorical or low-dimensional data."
> — Limitations of the study · bears on: Claim 8, Axis-standard · author-conceded methodological constraint of the integration approach.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq loses spatial | "our circulating immune atlas was constructed from PBMCs…" / Limitations; "spatial location" as future modality / Discussion | challenges (paper as foil/exemplar) |
| Claim 3 — destructive seq can't pair-observe time | "three time points: …day 0…3 days…7 days…" / Atlas; "continuous trajectory connecting naive to memory" / Lymphoid; "lineage" as future modality / Discussion | nuances (foil — inferred, non-paired) |
| Claim 4 — modalities orthogonal / non-substitutable | "important sources of cellular heterogeneity may not correlate strongly with transcriptomic features…" / Introduction; "944 incorrect edges…12…edges" / Results | supports |
| Claim 4 — modalities non-substitutable (counter) | "mapped this dataset…using only the transcriptome data…fully concordant" / Mapping | challenges |
| Claim 5 — protein essential for function/phenotype | "protein data…most informative modality" / Results; "T cell groups…received higher protein modality weights" / Results | supports |
| Claim 8 — multimodal orthogonal info, needs integration | "multimodal integration is essential for the unsupervised discovery…" / Atlas; "allow one data type to compensate for weaknesses in another" / Results | supports |
| Claim 9 — data islands / cross-paper comparability / standards | "supervised mapping procedure dramatically improved…" / Mapping; "R = 0.911…scRNA-seq and…CyTOF" / Mapping; Azimuth web app / Discussion | supports (nuance: reference-based) |
| Axis A (modality) | modality-weight machinery; chromatin/protein/RNA each resolve distinct states / throughout | supports |
| Axis B (temporal) | vaccination day 0/3/7 sampling; inferred B-cell trajectory | nuances |
| Axis C (spatial) | absent from this work; "spatial location" only as future modality | challenges (gap) |
| Axis-standard (integration/QC/comparability) | data-quality robustness, noise down-weighting, reference mapping, Azimuth | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Dataset scale | CITE-seq atlas: 210,911 final PBMCs (summary rounds to ~211,000) from 8 HIV-vaccine-trial volunteers, ages 20–49, 3 time points (day 0/3/7); 161,764 cells with 228 TotalSeq A antibodies (avg 8,003 RNA molecules/cell, 5,251 ADT/cell) + 49,147 ECCITE-seq cells with 54 antibodies. |
| Figure 1 | Cord-blood CITE-seq (8,617 cells, 10 markers): RNA vs protein vs WNN; CD8/CD4 wrong edges RNA 944 → protein 12 → WNN 20; modality weights recapitulate biology unsupervised. |
| Figure 2 | Bone marrow CITE-seq (30,672 cells, 25 antibodies): WNN resolves states; ADT-noise simulation drives protein weights to 0; benchmark vs MOFA+ and totalVI (WNN superior/equivalent on 25 proteins; up to 15-fold faster). |
| Figure S3 | 10x Multiome ATAC+RNA (11,351 PBMCs; wrong naive CD8/CD4 edges RNA 984 / ATAC 373 / WNN 322); ASAP-seq (4,725 cells, 227 antibodies); SHARE-seq mouse skin (34,774 cells) — novel chromatin-defined Basal_4 population. |
| Figures 3–4 | WNN atlas: 57 clusters (3 annotation levels: 8 / 30 / 57 categories); marker-panel discovery — 1 marker gives ≥10-fold enrichment for 45 clusters, 3 markers for 55 clusters (Table S2). |
| Figure 5 | Lymphoid heterogeneity: CD49a/CD103 integrin subsets; NK CD16/CD38 two-dimensional gradient; 31 expanded clones (≥10 cells); CMV-positive volunteers = 91% of expanded-clone cells. |
| Figure 6 | Vaccination innate response: shared 62-gene type-I-interferon module in CD14+ and CD16+ monocytes; Siglec-1/CD169 day-3 biomarker; cDC2-specific response; classical/non-classical monocyte ratio shift. |
| Figure 7 | Reference mapping (sPCA + anchors); flu-vaccine query (53,099 cells, 82 proteins); COVID-19 query (Wilk et al.) → 12 T-cell groups; MAIT depletion; scRNA-seq vs CyTOF R = 0.911; benchmark vs scArches. |
| Table S1 / S2 / S3 | S1: 228-antibody panel; S2: per-cluster immunophenotype enrichment panels; S3: per-volunteer CMV status. |

---

## Primary Sources Behind Key Quotes
- CITE-seq (simultaneous RNA + surface protein) → Stoeckius, M. et al. (2017). Simultaneous epitope and transcriptome measurement in single cells. Nat. Methods 14, 865–868. (ref in list; also source of the 8,617-cell CBMC demo dataset)
- Minimal RNA content / high RNase in T cells → Andreeff, M. et al. (1978). RNA content in human lymphocyte subpopulations. Proc. Natl. Acad. Sci. USA 75, 1938–1942; Sercan Alp, Ö. et al. (2015). Eur. J. Immunol. 45, 975–987. (Lu et al., 2018 also cited but full entry not captured)
- Transcriptome + chromatin accessibility (single-cell joint ATAC+RNA) → Cao, J. et al. (2018). Joint profiling of chromatin accessibility and gene expression in thousands of single cells. Science 361, 1380–1385; Chen, S., Lake, B.B., Zhang, K. (2019b). Nat. Biotechnol. 37, 1452–1457.
- Transcriptome + spatial location → Rodriques, S.G. et al. (2019). Slide-seq. Science 363, 1463–1467; Vickovic, S. et al. (2019). High-definition spatial transcriptomics. Nat. Methods 16, 987–990.
- Benchmark methods → MOFA+: Argelaguet, R. et al. (2020). Genome Biol. 21, 111; totalVI: Gayoso, A. et al. (2019). bioRxiv https://doi.org/10.1101/791947; scArches: Lotfollahi, M. et al. (2020). bioRxiv https://doi.org/10.1101/2020.07.16.205997.

---

## Flags
- [ ] Metadata unverified: Journal volume/issue/page numbers are not printed in the cleaned source. DOI (10.1016/j.cell.2021.04.048), venue ("Cell"; "Cell Resource"), and dates (Received Nov 3 2020; Revised Mar 3 2021; Accepted Apr 28 2021; Published May 31 2021) are confirmed in the text.
- [ ] Reconstructed (NOT in source text): No author byline with full names appears in the cleaned source — only initials in the Author Contributions section (reproduced in header). Full names were NOT inferred. (Corresponding/senior author initials R.S./P.S.)
- [ ] Read at source: For first-hand citation of spatial single-cell (Slide-seq / HD spatial transcriptomics — Rodriques 2019, Vickovic 2019) and of CITE-seq (Stoeckius 2017), cite those primary papers directly rather than via this one.
- [ ] Scope note: COVID-19 / vaccination immunology specifics (interferon modules, MAIT biology, CMV clonal expansion) are largely off-roadmap biology; captured only where they double as evidence for cross-modal information, temporal sampling design, or cross-platform comparability.
- [ ] OCR artifacts in source: Greek/symbol characters are degraded in the cleaned MD (e.g., "gd" for γδ T cells; "RORgt" for RORγt; superscript "+"/"-" rendered via markup). Quotes above normalize superscript markup to plain +/− but preserve wording.
