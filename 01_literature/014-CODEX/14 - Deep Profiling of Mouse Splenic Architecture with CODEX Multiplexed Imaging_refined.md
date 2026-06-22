# Deep Profiling of Mouse Splenic Architecture with CODEX Multiplexed Imaging — Source Index

**Authors:** Yury Goltsev, Nikolay Samusik, Julia Kennedy-Darling, Salil Bhate, Matthew Hale, Gustavo Vazquez, Sarah Black, and Garry P. Nolan
**Journal / Venue:** Cell, 2018 (volume/issue/pages not stated in text — see Flags)
**DOI:** doi:10.1016/j.cell.2018.07.010
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/14 - Deep Profiling of Mouse Splenic Architecture with CODEX Multiplexed Imaging_cleaned.md

---

## In One Sentence
The paper introduces CODEX (co-detection by indexing), an iterative DNA-barcode / primer-extension method that turns a standard three-color fluorescence microscope into a highly multiplexed (up to 66 antigens) single-cell, in-situ protein imaging platform, and applies it to ~700,000 cells of normal (BALBc) and lupus (MRL/lpr) mouse spleen to map cell types, cellular neighborhoods ("i-niches"), and disease-driven architectural change — finding that a cell's surface-protein expression is strongly conditioned by which cells surround it.

## Orientation (non-binding)
This is a spatial single-cell proteomics method paper. It most likely feeds the **spatial axis (C)**, the **protein modality (Axis A)**, **Claim 6** (high-throughput spatial proteomics is feasible), **Claim 7** (spatial organization / microenvironment alters cell state and perturbation response), and **Claim 2** (in-situ imaging as the alternative to dissociation, which discards spatial context). It also touches **Claim 9** (cross-platform comparability via identical-panel CyTOF benchmarking; release of a large public spatial reference dataset) and **Claim 10** (non-destructive in-situ measurement vs destructive dissociation; multiplexing bounded by imaging speed/resolution). It can serve BOTH as positive evidence ("we can measure protein + space at single-cell resolution, and neighborhood demonstrably shapes phenotype") and as a foil/limitation source (static fixed-tissue snapshot; disease "progression" reconstructed cross-sectionally, not by paired temporal tracking — bearing on Claim 3). Downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "We observed an unexpected, profound impact of the cellular neighborhood on the expression of protein receptors on immune cells."
> — SUMMARY · bears on: Claim 7, Axis C (spatial) · the paper's headline finding that local tissue context shapes a cell's surface-protein expression.

> "An algorithmic pipeline for single-cell antigen quantification in tightly packed tissues was developed and used to overlay well-known morphological features with de novo characterization of lymphoid tissue architecture at a single-cell and cellular neighborhood levels."
> — SUMMARY · bears on: Claim 6, Axis C · single-cell protein quantification directly from intact tissue images.

> "Accurate highly multiplexed singlecell quantification of membrane protein expression in densely packed lymphoid tissue images (which was once deemed impossible [Gerner et al., 2012]) was achieved using polymerase-driven incorporation of dye-labeled nucleotides into the DNA tag of oligonucleotide-conjugated antibodies, combined with an image-based expression estimation algorithm."
> — INTRODUCTION · bears on: Claim 6, Axis A (protein) · in-situ single-cell membrane-protein quantification in crowded tissue is demonstrated as achievable.

> "To validate the quantitative performance of CODEX, cells freshly isolated from mouse spleens were co-analyzed by mass-cytometry (CyTOF) and CODEX using identical 24-antibody panels (Table S1). Use of the same antibody clones and the same splenocyte preparation ensured the validity of comparisons."
> — Benchmarking CODEX · bears on: Claim 9 · cross-platform validation with controlled identical panels and sample prep.

> "Antigen co-expression signals from CODEX, obtained from image segmentation (see STAR Methods), were consistently similar to CyTOF (Figure 2B, for direct comparability, both CODEX and CyTOF data are plotted on a linear scale)."
> — Benchmarking CODEX · bears on: Claim 9 · imaging-derived protein readouts match a dissociated gold-standard cytometry platform.

