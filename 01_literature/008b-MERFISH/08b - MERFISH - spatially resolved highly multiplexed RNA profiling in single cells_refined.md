# Spatially resolved, highly multiplexed RNA profiling in single cells — Source Index

**Authors:** Kok Hao Chen, Alistair N. Boettiger, Jeffrey R. Moffitt, Siyuan Wang, Xiaowei Zhuang
**Journal / Venue:** Science, 2015, 348(6233):aaa6090
**DOI:** doi:10.1126/science.aaa6090
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/08b - MERFISH - spatially resolved highly multiplexed RNA profiling in single cells_cleaned.md

---

## In One Sentence
The paper introduces MERFISH (multiplexed error-robust fluorescence in situ hybridization), a single-molecule imaging method that uses combinatorial labeling, sequential hybridization, and error-correcting binary codes (modified Hamming-distance-4 and Hamming-distance-2) to count and spatially localize 140 and 1001 RNA species simultaneously in hundreds of individual fixed human fibroblast (IMR90) cells, with copy numbers validated against bulk RNA-seq and conventional smFISH.

## Orientation (non-binding)
This is an imaging-based, in-situ transcriptomics method paper: it preserves the native spatial context that dissociation-based scRNA-seq discards, so it most likely feeds Claim 2 (scRNA-seq loses spatial information — here the recovery side) and Axis C (spatial: subcellular → cell). It also extensively documents the throughput-vs-accuracy-vs-density trade-offs of single-cell measurement (Claim 10 trilemma). Note two double-edged points the downstream agent may deploy either way: (i) MERFISH measures RNA only (within the narrow-modality paradigm the thesis critiques — Axis A / Claim 4), yet it shows RNA spatial distribution encodes information about the encoded protein's destination/function; (ii) it images chemically fixed cells, i.e. a destructive snapshot that cannot follow the same cell over time (Axis B / Claim 3 nuance), so it recovers space but not live temporal trajectory.

---

## Load-Bearing Excerpts

> "Here, we report multiplexed error-robust fluorescence in situ hybridization (MERFISH), a single-molecule imaging approach that allows the copy numbers and spatial localizations of thousands of RNA species to be determined in single cells."
> — Abstract · bears on: Claim 2, Axis C (spatial) · States the method jointly measures copy number and spatial localization in single cells.

> "System-wide analyses of the abundance and spatial organization of RNAs in single cells promise to transform our understanding in many areas of cell and developmental biology, such as the mechanisms of gene regulation, the heterogeneous behavior of cells, and the development and maintenance of cell fate (1)."
> — Introduction · bears on: Claim 2, Axis C (spatial) · Frames spatial organization (not only abundance) as essential to understanding cell behavior.

> "Single-molecule fluorescence in situ hybridization (smFISH) has emerged as a powerful tool for studying the copy number and spatial organization of RNAs in single cells either in isolation or in their native tissue context (2, 3)."
> — Introduction · bears on: Claim 2, Axis C (spatial) · Positions in-situ imaging as the route to RNA spatial organization in native context.

> "Taking advantage of its ability to map the spatial distributions of specific RNAs with high resolution, smFISH has revealed the importance of subcellular RNA localization in diverse processes such as cell migration, development, and polarization (4–8)."
> — Introduction · bears on: Axis C (spatial, subcellular) · Asserts subcellular RNA localization is functionally important.

> "However, application of the smFISH approach to many systems-level questions remains limited by the number of RNA species that can be simultaneously measured in single cells."
> — Introduction · bears on: Claim 10 (trilemma), Claim 2 · The throughput limit of spatial imaging is the bottleneck being addressed.

> "State-of-the-art efforts by using combinatorial labeling with either color-based barcodes or sequential hybridization have enabled simultaneous measurements of 10 to 30 different RNA species in individual cells (16–19), yet many interesting biological questions would benefit from the measurement of hundreds to thousands of RNAs within a single cell."
> — Introduction · bears on: Claim 10 (trilemma), Claim 2 · Quantifies prior multiplexing ceiling (10–30) vs. the needed scale.

