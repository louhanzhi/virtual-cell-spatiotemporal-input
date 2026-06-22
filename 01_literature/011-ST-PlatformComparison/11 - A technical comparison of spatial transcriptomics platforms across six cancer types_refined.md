# A technical comparison of spatial transcriptomics platforms across six cancer types — Source Index

**Authors:** Sergi Cervilla, Daniela Grases, Elena Perez, Francisco X. Real, Eva Musulen, Julieta Aprea, Manel Esteller, Eduard Porta-Pardo
**Journal / Venue:** Genome Biology (BMC), 2026 — venue inferred from DOI prefix s13059; volume/issue/pages not printed in text; see Flags
**DOI:** doi:10.1186/s13059-026-03937-y
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/11 - A technical comparison of spatial transcriptomics platforms across six cancer types_cleaned.md

> Note: the cleaned source carries OCR artifacts (e.g. "profling", "fxed", "diferences", "Tis/Te" for "This/The", "infuences"). Quotes below are reproduced verbatim as printed in the source so they remain greppable jump-back anchors; the OCR glitches are the source's, not introduced here. See Flags.

---

## In One Sentence
The authors systematically benchmark five commercial spatial transcriptomics platforms (Visium v1, Visium v2/CytAssist, Visium HD, Xenium, CosMx) — plus a matched 35-protein Visium spatial protein panel — on serial FFPE sections from six cancer types, quantifying platform trade-offs in transcript/UMI detection, segmentation, cell-type recovery, sampling/area effects, gene-panel size, and RNA–protein concordance, and finding widespread spatial RNA–protein decoupling.

## Orientation (non-binding)
A same-sample technical benchmark sitting squarely on our **spatial axis (C)** and our **standard/integration axis** (claims 2, 9, 10). Its most load-bearing material for us is twofold: (1) empirical **spatial RNA–protein decoupling** (~0.1 spatial Pearson vs ~0.7 bulk CPTAC), direct ammunition that RNA does not stand in for protein (claims 4/5); and (2) hard numbers that **the same tissue yields different answers across platforms, panels, and sampled areas** — a comparability/standards argument (claim 9) and a measurement trade-off argument (resolution × coverage × sensitivity; claim 10). It can serve as support (spatial omics preserves architecture dissociation destroys; modalities decouple) AND as a foil (its own spatial-protein arm is only a 35-plex targeted panel, and it explicitly disclaims being a usage/standard guide). It does **not** address the temporal axis (B) — FFPE snapshots, no time course — and its proteomics is targeted/low-plex, not the high-throughput spatial proteomics our group argues for. Downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "Single-cell omics technologies partially address this limitation by enabling the analysis of molecular profles at single-cell resolution. Tis has uncovered extensive mutational [10], epigenetic [11], and transcriptional [12] heterogeneity in both cancer and immune cells. Yet, these methods require dissociation of the tissue, thereby destroying the spatial relationships between cells and their microenvironment. Tis information is critical the context of most diseases, including solid tumors, where spatial organization infuences cell signaling, immune infltration, and therapeutic response."
> — Background · bears on: claim 2 (scRNA-seq loses spatial), claim 7 (microenvironment shapes cell state), axis C · states that dissociation-based single-cell destroys spatial relationships that govern signaling/immune infiltration/therapy response.

> "Spatial omics technologies bridge this gap by capturing molecular information while preserving spatial architecture [13]."
> — Background · bears on: claim 2, axis C · positions spatial omics as the fix for the lost spatial dimension.

> "However, by averaging signals across heterogeneous cell populations, bulk profling obscures the cellular diversity and spatial context that shape tumor behavior."
> — Background · bears on: claim 10 (bulk vs single-cell trade-off), claim 2 · states bulk profiling loses cellular diversity and spatial context.

> "Advances in spatial profling now allow measurement of DNA alterations [14], epigenetic modifcations [15], and, most commonly, RNA [16–23] and protein [24–26] expression, directly within intact tissue sections."
> — Background · bears on: axis A (modality), claim 2 · notes spatial measurement spans DNA/epigenome/RNA/protein but is most commonly RNA.