> "Compared to CyTOF data on splenocytes isolated from non-enzymatically homogenized spleen, CODEX in situ analysis produced a similar distribution of cell counts for major cell type. Yet being a non-disruptive technique CODEX identified larger numbers of resident and stromal cell types such as erythroblasts and F4/80 macrophages than CyTOF did (Figure 3E)."
> — Benchmarking CODEX · bears on: Claim 2, Claim 10, Axis C · dissociation-based cytometry under-recovers resident/stromal cell types that the non-disruptive in-situ method captures.

> "In contrast to dissociated cells spreads (Figure 2A), cells in tissue sections are adjacent to each other—with large fractions of membranes in direct contact (Figure 2C). Therefore, neighboring cells can contaminate each other's signals during the quantification phase (Figure 2D)."
> — Benchmarking CODEX · bears on: Claim 10, Axis C · technical trade-off of single-cell quantification inside intact tissue (spatial spillover) that dissociation avoids.

> "When visualized as heatmaps, this metric revealed a significant non-random distribution of cells in the spleen. In the majority of cases, cell types were either selectively associating or avoiding each other (red or blue on the heatmap) pointing to prevalence of specific cell-to-cell interactions in shaping the spleen architecture."
> — Pairwise and Combinatorial (i-niches) Statistics · bears on: Claim 7, Axis C · spatial cell arrangement is structured, not random.

> "Unexpectedly, a consistently high degree of association was observed between the cells of the same phenotypic class (Figure 3G, red diagonal), suggesting that homotypic adhesion constitutes a major force driving the architecture of immune tissue."
> — Pairwise and Combinatorial (i-niches) Statistics · bears on: Claim 7, Axis C · a candidate organizing principle of tissue spatial architecture.

> "Taken together, we see that surface-marker expression alone is insufficient to associate many cell subsets with a given tissue subcompartment (e.g., CD4+ T cells can be found both in the PALS and in the red pulp). However, i-niche designation does provide such mapping data"
> — Pairwise and Combinatorial (i-niches) Statistics · bears on: Claim 7, Claim 8, Axis C · marker identity alone does not localize a cell; spatial-neighbor information is needed.

> "We observed that for several index cell types (e.g., for B and T cells) there was significant biasing of the surface-marker expression depending on the i-niche in which the index cell resides"
> — Cell-Surface-Marker Expression Depends on Local Neighborhood · bears on: Claim 7, Axis C · neighborhood biases a cell's protein-marker expression.

> "These observations suggest that the spread of the CD79b-B220 levels as well as of other marker levels on splenic B cells could be, to a large degree, accounted for by the niche composition around those B cells—and that the expression levels on these cells might be influenced by (or influences) the cells in their immediate surrounding."
> — Cell-Surface-Marker Expression Depends on Local Neighborhood · bears on: Claim 7, Axis C · marker-expression variance often attributed to noise is in part explained by spatial neighborhood.

> "Notably, adding the i-niche information as a dependent variable significantly improved the fitness of the model for all markers (Table S4) with highest improvement F-values for CD90, B220, CD21/35, and ERTR7 and the lowest prediction rates for Ly6G, CD5, CD11b, CD5, and TCR-b."
> — Cell-Surface-Marker Expression Depends on Local Neighborhood · bears on: Claim 7, Axis C · quantitative regression result: neighborhood improves prediction of marker expression for all markers (effect size varies by marker).

> "This result quantitatively demonstrates that the i-niche (neighbors) determines a significant proportion of variance in the expression of certain markers."
> — Cell-Surface-Marker Expression Depends on Local Neighborhood · bears on: Claim 7, Axis C · spatial neighbors account for a measurable share of protein-expression variance.

> "Further, tissue locale (i-niches) is a powerful indicator of potential differential function (to the extent tissue locale drives function), and these deterministic changes in surface marker protein expression are surrogate indicators of this locale or function."
> — Cell-Surface-Marker Expression Depends on Local Neighborhood · bears on: Claim 7, Axis C · spatial location is proposed as an indicator of functional state.