> "...analysis of how the expression profile of such a large number of RNAs vary from cell to cell and how these variations correlate among different genes could be used to systematically identify coregulated genes and map regulatory networks ... and RNA profiling of individual cells in native tissues could allow in situ identification of cell type."
> — Introduction · bears on: Claim 2, Claim 7, Axis C (spatial) · Names in-situ cell-type identification in native tissue as a target use.

> "Combinatorial labeling that identifies each RNA species by multiple (N) distinct signals offers a route to rapidly increase the number of RNA species that can be probed simultaneously ... not only does the number of addressable RNA species increases exponentially with N, but the detection error rates also grow exponentially with N (Fig. 1, B to D)."
> — Combinatorial labeling with error-robust encoding schemes · bears on: Claim 10 (trilemma) · Throughput and error scale together — the core measurement trade-off.

> "With just 16 hybridizations, more than 64,000 RNA species—which should cover the entire human transcriptome, including both messenger RNAs (mRNAs) and noncoding RNAs (20)—could be identified (Fig. 1B, black symbols). However, as N increases, the fraction of RNAs properly detected (the calling rate) would rapidly decrease and ... the fraction of RNAs that are identified as incorrect species (the misidentification rate) would rapidly increase..."
> — Combinatorial labeling with error-robust encoding schemes · bears on: Claim 10 (trilemma), Claim 2 · In principle whole-transcriptome reach, but accuracy collapses without error-robust codes.

> "Using these error rates, we estimated an ~80% calling rate for individual RNA species after error correction— ~80% of the fluorescent spots corresponding to a RNA species were decoded correctly (fig. S6E)."
> — Measuring 140 genes with MERFISH by use of a 16-bit MHD4 code · bears on: Claim 1, Claim 10 · Quantifies detection efficiency of the error-correcting scheme.

> "The copy numbers of individual RNA species per cell measured with these two codebooks showed excellent agreement with a Pearson correlation coefficient of 0.94 (Fig. 2G), indicating that the choice of encoding scheme did not bias the measured counts."
> — Measuring 140 genes with MERFISH by use of a 16-bit MHD4 code · bears on: Claim 9 (comparability/standard), Claim 1 · Demonstrates measurement is robust to encoding choice (a within-method reproducibility check).

> "The ratio of the copy numbers determined by these two approaches was 0.82 T 0.06 (mean T SEM across the 15 measured RNA species) ... Given that the agreement between the MERFISH and conventional smFISH results extended to the genes at the lowest measured abundance (<1 copy per cell), we estimate that our measurement sensitivity was better than 1 copy per cell."
> — Measuring 140 genes with MERFISH by use of a 16-bit MHD4 code · bears on: Claim 1, Claim 9 · Cross-method validation (vs. smFISH) and single-copy sensitivity claim. ("T" is an OCR rendering of ±; see Flags.)

> "Our imaging results correlated remarkably well with bulk sequencing results, with a Pearson correlation coefficient of 0.89 (Fig. 2H)."
> — Measuring 140 genes with MERFISH by use of a 16-bit MHD4 code · bears on: Claim 1, Claim 9 (comparability) · Imaging copy numbers agree with an orthogonal bulk-seq platform.

> "At the single-cell level, one can take advantage of the natural stochastic fluctuations in gene expression for such analysis and can thus study multiple regulatory networks without having to stimulate each of them individually. Such covariation analysis can constrain regulatory networks, suggest new regulatory pathways, and predict function for unannotated genes based on associations with covarying genes (11, 28)."
> — Analysis of expression covariation among different genes · bears on: Claim 3 (temporal nuance), Claim 1 · Regulation is inferred from a static population's cell-to-cell variation, not from tracking cells over time.

> "two of these particularly 'noisy' genes, MKI67 and CENPF, are both annotated as cell-cycle related genes (26), and based on their bimodal expression (Fig. 3C), we propose that their transcription is strongly regulated by the cell cycle."
> — High-throughput analysis of cell-to-cell variation in gene expression · bears on: Claim 3 (temporal nuance) · Cell-cycle dynamics are inferred from a snapshot distribution (bimodality), not from a real time course.