> "In matched FFPE samples, Visium v2 consistently detected more unique genes (~ 2,000 vs. ~ 200; Fig. 1c), captured more UMIs per spot, and exhibited stronger spatial autocorrelation (Moran's I), particularly for lowly expressed genes (Additional fle 2: Fig. S1)."
> — Results, Generation of matching data · bears on: claim 9 (within-platform version change alters data), claim 10 · quantifies that a chemistry upgrade (v1→v2) changes detected genes by ~10x on the same tissue.

> "When comparing the proportion of negative control signals relative to gene signals, normalized by the panel size, we found that CosMx exhibited a negative probe signal rate of approximately 10.31%, while Xenium demonstrated a markedly lower rate of 0.06% (Additional fle 3: Table S2). Consistently, the signal-to-noise ratio ... was substantially higher in Xenium. Specifcally, gene probes in CosMx yielded approximately 3 times more counts than negative probes, whereas in Xenium, this ratio was approximately 450 (Additional fle 2: Fig. S4)."
> — Results, CosMx vs Xenium · bears on: claim 9 (QC/comparability), claim 10 · quantifies large platform differences in background/specificity (SNR ~3 vs ~450).

> "Using UMI density per gene as the comparison metric, Xenium showed a stronger correlation with Visium v2 (Pearson R = 0.93) than CosMx (R = 0.86) across all tumor types ... Tis discrepancy was most pronounced for lowly expressed genes, which in CosMx often had UMI densities indistinguishable from those of negative control probes, suggesting limited reliability for low-abundance transcripts."
> — Results, CosMx vs Xenium · bears on: claim 9 (cross-platform concordance), claim 10 · quantifies imaging-vs-sequencing concordance and CosMx unreliability for low-abundance genes.

> "CosMx consistently detected 2 to 3 times more genes and transcripts per cell than Xenium across all tumor types (Fig. 2e, f, 'All'), consistent with its larger panel size. To isolate platform-specifc efects from panel content, we repeated the analysis using only the 125 genes shared between both panels. ... When comparing transcript counts per cell for these shared genes, Xenium consistently outperformed CosMx across all samples (Fig. 2f, 'Int'), suggesting higher detection efciency on a per-gene basis."
> — Results, CosMx vs Xenium · bears on: claim 9, claim 10, axis A · shows raw counts are confounded by panel size; per-gene efficiency differs once panel content is controlled.

> "Xenium consistently detected 5% to 30% more cells than CosMx (Fig. 2a), probably refecting the diferences in the segmentation strategy."
> — Results, CosMx vs Xenium · bears on: claim 9 · segmentation choice changes cell counts on the same tissue.

> "we observed a higher proportion of fbroblast cells misclassifed as cancer cells in the CosMx dataset (71.6% in CosMx vs. 10.2% in Xenium)."
> — Results, Biological concordance · bears on: claim 9 (platform-dependent annotation), claim 10 · large platform disagreement in cell-type calls within stromal regions.

> "Tis discrepancy was more pronounced in CosMx, where endothelial structures were largely absent (8.51% endothelial cells in CosMx vs. 28.7% in Xenium). ... diferences in gene detection efciency become critical when assessing fner spatial features."
> — Results, Biological concordance · bears on: claim 9, axis C · detection efficiency gaps distort fine spatial/anatomical structure recovery.

> "However, sampling only a single FOV yielded highly variable estimates. For example, the inferred proportion of cancer cells ranged from 5 to 55%, whereas the true value for the entire sample was 22% (Fig. 3e, Additional fle 2: Fig. S14). As a control, we did an analogous simulation by randomly selecting an equivalent number of single cells from across the full tissue area, mimicking a single-cell experiment without spatial constraints. In this case, the variability was markedly reduced and consistently closer to the ground truth."
> — Results, Biological concordance · bears on: claim 9 (sampling/comparability), claim 10, axis C · spatially-constrained small-area sampling gives wildly biased composition vs ground truth.

> "Tese results illustrate how spatial constraints, even when total cell numbers are matched, can introduce substantial variability in cell type composition estimates, highlighting the importance of scanned area in the design and interpretation of spatial transcriptomics experiments."
> — Results, Biological concordance · bears on: claim 9, claim 10 · scanned area is a design/standard variable that changes results.

> "the MMP7 gene ... is absent from the Xenium Multi-Tissue panel. In our colorectal tumor sample, CosMx detected strong MMP7 expression ... Tis signal enabled spatial subtyping of cancer cells with potential relevance to tumor progression, an insight that would have been missed using XeniumMT due to its limited panel content."
> — Results, Biological concordance · bears on: claim 9 (panel design as standard), claim 4/5 (coverage gaps lose information) · targeted-panel content limits what biology can be seen.