> "We found some examples supporting that, whereby the proximity of CD4 T cells to B220+ DN T leads to CD4 T cell activation in spleens of MRL/lpr mice: Figure 6C shows increased levels of CD27 expression in CD4 T cells present in i-niches dominated by B220+ DN T cells"
> — Reorganization of Cells in Disease-Associated Tissue Substructures · bears on: Claim 7, Axis C · contact-dependent (neighbor-driven) change in a cell's activation-marker expression — a spatial-microenvironment effect on cell state (example: mouse lupus).

> "The perturbation introduced to normal splenic composition with MRL/lpr genotype allowed us to examine the mechanisms implicated in transition from normal to diseased spleen."
> — Disease-Driven Change in Cell Counts Determines the Frequency of Specific Cell-to-Cell Contacts · bears on: Claim 7 · disease framed explicitly as a perturbation read out in spatial architecture.

> "These and other changes were used to broadly classify the MRL/lpr spleens into early, intermediate, and late disease stages (Figure S3)."
> — Changes in Splenic Composition Associated with Disease Progression · bears on: Claim 3 (nuance) · "progression" is reconstructed from a cross-section of distinct fixed samples/animals, not from paired temporal tracking of one tissue.

> "A simple regularized logistic regression model that considered only average marker expression and did not incorporate spatial information was unable to successfully distinguish patches normal and MRL/lpr spleens, whereas the trained neural network model consistently achieved a 90% precision of classification of image patches during cross-validation."
> — Neural network training and data analysis (STAR Methods) · bears on: Claim 1, Claim 2, Claim 7, Axis C · spatially-informed model succeeds where a model on dissociated/averaged expression fails — spatial context carries classifying signal that averaged expression loses.

> "A consistent performance of CODEX in codetecting up to 66 antigens was demonstrated, and the ''activation primer''-based extension of the system could enable a potentially vast expansion of CODEX multiplexing capacity."
> — DISCUSSION · bears on: Claim 6, Claim 10, Axis A · demonstrated high-plex protein detection (66 antigens) with a route to higher multiplexing.

> "Thus, panel-activator design extends CODEX to a theoretically unlimited multiplexing capacity, bounded only by the speed and resolution of the imaging process itself and the time required for each imaging cycle."
> — Benchmarking CODEX / Primer dependent panels · bears on: Claim 6, Claim 10 · multiplexing ceiling is set by imaging speed/resolution and cycle time — an explicit throughput trade-off.

> "CODEX completes a 30-antibody visualization in approximately 3.5 hr."
> — DISCUSSION · bears on: Claim 10 · concrete throughput figure for the spatial-proteomics measurement.

> "With the help of a simple automated fluidic setup (Figure S7), the CODEX platform can be performed on most three-color fluorescence microscopes with a motorized stage and thereby enable conversion of regular fluorescence microscope into a tool for multidimensional tissue rendering and cell cytometry."
> — DISCUSSION · bears on: Claim 6, Claim 10 · low-cost accessibility of high-plex spatial proteomics on standard instrumentation.

> "for the current method, fresh-frozen tissue was used yet at a cost of testing an extensively broader collection of clones we have recently succeeded in adapting the procedure to formalin fixed paraffin embedded (FFPE) archival tissue (unpublished data). We believe this will open the large retrospective collection of FFPE samples from clinical cohorts to multidimensional cytometric analysis."
> — DISCUSSION · bears on: Claim 6 · scope/availability of spatial-proteomics inputs (toward archival clinical samples).

> "As of today, this algorithm is only applicable to uniformly distributed surface markers. Future changes might be required to accommodate markers that follow a different distribution, i.e., localized to lipid rafts or immune synapses."
> — DISCUSSION · bears on: Claim 10 (nuance), Axis A/C · author-conceded limitation of the in-situ quantification algorithm (sub-cellularly localized markers not yet handled).

> "By this token, the data collected in this study lays the foundation for a pan-cellular reference database defining cellular types not only by identities of proteins expressed, but also by definitions for specific cell-to-cell interactions."
> — DISCUSSION · bears on: Claim 9, Claim 7, Axis C · proposes defining cell types by protein identity AND spatial interaction patterns — a reference-standard ambition.

