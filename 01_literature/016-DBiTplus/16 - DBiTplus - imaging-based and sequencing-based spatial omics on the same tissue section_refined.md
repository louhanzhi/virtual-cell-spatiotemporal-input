# Integration of imaging-based and sequencing-based spatial omics mapping on the same tissue section via DBiTplus — Source Index

**Authors:** Archibald Enninful, Zhaojun Zhang, Dmytro Klymyshyn, Matthew Ingalls, Mingyu Yang, Hailing Zong, Zhiliang Bai, Negin Farzad, Graham Su, Alev Baysoy, Jungmin Nam, Yao Lu, Shuozhen Bao, Siyan Deng, Nancy R. Zhang, Oliver Braubach, Mina L. Xu, Zongming Ma & Rong Fan
**Journal / Venue:** Nature Methods, 2025 (article type: Article; venue inferred from DOI prefix s41592 + peer-review note — see Flags)
**DOI:** doi:10.1038/s41592-025-02948-0
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/16 - DBiTplus - imaging-based and sequencing-based spatial omics on the same tissue section_cleaned.md

---

## In One Sentence
The authors present DBiTplus, a workflow that performs sequencing-based spatial transcriptomics and multiplexed protein immunofluorescence imaging on the *same* tissue section (via RNase H-mediated cDNA retrieval that preserves tissue architecture), then computationally integrates the two modalities to deconvolve barcoded spots into single-cell-resolved spatial transcriptomes, demonstrated on mouse embryos and human lymph node / lymphoma tissue.

## Orientation (non-binding)
This is a spatial multi-omics *method* paper. It is most likely to feed the spatial axis (Axis C) and the cross-modal integration / unified-reference-frame parts of the Standard axis, plus Claims 8 (multimodal integration), 9 (data-silo / integration accuracy), 2 (spatial omics), 4 (mRNA–protein discordance), and 10 (resolution × coverage × destructiveness trade-offs). It can serve our thesis as *support* (concrete demonstration that same-section multimodal measurement on the same physical cells is achievable, and direct measurement that RNA cannot substitute for protein) and as a *foil/nuance* (it concedes the standard same-vs-adjacent-section integration problem and the depth/dropout trade-off that any data standard must confront; its "temporal" handling is pseudotime inferred from a static snapshot, not real time-course). Downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "The advent of high-throughput single-cell technologies has revolutionized our understanding of biological systems, enabling comprehensive analyses at the molecular level across diverse biological contexts. These approaches lack spatial context, limiting our understanding of intercellular interactions within tissues."
> — Introduction / p.1 · bears on: Claim 2, Axis C · States dissociated single-cell methods lack spatial context.

> "Broadly, in situ sequencing or imaging techniques offer higher spatial resolution and sensitivity but may lack transcriptome-wide coverage, whereas sequencing-based methods provide transcriptome-wide coverage, often at the expense of high spatial resolution."
> — Introduction / p.1 · bears on: Claim 10, Axis C · States the resolution-vs-coverage trade-off across spatial method classes.

> "Currently, most spatial multi-omic technologies involve running single spatial omics assays separately on adjacent or serial tissue sections, followed by computational data integration of the multimodal datasets. Due to heterogeneity in cellular composition and tissue architecture, even between adjacent sections from the same block, integrating multimodal data computationally may be suboptimal, as perfect concordance between tissue sections is almost unattainable. Thus, new methods for spatially resolved multimodal and multi-omics measurements on the same tissue sections are necessary."
> — Introduction / p.1 · bears on: Claim 8, Claim 9, Standard · States adjacent-section multimodal integration is suboptimal and motivates same-section measurement.

> "Central to the efforts to combine DBiT-seq with mxIF was to develop techniques to release cDNA from tissue sections while maintaining tissue integrity."
> — Results: Design and overview / p.2 · bears on: Claim 10, Axis C, Standard · States the technical goal of non-destructive cDNA retrieval to preserve tissue for downstream imaging.