> "larger panels may sufer from reduced sensitivity due to optical crowding, an efect in which high probe density compromises accurate signal resolution [35]."
> — Results, Effect of panel size · bears on: claim 10 (measurement trade-off), axis A · names a physical limit on imaging-based multiplexing.

> "When focusing on 225 genes shared between panels, XeniumMT consistently detected more transcripts and genes per cell, indicating higher sensitivity for overlapping targets. ... Xenium5K produced ~ threefold fewer transcripts per gene, consistent with reduced per-gene sensitivity."
> — Results, Effect of panel size · bears on: claim 10 · broader panel costs per-gene sensitivity (~3x fewer transcripts/gene) on matched targets.

> "MYC expression in the colorectal adenocarcinoma sample retained its overall spatial localization, but was markedly sparser in Xenium5K, leading to diferences in the proportion of cancer cells classifed as MYC-positive: 70% in XeniumMT versus 30% in Xenium5K (Fig. 4d). Tese discrepancies underscore how panel size can infuence downstream biological interpretation."
> — Results, Effect of panel size · bears on: claim 9, claim 10 · panel-size choice flips a biological readout (70% vs 30% MYC+).

> "In summary, our comparison of the Xenium Multi-Tissue and 5 K panels revealed a clear trade-of between gene coverage and per-gene sensitivity. While the larger panel improved cell type annotation and enabled deeper immune subtyping, it exhibited lower transcript detection efciency and higher sparsity."
> — Results, Effect of panel size · bears on: claim 10, axis A · explicit coverage-vs-sensitivity trade-off statement.

> "Te platforms evaluated thus far require a trade-of between spatial resolution and transcriptome breadth: Visium (v1 and v2) provides whole-transcriptome coverage at multicellular resolution, whereas CosMx and Xenium ofer subcellular resolution but are limited to targeted gene panels. VisiumHD represents a new class of technology that may ofer both: single-cell or subcellular resolution with whole-transcriptome coverage."
> — Results, Subcellular resolution · bears on: claim 10 (resolution × breadth trilemma), axis C, axis A · canonical statement of the resolution-vs-coverage trade-off across platform classes.

> "While this brings the resolution to a sub-cellular level, it has extraordinary computational costs. To mitigate this, coarser bin aggregations ... are typically used ... However, this binning strategy introduces tradeofs: larger bins may include transcripts from multiple cells, while smaller bins may fragment single-cell transcriptomes."
> — Results, Subcellular resolution · bears on: claim 10, claim 9 (computational/standard burden), axis C · VisiumHD resolution comes with compute cost and bin-mixing/fragmentation trade-offs.

> "At 2 µm resolution, most bins contain transcripts from only one cell; in contrast, 8 µm bins frequently capture transcripts from 2–4 cells, and 16 µm bins from 5–10 cells, with variation across tumor types and cell type specifcity."
> — Results, Subcellular resolution · bears on: claim 10, axis C · quantifies how binning conflates cells.

> "Pathway-level inference is challenging in panel-based platforms due to limited gene coverage, which may compromise scoring accuracy or exclude key regulators. In contrast, VisiumHD's whole transcriptome resolution enabled robust hypoxia scoring, revealing heterogeneous expression patterns consistent with those observed in Visium v2 (Fig. 5h)."
> — Results, Subcellular resolution · bears on: claim 4/5 (coverage needed for function), claim 10, axis A · limited modality coverage degrades functional/pathway inference.

> "To assess how well spatial transcriptomics recapitulates protein-level abundance, we generated spatial proteomics data using the Visium v2 Immuno-Oncology panel, which targets 35 proteins. Tis assay, integrated into the standard Visium workfow, uses oligotagged antibodies that bind proteins and are co-barcoded with the spatial capture spots, enabling RNA and protein quantifcation from adjacent sections."
> — Results, RNA–protein correlation · bears on: claim 6 (spatial protein feasibility — but targeted/low-plex), claim 8 (RNA+protein integration), axis A · describes the spatial multi-omics protein arm (only 35 targeted proteins).