> "We performed deep characterization here for normal and diseased tissue from such a perspective of cell-cell arrangements and present here, for the research community, a large ( 700,000 cells) public dataset encompassing segmentation, quantification, and, most uniquely, spatial data from normal and diseaseafflicted spleens (http://welikesharingdata.blob.core.windows.net/forshare/index.html)."
> — DISCUSSION · bears on: Claim 9, Axis C · release of a large public single-cell dataset whose distinguishing feature is spatial data.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq / dissociation loses spatial info | "being a non-disruptive technique CODEX identified larger numbers of resident and stromal cell types…" / Benchmarking | supports |
| Claim 6 — high-throughput spatial(temporal) proteomics is feasible | "codetecting up to 66 antigens" / DISCUSSION; "singlecell quantification of membrane protein expression… was achieved" / INTRODUCTION | supports |
| Claim 7 — spatial organization / microenvironment alters cell state & perturbation response | "profound impact of the cellular neighborhood on the expression of protein receptors" / SUMMARY; "adding the i-niche information… significantly improved the fitness of the model for all markers" / §Cell-Surface-Marker; "proximity of CD4 T cells to B220+ DN T leads to CD4 T cell activation" / §Reorganization | supports |
| Claim 8 — multimodal / spatial provides orthogonal info needing integration | "surface-marker expression alone is insufficient to associate many cell subsets with a given tissue subcompartment" / §i-niches Statistics | supports |
| Claim 9 — data silos / cross-platform comparability / standards / reference | "identical 24-antibody panels… same antibody clones and the same splenocyte preparation" / Benchmarking; "lays the foundation for a pan-cellular reference database" / DISCUSSION; "large ( 700,000 cells) public dataset… spatial data" / DISCUSSION | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "theoretically unlimited multiplexing capacity, bounded only by the speed and resolution of the imaging process" / Benchmarking; "neighboring cells can contaminate each other's signals" / Benchmarking; "30-antibody visualization in approximately 3.5 hr" / DISCUSSION | supports / nuances |
| Claim 1 — data is the bottleneck; non-spatial/averaged input loses signal | "logistic regression model that considered only average marker expression and did not incorporate spatial information was unable to… distinguish" / STAR Methods (NN) | supports |
| Claim 3 — destructive measurement cannot observe time in pairs | "classify the MRL/lpr spleens into early, intermediate, and late disease stages" / §Disease Progression (cross-sectional, fixed snapshots — not paired tracking) | nuances / challenges |
| Axis A — protein modality (functional execution layer) | "membrane protein expression… was achieved" / INTRODUCTION; "codetecting up to 66 antigens" / DISCUSSION | supports |
| Axis C — spatial (subcellular → cell → neighborhood → tissue) | "188 nm/pixel resolution… axial resolution 900 nm" / Imaging; "i-niche… ring of first tier neighbors" / §i-niche analysis | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Figure 1 / Video S1 | CODEX schematic: iterative primer-extension rendering of DNA-barcoded antibodies; Klenow-dependent CD4/TCR-b staining validation; CODEX vs conventional antibody staining concordance in spleen. |
| Figure 2 | Accuracy of CODEX quantitation: CODEX vs CyTOF on identical 24-color panel; cell segmentation in tissue; cell-by-cell spatial spillover compensation (~2-fold spillover reduction). |
| Figure 3 / Table S2 | 30-antibody panel; 4 splenic compartments (red pulp, B-follicle, PALS, marginal zone); 734,101 segmented cells; X-shift → 27 phenotypic groups (58 clusters annotated); cell-type interaction (log odds ratio) heatmap. |
| Figure 4 / Table S4 | i-niche definition (ring of first-tier Delaunay neighbors); 100 i-niches by K-means; neighborhood-dependent marker expression; two-feature regression (cell-type identity + i-niche) improves fit for all markers. |
| Figure 5 / Table S3 | Disease vs normal: cell-count changes in 19/27 cell types; cell-count change (R²=0.288) vs interaction-strength change (R²=0.058) as drivers of contact-frequency change; χ² interaction-count > χ² log-odds. |
| Figures 6–7 | Disease-associated i-niche emergence (B220+ DN T, erythroblast, B-cell niches); i-niches as morphology markers; fully convolutional neural network distinguishes normal vs MRL/lpr patches (~90% precision) trained on as few as one/four samples. |
| Performance stats table | Signal-to-noise (avg over 15 cycles) 85:1; fluorophore-removal efficiency ~98%; signal deterioration 0.79%/cycle; background increase 0.06%/cycle. |
| Segmentation accuracy table | Cells correctly identified: BALBc 87.25% ± 2.89%, MRL 88.50% ± 5.31%; singlets BALBc 89.88% ± 1.12%, MRL 92.09% ± 4.41%. |
| Imaging spec | 40x oil NA 1.3; 7×9 tiled, 1386×1008 px/tile, 188 nm/pixel lateral, 900 nm axial, 11 z-planes; 9 final images (x=9702, y=9072, z=11), 31 channels (30 antibodies + 1 nuclear). |
| Dataset / cohort | 9 spleens: 3 BALBc (wild-type) + 6 MRL/lpr; MRL grouped early (4,5,6) / intermediate (7,8) / late (9); 9-month-old female mice; ~707,466 cells after cleanup. |