> "As an imaging-based approach, MERFISH also allowed us to investigate the spatial distributions of many RNA species simultaneously. Several patterns emerged from the visual inspection of individual genes, with some RNA transcripts enriched in the perinuclear region, some enriched in the cell periphery, and some scattered throughout the cell (Fig. 4A)."
> — Mapping spatial distributions of RNAs · bears on: Axis C (spatial, subcellular), Claim 2 · Direct evidence of measurable subcellular RNA spatial patterning.

> "Thus, we propose that the spatial pattern that we observed for these mRNAs reflects their cotranslational enrichment at the ER. The enrichment of these mRNAs in the perinuclear region (Fig. 4, C and D, light blue), where the rough ER resides, supports this conclusion."
> — Mapping spatial distributions of RNAs · bears on: Axis C (spatial), Claim 4 (modality cross-link) · Subcellular RNA position reports on the encoded protein's secretory/translation fate — spatial info carries functional meaning.

> "This group [II] was enriched with GO terms such as cortical actin cytoskeleton, actin filament binding, and cell-cell adherens junction ... The enrichment of group II mRNAs in the peripheral region of the cells ... suggests that the spatial distribution of the group II genes might be related to the distribution of actin cytoskeleton mRNAs."
> — Mapping spatial distributions of RNAs · bears on: Axis C (spatial), Claim 4 (modality cross-link) · A second spatial RNA group whose localization tracks the function of the encoded proteins.

> "We pursued an alternative approach ... by relaxing the error correction requirement but keeping the error-detection capability. For example, by reducing the Hamming distance from 4 to 2, we could use all 14-bit words that contain four 1 bits to encode 1001 genes and probe these RNAs with only 14 rounds of hybridization. However, because a single error can produce a word equally close to two different code words, error correction is no longer possible for this modified Hamming-distance-2 (MHD2) code. Hence, we expect the calling rate to be lower and the misidentification rate to be higher with this encoding scheme."
> — Measuring 1001 genes with MERFISH by use of a 14-bit MHD2 code · bears on: Claim 10 (trilemma) · Explicit accuracy-for-throughput trade: more genes per round costs error correction.

> "Thus, the lack of error correction in the MHD2 code reduced the calling rate to ~30% of that of the MHD4 code ... The total count of these RNAs per cell was ~1/3 of that observed in the 140-gene measurements."
> — Measuring 1001 genes with MERFISH by use of a 14-bit MHD2 code · bears on: Claim 10 (trilemma), Claim 1 · Quantifies the sensitivity cost of scaling to ~1000 genes.

> "RNA copy numbers measured from these 73% RNA species showed excellent correlation with our bulk RNA sequencing results (Pearson correlation coefficient r = 0.76) (Fig. 5B, black)."
> — Measuring 1001 genes with MERFISH by use of a 14-bit MHD2 code · bears on: Claim 1, Claim 9 (comparability) · 1001-gene copy numbers still agree with bulk-seq, though less tightly than the 140-gene MHD4 run.

> "In the 1001-gene experiments, the cell nucleus generally contained too much fluorescent signal to allow identification of individual RNA molecules. These bright regions were excluded from all subsequent analysis."
> — Construction of measured words (Methods) · bears on: Claim 10 (trilemma), Axis C (spatial) · Local molecular density limits which compartments/transcripts can be resolved.

> "Of the two encoding schemes presented here, the MHD4 code is capable of both error detection and error correction and hence can provide a higher calling rate and a lower misidentification rate than can the MHD2 code ... MHD2, on the other hand, provides a faster scaling of the degree of multiplexing ... experimenters can set the balance between detection accuracy and ease of multiplexing according to the specific requirements of the experiments."
> — Discussion · bears on: Claim 10 (trilemma) · States the accuracy ↔ multiplexing balance as a tunable design choice.

> "On the basis of our imaging and sequencing results, we estimate that including the whole transcriptome of the IMR90 cells would lead to a total RNA density of ~200 molecules/mm³. Using our current imaging and analysis methods, we could resolve 2 to 3 molecules/mm³ per hybridization round (38), which would reach a total RNA density of ~20 molecules/mm³ after 32 rounds of hybridization. This density should allow all but the top 10% most expressed genes to be imaged simultaneously..."
> — Discussion · bears on: Claim 10 (trilemma) · Molecular-crowding ceiling on how much of the transcriptome can be imaged at once. (Units printed as "mm³" are almost certainly µm³; see Flags.)