> "We developed a workflow integrating the mxIF cell-by-protein and DBiTplus spot-by-gene matrices into a unified feature matrix with cell-type labels and spatial coordinates"
> — Results: Computational framework / p.2 · bears on: Claim 8, Standard · States the construction of a unified multimodal feature matrix with shared spatial coordinates.

> "DBiTplus was applied to an E11 paraffin-embedded mouse embryo and showed a strong correlation (R = 0.99) with the standard DBiT-seq workflow (on the adjacent section) with 27,884 overlapping genes. Each spot captured ~1,200 genes and 3,300 unique molecular identifiers (UMIs)"
> — Results: Mouse embryo / p.3 · bears on: Claim 6, Axis A · Reports transcriptome-wide capture depth and concordance with the standard workflow.

> "the CODEX (protein) contributed more for T cell-subtype identification, relative to DBiTplus (transcriptome), and the converse was observed for B cell subtypes such as GCB and plasma B cells… This can be explained by the marker composition of the CODEX panel, which included more T cell than B cell markers."
> — Results: Normal human lymph nodes / p.4 · bears on: Claim 4, Claim 8, Axis A · States that protein vs transcriptome modalities carry differential weight for distinguishing different cell subtypes.

> "Three methods—TACCO (Optimal transport-based), Cell2location (Bayesian probabilistic model) and RCTD (Poisson regression-based deconvolution)—were tested to benchmark spatial cell-type deconvolution, relative to the ground-truth CODEX-informed spot-level cell-type dataset… TACCO performed best, with 50% of spots showing Pearson scores > 0.6, versus 36% for Cell2location"
> — Results: Normal human lymph nodes / p.4 · bears on: Claim 8, Claim 9, Standard · Benchmarks deconvolution methods against an imaging-derived ground truth.

> "This is important because the relationship between protein levels and their coding transcripts can be discordant, influenced by spatial and temporal mRNA variations and the protein biosynthesis machinery."
> — Results: RNA–protein concordance / p.5 · bears on: Claim 4, Claim 5, Axis A · States RNA and protein levels can be discordant due to spatial/temporal and biosynthetic factors.

> "Of the 35 markers in the human lymph node CODEX panel, CD68 was the only gene transcript missing… Interestingly, CD68 transcripts were detectable in the reference dataset… CD68 protein expression was clearly visible in the CODEX images"
> — Results: RNA–protein concordance / p.5 · bears on: Claim 4, Claim 5, Axis A · Example where a protein is detected by imaging while its transcript is absent in the sequencing modality.

> "we evaluated the correlation between average normalized mRNA and protein levels in our dataset. As expected, we observed minimal correlation (R = 0.23, P = 0.18), consistent with prior findings in peripheral blood mononuclear cells, particularly for T cell markers such as CD4"
> — Results: RNA–protein concordance / p.5 · bears on: Claim 4 · Quantifies weak mRNA–protein correlation in the same cells.

> "These findings underscore the strength of DBiTplus in co-mapping RNAs and proteins on the same tissue section, allowing for cross-validation and enhancing confidence in cell-type annotation and spatial localization."
> — Results: RNA–protein concordance / p.5 · bears on: Claim 8, Standard · States that same-section co-mapping enables cross-modal validation.

> "DBiTplus further enables spatial profiling of small noncoding RNAs such as microRNAs (miRNAs), which regulate mRNA synthesis and gene expression."
> — Results: miRNAs in Richter's transformation / p.7 · bears on: Axis A, Claim 2 · States the assay captures an additional modality (small noncoding RNA / miRNA).

> "Spatial multi-omics integrates genomics, transcriptomics, proteomics and metabolomics while preserving spatial context, providing a comprehensive view of molecular processes in tissues. Traditional approaches utilize separate assays on adjacent tissue sections limiting alignment and multimodal integration accuracy due to tissue heterogeneity."
> — Discussion / p.8 · bears on: Claim 8, Claim 9, Axis A, Axis C, Standard · States the rationale for multimodal spatial measurement and the limitation of adjacent-section approaches.