---

## Primary Sources Behind Key Quotes
- "singlecell quantification… once deemed impossible" → Gerner, M.Y., Kastenmuller, W., Ifrim, I., Kabat, J., and Germain, R.N. (2012). Immunity 37, 364–376.
- Prior multiplexed-imaging methods (stain/strip/wash lineage CODEX improves on) → Schubert et al. (2006), Nat. Biotechnol. 24, 1270–1278; Gerdes et al. (2013), Proc. Natl. Acad. Sci. USA 110, 11982–11987.
- Mass cytometry / CyTOF benchmark comparator → Bendall et al. (2011), Science 332, 687–696; Spitzer et al. (2015), Science 349, 1259425.
- X-shift phenotype mapping used for cell-type definition → Samusik, N., Good, Z., Spitzer, M.H., Davis, K.L., and Nolan, G.P. (2016). Nat. Methods 13, 493–496.
- Delaunay/Gabriel-graph spatial-neighbor methodology → Gabriel, K.R., and Sokal, R.R. (1969). Syst. Zool. 18, 259.
- ERTR7 stroma in T-cell trafficking (spatial-niche functional readout) → Burrell et al. (2015), Transplantation 99, 1119–1125.

---

## Flags
- [ ] Metadata unverified: Journal confirmed as Cell and DOI (10.1016/j.cell.2018.07.010) confirmed in text (Supplemental Information line and author block), but **volume / issue / page numbers are not present in the cleaned text** — do not assert them without checking the published record.
- [ ] Verbatim OCR artifacts preserved: e.g. "singlecell" (INTRODUCTION) and "diseaseafflicted" (DISCUSSION) are merged-word artifacts in the cleaned source; quoted as-is. Some source numbers render with stray markup (e.g. "( 700,000 cells)") — treated as ~700,000.
- [ ] Scope note: extensive MRL/lpr lupus disease-mechanism detail (specific cell-pair interaction changes, cell-count- vs affinity-driven contact dynamics) is mostly out-of-scope per the context file (no binding to a specific disease/species) and was NOT captured except where it doubles as a spatial-microenvironment-shapes-cell-state example (CD27/CD4 finding) or a temporal-snapshot nuance.
- [ ] Temporal caveat for downstream use: this is fixed-tissue imaging; "early/intermediate/late" stages come from different animals, not paired longitudinal observation — relevant if cited under Claim 3.
- [ ] Read at source: for the spatial-neighborhood / niche-shapes-phenotype claim, Figures 4 and 6 and Table S4 (regression F-values) are the primary evidence and are worth inspecting first-hand; for cross-platform comparability, Figure 2B (CODEX vs CyTOF).