> "Last, theoretical predictions (17) indicate that the use of superresolution imaging (41, 42) could increase the resolvable density to ~10^5 molecules/mm³, which should be ample to address the entire transcriptome ... However, RNAs in densely packed structures, such as p-bodies and stress granules, may still elude measurement."
> — Discussion · bears on: Claim 10 (trilemma), Axis C (spatial) · A conceded residual limit: the densest RNA structures may remain unmeasurable.

> "Given its ability to quantify RNAs across a wide range of abundances without amplification bias while preserving native context, we envision that MERFISH will enable many applications of in situ transcriptomic analyses of individual cells in culture or complex tissues."
> — Discussion · bears on: Claim 2, Axis C (spatial), Claim 1 · Summary claim: amplification-bias-free quantification while preserving spatial/native context.

> "Human primary fibroblasts (American Type Culture Collection, IMR90) ... Cells were fixed for 20 min in 4% paraformaldehyde (Electron Microscopy Sciences, 15714) in 1× phosphate buffered saline (PBS; Ambion, AM9625) at room temperature..."
> — Sample preparation and labeling with encoding probes (Methods) · bears on: Claim 3 (temporal nuance), Axis B (temporal) · Measurement is on chemically fixed cells — a single destructive snapshot, not a live time course of the same cell.

> "We found that only a small fraction, 15 T 1% (mean T SEM across six different RNA species) of RNA molecules were outside the imaging range of a fixed focal plane without z-scanning."
> — MERFISH imaging (Methods) · bears on: Claim 10 (trilemma), Axis C (spatial) · Quantifies coverage loss from 2D wide-field imaging without z-sectioning.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 (scRNA-seq loses spatial; spatial-omics methods) | "MERFISH ... copy numbers and spatial localizations" / Abstract; "preserving native context" / Discussion | supports (recovery side) |
| Claim 1 (data quality; quantification) | "~80% calling rate" / 140-gene; "without amplification bias" / Discussion; "r = 0.89" | supports |
| Claim 3 (destructive measurement → no paired temporal observation) | "Cells were fixed ... 4% paraformaldehyde" / Methods; "natural stochastic fluctuations" / covariation | nuances |
| Claim 4 (modalities orthogonal / RNA-only insufficient) | "cotranslational enrichment at the ER" / spatial; (method measures RNA only) | nuances |
| Claim 7 (spatial organization shapes cell state) | "in situ identification of cell type" / Introduction; spatial GO groups / Fig. 4 | supports |
| Claim 9 (comparability / standards / QC) | "two codebooks ... 0.94" / 140-gene; "r = 0.76" vs bulk / 1001-gene; "0.82 T 0.06" vs smFISH | supports |
| Claim 10 (resolution × throughput × destructiveness trilemma) | "error rates also grow exponentially with N"; "balance between detection accuracy and ease of multiplexing"; "~200 molecules/mm³" density | supports |
| Axis A (modality) | RNA-only transcriptome imaging; spatial pattern infers protein fate | nuances |
| Axis B (temporal) | fixed-cell snapshot; cell-cycle inferred from bimodality | challenges (recovers space, not time) |
| Axis C (spatial) | perinuclear vs peripheral RNA enrichment / Fig. 4; subcellular localization | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | MERFISH concept: combinatorial labeling; modeled addressable-species count, calling rate, and misidentification rate vs. number of bits N for simple binary, HD4, and MHD4 codes (per-bit error rates 10% for 1→0, 4% for 0→1); two-step encoding/readout probe scheme. |
| Fig. 2 | 140-gene measurement (16-bit MHD4, IMR90): single-molecule images across 16 hyb rounds; decoded binary words; copy number with/without error correction; confidence-ratio separation of 130 RNAs vs 10 controls; two-codebook agreement r=0.94 (P=1×10⁻⁵³); MERFISH vs bulk-seq r=0.89 (P=3×10⁻³⁹). |
| Fig. 3 | Cell-to-cell variation and pairwise covariation (140 genes): Fano factors increasing with mean abundance; correlated/anticorrelated gene pairs; hierarchical clustering into 7 groups; GO-term enrichment per group. |
| Fig. 4 | Spatial distributions (140 genes): perinuclear vs peripheral vs scattered RNA patterns; clustering into spatial Group I (perinuclear, secretion/ER) and Group II (peripheral, actin cytoskeleton); distance-to-nucleus/edge quantification; GO enrichment. |
| Fig. 5 | 1001-gene measurement (14-bit MHD2): decoded molecules per cell (~430 in shown cell, ~200 cells); copy number vs bulk-seq r=0.76 (73% high-confidence genes) and r=0.65 (remaining 27%); 107 shared genes vs 140-gene run r=0.89. |
| Fig. 6 | Covariation analysis (1001 genes): ~100 correlated gene groups, nearly all with significant GO enrichment; function hypotheses for 46 unannotated RNAs + 61 transcription factors/partially annotated proteins. |
| Key numbers | Prior multiplexing ceiling 10–30 genes; this work 140 and 1001 genes; ~80% calling rate (MHD4); MHD2 calling rate ~1/3 of MHD4; ~192 (140-gene) / ~94 (1001-gene) encoding probes per RNA; readout hyb ~15 min vs >10 h direct; full experiment ~20 h; sensitivity <1 copy/cell; ~15% RNA outside fixed focal plane; ~5% RNA in nucleus. |