> "leveraging mxIF data to guide the splitting of DBiT spatial transcriptomes can enable the creation of truly single-cell-level spatially resolved transcriptome atlases."
> — Discussion / p.8 · bears on: Claim 8, Axis C, Standard · Claims image-guided deconvolution yields single-cell-resolution spatial transcriptome atlases.

> "DBiTplus shares common limitations with sequencing-based spatial transcriptomics approaches; low capture depth can lead to dropout of low-abundance transcripts, which may be exacerbated by the lower transcript recovery rate of DBiTplus, compared to the standard DBiT-seq workflow, an important consideration when profiling rare cell populations."
> — Discussion / p.8 · bears on: Claim 10, Axis A · Author-conceded limitation: reduced transcript recovery / dropout of low-abundance transcripts.

> "the tight clamping of the tissue during the DBiTplus workflow may disrupt tissue architecture outside the clamped region and may lead to reduced imaging signal."
> — Discussion / p.8 · bears on: Claim 10, Axis C · Author-conceded limitation: the assay can perturb tissue architecture and imaging signal.

> "While Xenium and CosMx achieve single-cell spatial resolution through direct imaging of transcripts, DBiTplus even allows for unbiased profiling of total RNAs including small noncoding RNAs (that is, miRNAs), which is unique for discovery of new RNA biological mechanisms."
> — Discussion / p.8 · bears on: Claim 2, Claim 10, Axis A · Contrasts imaging-based single-cell resolution against sequencing-based unbiased / broader-modality coverage.

> "In summary, DBiTplus represents a spatial multi-omics approach that integrates sequencing-based and imaging-based spatial assays on the same tissue section, enabling image-guided deconvolution into single-cell-resolved spatial transcriptomes. By combining multiple molecular layers at single-cell resolution, DBiTplus provides unprecedented insights into tissue architecture and cellular interactions"
> — Discussion / p.8 · bears on: Claim 8, Axis C, Standard · Summarizes the same-section multimodal integration claim.

> "The tumor microenvironment (TME) is composed primarily of malignant B cells (both large and small, ~55%) and T cells (~30%), consistent with mxIF and clinical immunohistochemical images for CD20 and CD3"
> — Results: MZL progression / p.6 · bears on: Claim 7, Axis C · Quantifies spatial cellular composition of a tissue microenvironment.

> "Spatial gradient plots revealed enrichment of CD163+ macrophages, CD274 (PD-L1) and CD20+ cells in DLBCL regions, indicating an immunologically active yet suppressed microenvironment."
> — Results: CLL→DLBCL transformation / p.7 · bears on: Claim 7, Axis C · Reports spatially graded microenvironment composition associated with a disease state.

> "T cell infiltration was higher in DLBCL than CLL, with small B cells, on average, located closer to the nearest T cell compared to large B cells"
> — Results: CLL→DLBCL transformation / p.7 · bears on: Claim 7, Axis C · Spatial-neighborhood (cell-to-cell distance) measurement tied to cell state.

> "We performed pseudotime analysis on the deconvoluted data of small and large B cell transcriptomes using Monocle 3 and found small and large B cells on a differentiation continuum, revealing dynamic transcriptional changes across MZL progression"
> — Results: MZL pseudotime / p.6 · bears on: Claim 3, Axis B · Temporal dynamics here are *inferred* (pseudotime ordering) from a single static snapshot, not measured as a real time-course.