> "Across the fve analyzed tumor samples, we observed weak global correlation between transcript and protein levels. Te average Pearson correlation coefcient across all genes and samples was approximately 0.1 (Fig. 6a), substantially lower than the ~ 0.7 average correlation observed in matched bulk tumor samples from the Clinical Proteomic Tumor Analysis Consortium (CPTAC) across seven cancer types (Fig. 6b)."
> — Results, RNA–protein correlation · bears on: claim 4 (modalities non-substitutable), claim 5 · KEY quantitative RNA–protein decoupling in space (~0.1 vs ~0.7 bulk).

> "In the second pattern, correlations were near zero, typically involving genes with low transcript abundance despite protein presence, such as KRT5 in the same lung sample (Fig. 6c, bottom)."
> — Results, RNA–protein correlation · bears on: claim 4 · concrete case where protein is present but transcript is near-absent — RNA cannot stand in for protein.

> "Tis suggests that local microenvironmental efects, post-transcriptional regulation, and protein stability contribute to RNA–protein decoupling in situ, fndings that are masked in aggregate measurements but critical for translational insight."
> — Discussion · bears on: claim 4/5 (orthogonal modality information), claim 7 (microenvironment) · names mechanisms (post-transcriptional regulation, protein stability) that make protein information irreducible to RNA.

> "While bulk data suggests consistent RNA–protein coupling, our spatial analysis demonstrates that these relationships are context-dependent and may vary across regions, cell types, and technologies."
> — Results, RNA–protein correlation (summary) · bears on: claim 4, claim 8, axis C · RNA–protein relationship is spatially/contextually variable, not a fixed scaling.

> "we also examined the impact of RNA quality and observed a strong correlation between DV200 and the average number of genes detected per cell in both platforms, emphasizing the importance of RNA integrity for spatial transcriptomics (Fig. 2i)."
> — Results, CosMx vs Xenium · bears on: claim 9 (QC standard) · sample-quality metric (DV200) drives detection — a QC/standard dependency.

> "However, the rapid proliferation of spatial transcriptomics platforms has introduced a new challenge: selecting the most appropriate platform for a given biological question, tissue type, or translational goal."
> — Discussion · bears on: claim 9 (fragmentation / no standard) · states the platform-proliferation problem our standards argument targets.

> "Prior studies have compared in situ platforms across various tissues [41–44], but few have included matched sequencing-based platforms, and none have systematically profled Visium v1, Visium v2, and VisiumHD within the same framework."
> — Discussion · bears on: claim 9 · prior benchmarks are incomplete/non-matched — motivates harmonized same-sample comparison.

> "By controlling for biological and procedural confounders, we isolate platform-specifc efects and provide a reference dataset for tool developers, methods evaluators, and researchers planning future spatial studies."
> — Discussion · bears on: claim 9, claim 1 (data/benchmark for downstream methods) · positions the harmonized dataset as a reference for comparability.

> "Instead, our aim is to highlight the consequences of technical diferences (such as bin size, segmentation strategy, sampling area, and gene panel design) for downstream data sparsity, resolution, and interpretability. Tese comparisons may also help guide the development of computational methods that are platform-aware and robust to modality-specifc artifacts."
> — Discussion · bears on: claim 9, claim 1, claim 10 · catalogs the technical knobs that make cross-dataset data non-interchangeable; calls for platform-aware methods.

> "First, spatial transcriptomics is a fast-moving feld, and our data refect the capabilities of each platform as of mid-2025. ... Second, while we included several major platforms, our study does not cover other important technologies such as MERFISH, Slide-seq, or Stereo-seq. Tird, although we processed serial sections from the same FFPE blocks when possible, some comparisons ... used tissue sections generated at later time points, potentially introducing Z-axis variability."
> — Discussion (limitations) · bears on: claim 9, claim 10 · author-conceded scope/temporal-drift limits of the benchmark.

> "Also, this study was designed as a technical comparison rather than a biological discovery exercise ... while this study ofers a detailed technical reference, it is not intended as a platform recommendation or usage guide [27]."
> — Discussion (limitations) · bears on: claim 9 · authors explicitly decline to set a usage standard/recommendation — a boundary, and a counter-line on whether this paper itself supplies the standard.