---

## Primary Sources Behind Key Quotes
- Spatially resolved transcriptomics review (context for the whole spatial-omics framing) → N. Crosetto, M. Bienko, A. van Oudenaarden, *Nat. Rev. Genet.* 16:57–66 (2015), ref 1.
- Foundational smFISH (single-RNA detection) → A. M. Femino et al., *Science* 280:585–590 (1998), ref 2; A. Raj et al., *Nat. Methods* 5:877–879 (2008), ref 3.
- Prior 10–30-plex combinatorial / sequential FISH (the multiplexing ceiling claim) → J. M. Levsky et al., *Science* 297:836–840 (2002), ref 16; E. Lubeck & L. Cai, *Nat. Methods* 9:743–748 (2012), ref 17; M. J. Levesque & A. Raj, *Nat. Methods* 10:246–248 (2013), ref 18; E. Lubeck et al., *Nat. Methods* 11:360–361 (2014), ref 19.
- Subcellular RNA localization importance → reviews refs 4–8 (e.g., A. R. Buxbaum, G. Haimovich, R. H. Singer, *Nat. Rev. Mol. Cell Biol.* 16:95–109, 2015, ref 8).
- Fano-factor / promoter-switching noise model → A. Sanchez & I. Golding, *Science* 342:1188–1193 (2013), ref 24.

---

## Flags
- [ ] Metadata verified: title, authors, venue (Science 348(6233):aaa6090), DOI (10.1126/science.aaa6090), and dates (received 5 January 2015; accepted 19 March 2015; published online 9 April 2015) are all explicit in the source text; data deposited GSE67685 and http://zhuang.harvard.edu/merfish.
- [ ] OCR artifacts in source (do not treat as authors' wording): "T" repeatedly stands for the ± symbol (e.g., "0.82 T 0.06", "15 T 1%"); RNA-density and imaging-region units printed as "mm³"/"mm" are almost certainly µm³/µm (per cubic micron; 40 × 40 µm region; 167 nm pixel) — a quantitative read should use the µ-scale interpretation.
- [ ] Scope note: this paper measures RNA only, on a single fixed cultured cell line (IMR90); it is the primary MERFISH method paper (cite it first-hand for the method itself). Protein/spatial-proteomic extensions of MERFISH are out of this paper's scope.
- [ ] Read at source for the perspective's spatial-omics review framing: Crosetto et al. *Nat. Rev. Genet.* 16:57–66 (2015), ref 1 (a dedicated "spatially resolved transcriptomics" review, more citable for Claim 2 than this method paper).