> "All samples were downsampled to the same number of reads for comparison (99,000,000 reads)."
> — Extended Data Fig. 2 legend / (figure caption) · bears on: Claim 9, Standard · States explicit read-depth normalization to make cross-sample comparison fair.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq loses spatial info | "These approaches lack spatial context…" / Introduction | supports |
| Claim 3 — destructive seq can't observe time pairwise | "We performed pseudotime analysis…Monocle 3" / MZL pseudotime | nuances |
| Claim 4 — modalities orthogonal / mutually irreplaceable | "minimal correlation (R = 0.23, P = 0.18)" / RNA–protein concordance | supports |
| Claim 4 — modalities orthogonal | "CD68 was the only gene transcript missing…protein…clearly visible" / RNA–protein | supports |
| Claim 5 — protein modality indispensable for function/phenotype | "CODEX (protein) contributed more for T cell-subtype identification" / lymph nodes | supports |
| Claim 6 — high-throughput spatial proteomics feasible | "35-plex CODEX panel" / lymph nodes; "44-marker panel" / MZL | supports |
| Claim 7 — microenvironment / spatial neighborhood shapes cell state | "small B cells…located closer to the nearest T cell" / CLL→DLBCL | supports |
| Claim 8 — multimodal orthogonal info, needs integration | "co-mapping RNAs and proteins…allowing for cross-validation" / RNA–protein | supports |
| Claim 9 — data silos / cross-section incomparability | "perfect concordance between tissue sections is almost unattainable" / Introduction | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "higher spatial resolution…but may lack transcriptome-wide coverage" / Introduction | supports |
| Claim 10 — destructiveness / recovery trade-off | "lower transcript recovery rate…dropout of low-abundance transcripts" / Discussion | challenges |
| Axis A — modality breadth (transcriptome + protein + miRNA + H&E) | "spatial profiling of small noncoding RNAs such as microRNAs" / miRNAs | supports |
| Axis B — temporal | "pseudotime analysis…Monocle 3" / MZL pseudotime | nuances |
| Axis C — spatial (subcellular → cell → microenvironment) | "single-cell-level spatially resolved transcriptome atlases" / Discussion | supports |
| Standard — cross-modal pairing on a unified reference frame | "unified feature matrix with cell-type labels and spatial coordinates" / framework | supports |
| Standard — benchmarking / comparability | "downsampled to the same number of reads (99,000,000)" / Ext. Data Fig. 2 | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | DBiTplus experimental workflow (a) and the three-step integrative analysis pipeline (b). |
| Fig. 2 | FFPE E11 mouse embryo: tissue integrity preserved after cDNA retrieval; R = 0.99 (P < 2.2×10⁻¹⁶) vs standard DBiT-seq; 27,884 overlapping genes; ~1,200 genes / 3,300 UMIs per spot; 26-marker CODEX; 10 transcriptomic clusters; CODEX-informed spot deconvolution. |
| Fig. 3 | FFPE benign human lymph node (50-µm device); 35-plex CODEX; co-registration; WNN modality weights (protein > transcriptome for T-cell subtypes); deconvolution benchmark — TACCO 50% of spots Pearson > 0.6, Cell2location 36%. |
| Fig. 4 | Marginal zone lymphoma (MZL): 25-µm device + 44-marker CODEX; TME ~55% malignant B cells, ~30% T cells; pseudotime (Monocle 3) along progression. |
| Fig. 5 | Concurrent CLL + Richter's transformation-DLBCL in one node: 30-marker CellScape; large B cells ~20 µm diameter; T-cell–tumor distance (n_CLL = 5,525; n_DLBCL = 4,924; median 7.292 vs 7.715 µm); immune signature scores higher in DLBCL (Mann–Whitney, ****P < 0.0001). |
| Ext. Data Fig. 1 | cDNA-retrieval comparison: NaOH/DMSO disrupted morphology or staining; RNase H best preserved morphology and yielded 14 positive markers. |
| Ext. Data Fig. 2 | FF E13 embryo: 24,102 (control) vs 20,973 (RNase H) genes; replicate correlations R = 0.87 / 0.72, between-replicate R = 0.84; downsampled to 99,000,000 reads; average 1,029 genes / 1,601 UMIs per 25-µm spot. |
| Ext. Data Fig. 4 | Label-transfer F1-scores by cell type (overall accuracy 0.87, n = 6,920); ASW with/without CODEX 0.47 vs 0.46; ARI improved 0.09 → 0.21 with CODEX guidance; RCTD deconvolution metrics. |
| Ext. Data Fig. 6 | RNA–protein concordance: 35-marker panel, only CD68 transcript missing; DBiTplus vs Patho-DBiT reference R = 0.89 (P < 2.2×10⁻¹⁶); mRNA–protein R = 0.23 (P = 0.18). |
| Ext. Data Fig. 10 | Spatial miRNA profiling: 7 miRNA clusters; clusters 0/1 mirror CLL→DLBCL transition; Monocle 3 pseudotime of transformation. |