> "Platforms must demonstrate reproducibility, regulatory compliance, and integration with standard pathology workfows, particularly in FFPE tissues. ... As spatial -omics continues to expand into chromatin accessibility, spatial epigenomics, and multimodal proteogenomics, the need for rigorous, same-sample comparisons will only grow."
> — Discussion (outlook) · bears on: claim 9, claim 8 (multimodal integration) · argues reproducibility/standardization and same-sample benchmarking are prerequisites for translation.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data/benchmark bottleneck for downstream methods | "By controlling for biological and procedural confounders, we isolate platform-specifc efects and provide a reference dataset…" / Discussion | nuances |
| Claim 2 — scRNA-seq loses spatial info | "these methods require dissociation of the tissue, thereby destroying the spatial relationships…" / Background; "Spatial omics technologies bridge this gap…" | supports |
| Claim 3 — destructive measurement / temporal | — (FFPE snapshots; no time course addressed) | — |
| Claim 4 — modalities orthogonal, RNA can't substitute protein | "weak global correlation … approximately 0.1 … vs ~0.7 … CPTAC" / RNA–protein; "low transcript abundance despite protein presence, such as KRT5" | supports |
| Claim 5 — protein/other modalities indispensable for function/phenotype | "local microenvironmental efects, post-transcriptional regulation, and protein stability contribute to RNA–protein decoupling" / Discussion; hypoxia scoring needs whole transcriptome | supports |
| Claim 6 — high-throughput spatial proteomics feasible | "Visium v2 Immuno-Oncology panel, which targets 35 proteins … oligotagged antibodies … co-barcoded" / RNA–protein | nuances (only targeted 35-plex) |
| Claim 7 — microenvironment/spatial context shapes cell state | "spatial organization infuences cell signaling, immune infltration, and therapeutic response" / Background | supports |
| Claim 8 — multimodal provides orthogonal info, needs integration | "spatial co-profling of RNA and protein reveals diverse expression relationships…"; "need for rigorous, same-sample comparisons will only grow" | supports |
| Claim 9 — data silos / cross-paper incomparability / lack of standards | "selecting the most appropriate platform…"; "few have included matched sequencing-based platforms"; negative-probe 10.31% vs 0.06%; R=0.93 vs 0.86; sampling 5–55% vs true 22% | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "trade-of between spatial resolution and transcriptome breadth…"; "trade-of between gene coverage and per-gene sensitivity"; optical crowding; binning trade-offs | supports |
| Axis A — modality (measure what) | RNA–protein decoupling; targeted vs whole-transcriptome panels; DNA/epigenome/RNA/protein spatial modalities | supports / nuances |
| Axis B — temporal | — (not addressed; fixed FFPE) | — |
| Axis C — spatial (subcellular→cell→microenvironment) | dissociation destroys spatial architecture; subcellular imaging vs spot/bin resolution; scanned-area sampling bias | supports |
| Standard / integration (cross-cutting) | harmonized same-sample benchmark; QC (DV200, negative-probe rate); platform-aware methods; reproducibility/regulatory for translation | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table (Fig. 1b summary, p.~Results) | Platform characteristics: Visium v1 (55 µm, 17,943 genes, no segmentation), Visium v2/CytAssist (55 µm, 18,085 genes; + 35-protein panel), VisiumHD (2 µm, 18,085 genes), Xenium Multi-Tissue (single-cell, 377 genes), Xenium Prime (single-cell, 5,000 genes), CosMx (single-cell, 1,000 genes). |
| Post-filter dataset sizes (Results text) | 18,672 spots (Visium v1); 33,117 spots (Visium v2); 2,551,540 8 µm bins (VisiumHD); 667,916 cells (CosMx); 5,809,890 cells (Xenium). |
| Fig. 1c–d | Visium v2 vs v1: ~2,000 vs ~200 detected genes; ACTA2 colorectal spatial pattern. |
| Fig. 2 | CosMx vs Xenium: cell counts (Xenium +5–30%), cell area, genes/transcripts per cell (All vs 125 shared "Int"), Visium v2 correlation (R 0.93 vs 0.86), DV200 vs genes/cell. |
| Fig. 3 | Cell-type recovery/composition CosMx vs Xenium; FOV sampling simulation (cancer cells 5–55% vs true 22%); fibroblast→cancer misclassification 71.6% vs 10.2%; endothelial 8.51% vs 28.7%; MMP7 panel-content example. |
| Fig. 4 | Xenium 377-gene (XeniumMT) vs 5,000-gene (Xenium5K): genes/transcripts per cell (225 shared), Visium v2 correlation R 0.92–0.93, ~3x fewer transcripts/gene in 5K, MYC+ 70% vs 30%, ovarian misclassification 12% vs <1%. |
| Fig. 5 | VisiumHD: bin-size simulation (2/8/16 µm cell mixing), correlation to Visium v2 (R>0.97) and Xenium (R>0.85), UMI density ~3x lower than Visium v2 / ~15x lower than Xenium, hypoxia pathway scoring. |
| Fig. 6 | RNA–protein concordance: spatial Pearson ~0.1 vs bulk CPTAC ~0.7 (7 cancer types); three patterns (ITGAX positive, KRT5 near-zero, CD68 partial); Xenium cross-validation of CD68. |
| Table S2 (Additional file 3) | Negative probe rates: CosMx ~10.31% vs Xenium 0.06%; comparable for XeniumMT (20 controls) vs Xenium5K (40 controls). |