---

## Primary Sources Behind Key Quotes
- mRNA–protein levels can be discordant (general principle) → Liu, Y., Beyer, A. & Aebersold, R. "On the dependency of cellular protein levels on mRNA abundance." Cell 165, 535–550 (2016) — ref 19.
- Discrepant mRNA vs protein in immune cells (the R = 0.23 comparison context) → Li, J., Zhang, Y., Yang, C. & Rong, R. "Discrepant mRNA and protein expression in immune cells." Curr. Genomics 21, 560–563 (2020) — ref 20.
- Underlying DBiT-seq barcoding method this paper extends → Liu, Y. et al. "High-spatial-resolution multi-omics sequencing via deterministic barcoding in tissue." Cell 183, 1665–1681.e18 (2020) — ref 3.
- FFPE / Patho-DBiT workflow and reference lymph node dataset → Bai, Z. et al. "Spatially exploring RNA biology in archival formalin-fixed paraffin-embedded tissues." Cell (2024) — ref 13.
- Same-slide / same-section spatial multi-omics precedents cited as motivation → REDCAT (Li, Y. et al., bioRxiv 2024 — ref 9) and IN-DEPTH (Yeo, Y. Y. et al., bioRxiv 2024 — ref 10).
- Cross-modal integration algorithm adapted here → Chen, S. et al. "Integration of spatial and single-cell data across modalities with weakly linked features" (MaxFuse). Nat. Biotechnol. 42, 1096–1106 (2024) — ref 11.

---

## Flags
- [ ] Metadata unverified: Venue name "Nature Methods" is not printed in the cleaned body as a masthead; it is inferred from the DOI prefix (10.1038/s41592 = Nature Methods) and the peer-review line ("Nature Methods thanks Qiangyuan Zhu…"). Treat as high-confidence but not literally printed.
- [ ] Metadata unverified: Publication year. Source shows "Received 5 November 2024 / Accepted 27 October 2025 / Published online: xx xx xxxx" (placeholder) and "© The Author(s) 2026." Header lists 2025 (DOI year) but copyright is 2026; the exact published-online date is not finalized in this cleaned copy.
- [ ] Page numbers approximate: the cleaned MD has no printed page numbers; "p.X" anchors above are sequential reading-order estimates, not journal pagination. Section names are the reliable jump-back anchors.
- [ ] Read at source (for Claim 4 — mRNA–protein non-equivalence): Liu, Beyer & Aebersold 2016 (Cell 165:535–550, ref 19) and Li et al. 2020 (Curr. Genomics 21:560–563, ref 20) are the first-hand sources for the discordance claim — cite directly rather than via this paper.
- [ ] Scope note: Detailed lymphoma disease-mechanism findings (specific DEGs, pathway/upstream-regulator results for MZL/CLL/DLBCL, individual miRNA biology) were largely NOT captured — they fall under the context file's "do not bind to a specific disease/cell" boundary. Only their data-standard-relevant framing (spatial microenvironment, RNA–protein discordance, multimodal integration, pseudotime as inferred-time) was indexed.
- [ ] Interpretive note (not in source): The paper achieves cross-*modality* pairing on the *same physical cells* (a unified reference frame), but does NOT achieve cross-*time* paired observation; its "temporal" results are pseudotime inferred from a static section. This distinction is the indexer's, flagged so the writer does not over-read DBiTplus as solving the temporal axis.