---

## Primary Sources Behind Key Quotes
- Bulk RNA–protein correlation ~0.7 (CPTAC, computed by this paper from downloaded matrices) → Liang W-W, et al. "Integrative multi-omic cancer profiling…" Cancer Cell. 2023;41:1567-1585.e7 — ref [53].
- Spatial omics "preserving spatial architecture" framing → Moses L, Pachter L. "Museum of spatial transcriptomics." Nat Methods. 2022;19:534–46 — ref [13].
- Optical crowding at high panel density → Eng C-HL, et al. "Transcriptome-scale super-resolved imaging in tissues by RNA seqFISH+." Nature. 2019;568:235–9 — ref [35].
- Visium / sequencing-based ST origin → Ståhl PL, et al. Science. 2016;353:78–82 — ref [16].
- CosMx (SMI) platform → He S, et al. Nat Biotechnol. 2022;40:1794–806 — ref [20].
- Xenium platform → Janesick A, et al. Nat Commun. 2023;14:8353 — ref [23].
- Cell segmentation alternative (Baysor) → Petukhov V, et al. Nat Biotechnol. 2022;40:345–54 — ref [28].
- Bin-to-cell reconstruction (Bin2Cell) → Polański K, et al. Bioinformatics. 2024;40:btae546 — ref [36].
- Authors' own "Practical Guide to Spatial Transcriptomics" (cited as the usage-guide they decline to be) → Porta-Pardo E, Grases D. 2025. Preprint doi:10.20944/preprints202504.1450.v1 — ref [27].

---

## Flags
- [ ] Metadata unverified: Journal name "Genome Biology" is **inferred from the DOI prefix s13059** (BMC/Springer Nature, editor "Claudia Feng", Publisher's Note "Springer Nature") — the journal name is **not printed verbatim** in the source body. Volume, issue, and page numbers are not present in the cleaned text. DOI itself (10.1186/s13059-026-03937-y) and dates (Received 13 Oct 2025; Accepted 6 Jan 2026; Published online 12 Jan 2026) ARE printed.
- [ ] Source inconsistency: line 343 prints the code Zenodo DOI as "10.5281/zenodo.1801661" (8 digits) while refs [54]–[58] give 17–18-digit Zenodo IDs (e.g. 17986017, 18016691); the inline one is likely truncated by OCR.
- [ ] Source inconsistency: reference list skips number "8" (ref [7] Rooney is followed by an unnumbered "Reardon B, et al." then "9. Rubio-Perez") — the Reardon entry is presumably ref [8].
- [ ] OCR artifacts throughout the cleaned source (missing "fi/fl" ligatures, "Tis/Te" for "This/The", "10 Genomics" for "10x Genomics", "$95~^{\circ}C$"-style math markup). Quotes reproduced as-is for greppability; check the raw before final typesetting.
- [ ] Scope note: this paper does NOT address the temporal axis (claim 3 / axis B) — all data are fixed FFPE snapshots; "Z-axis variability" refers to serial-section depth, not time.
- [ ] Scope note: the spatial-protein arm is a **targeted 35-protein** antibody panel, not high-throughput/discovery proteomics — relevant when citing for claim 6 (spatial proteomics feasibility) so the writer does not overstate plex.
- [ ] Read at source: for the RNA–protein decoupling argument (claim 4), the bulk ~0.7 benchmark traces to Liang et al. 2023 (CPTAC, ref [53]) — cite first-hand rather than via this paper.
