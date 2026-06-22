# Spatial single-cell mass spectrometry defines zonation of the hepatocyte proteome — Source Index

**Authors:** Florian A. Rosenberger, Marvin Thielert, Maximilian T. Strauss, Lisa Schweizer, Constantin Ammar, Sophia C. Mädler, Andreas Metousis, Patricia Skowronek, Maria Wahle, Katherine Madden, Janine Gote-Schniering, Anna Semenova, Herbert B. Schiller, Edwin Rodriguez, Thierry M. Nordmann, Andreas Mund & Matthias Mann
**Journal / Venue:** Nature Methods, 2023 (volume/issue/pages not stated in source text; see Flags)
**DOI:** doi:10.1038/s41592-023-02007-6
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/19 - Spatial single-cell mass spectrometry defines zonation of the hepatocyte proteome_cleaned.md

---

## In One Sentence
The authors introduce single-cell Deep Visual Proteomics (scDVP) — a workflow that integrates high-content imaging, AI segmentation, laser microdissection and multiplexed mass spectrometry to measure the proteome of individual hepatocyte slices within intact mouse liver tissue — and use it to show that roughly half the detectable hepatocyte proteome is spatially zonated along the portal-to-central-vein axis.

## Orientation (non-binding)
This is a spatial single-cell proteomics METHOD paper sitting directly on the spatial axis (Axis C) and the proteome modality (Axis A). It likely feeds: claim 2 (dissociation/suspension single-cell proteomics loses spatial context, here resolved by keeping cells in situ), claim 6 (high-throughput spatial single-cell proteomics is technically feasible), claim 4/8 (its cross-omics comparison shows RNA and protein correlate poorly genome-wide → modalities carry orthogonal, non-substitutable information), and claim 7 (spatial microenvironment/gradients shape the proteome). It can serve BOTH as support (spatial proteomics is real and adds orthogonal information) AND as an honest concession of the temporal gap (claim 3 / Axis B): the authors explicitly state they did not cover the temporal aspect, and the assay is a destructive fixed-tissue snapshot. Note: this is the Mann lab (not the authoring group), so it is field-method ammunition rather than "our own capability."

---

## Load-Bearing Excerpts

> "scDVP resolves the context-dependent, spatial proteome of murine hepatocytes at a current depth of 1,700 proteins from a cell slice. Half of the proteome was diferentially regulated in a spatial manner, with protein levels changing dramatically in proximity to the central vein."
> — Abstract · bears on: claim 2, claim 6, claim 7, Axis A (proteome), Axis C (spatial) · states spatial single-cell proteomics depth and the extent of spatial regulation. [sic: "diferentially" as printed in source]

> "scDVP is applicable to healthy and diseased tissues and complements other spatial proteomics and spatial omics technologies."
> — Abstract · bears on: claim 8, standard/integration · positions the method as complementary to other spatial omics.

> "While this trajectory is promising, proteome depth, throughput and lack of spatial context limit biological use."
> — Introduction · bears on: claim 2, claim 10, Axis C · concedes that prior MS single-cell proteomics lacks spatial context.

> "we here developed single-cell DVP (scDVP), a complementary approach that extends scProteomics technologies into the intact tissue context."
> — Introduction · bears on: claim 2, claim 6, Axis C · frames the contribution as bringing single-cell proteomics into intact tissue.

> "the proteome of hepatocytes is determined by paracrine signaling, as well as oxygen and nutrient gradients. These metabolic gradients require distinct functional cell states along the portal vein (PV) to central vein (CV) axis."
> — Introduction · bears on: claim 7, Axis C · states that microenvironmental gradients determine the proteome and cell state.

> "Despite this long and varied background, the extent of spatial heterogeneity and proteome variation in hepatocyte remains an open question."
> — Introduction · bears on: claim 7 · frames spatial proteome heterogeneity as still unresolved.

> "one shape cut from a 10 µm section corresponds to a third or half of a hepatocyte, or approximately 250 pg of protein input, equivalent to the protein content of one HeLa cell."
> — Results (workflow) · bears on: claim 6, claim 10 · quantifies the protein input from a single cell slice.

> "This resulted in a doubling of identified proteins with a median number of 1,712 proteins across three biological replicates and 455 single shapes, at twice the previous throughput... A maximum of 2,769 proteins were identified in one shape, and 3,738 unique proteins were found across all samples"
> — Multiplex-DIA · bears on: claim 6, claim 10, Axis A · quantitative proteome depth per shape and across the dataset.

> "This suggests little to no contamination from surrounding blood, a common issue in bulk proteomics"
> — Multiplex-DIA · bears on: claim 10, Axis C · in-situ microdissection avoids a contamination problem of bulk measurement.

> "The number of detected proteins correlated logarithmically with the microdissected area..., indicating that scDVP requires the highest possible MS sensitivity."
> — Multiplex-DIA · bears on: claim 10 · sensitivity is the limiting factor tying input amount to depth.

> "This demonstrates that single-cell data retains subtle biological differences compared to the excision of larger areas."
> — Results (pseudo-neighbors) · bears on: claim 7, claim 10 · single-cell resolution preserves biology lost by pooling.

> "Analysis of variance (ANOVA) testing across all bins revealed that 49% of all proteins detected in at least half of the samples were significantly different between zones (false discovery rate (FDR) <0.05..."
> — Results · bears on: claim 7, Axis C · quantifies the fraction of the proteome that is spatially regulated.

> "Only 5.8% of these proteins were expressed equally in all zones (multiple testing-adjusted Shapiro–Wilk test, P > 0.05)"
> — Results · bears on: claim 7, Axis C · very few proteins are spatially uniform.

> "A cross-omics comparison with scRNAseq data confirmed the directionality of the most prominent zonation markers (Pearson’s R = 0.97...), while correlation was low across all proteins and transcripts (Pearson’s R = 0.12). Notably, a number of proteins were regulated only in the RNA or protein dimension, or even inversely correlated..., such as dimethylglycine dehydrogenase in the choline catabolic pathway."
> — Results (cross-omics) · bears on: claim 4, claim 8, Axis A · genome-wide RNA–protein correlation is low and some proteins are RNA-only, protein-only, or inverse — direct evidence that modalities are non-substitutable.

> "Similarly, when we compared our data with a FACS-based hepatocyte proteome..., we found slightly lower correlation of markers and better overlap overall (Pearson’s R of 0.16 versus 0.12...)."
> — Results (cross-omics) · bears on: claim 4, claim 8 · cross-method/cross-dataset comparison of spatial proteomes.

> "This underlines that the scDVP dataset provides orthogonal insight into liver physiology instead of merely complementing existing datasets."
> — Results (cross-omics) · bears on: claim 4, claim 8 · claims the data are orthogonal, not merely redundant.

> "we found only small changes of summed organellar intensities across spatial bins..., namely decreasing mitochondrial and endoplasmic reticulum mass and increasing Golgi apparatus and nucleoplasm from PV to CV."
> — Results (subcellular) · bears on: Axis C (subcellular), claim 7 · subcellular compartment composition shifts across space.

> "Combining the single-shape proteomes with their inherent spatial information and staining intensities, scDVP revealed clear dependence of fluorescent intensities with the eight proteome classes established above."
> — Spatial context regulates single-cell proteomes · bears on: claim 7, claim 8, Axis C · links spatial/imaging features to proteome state.

> "we reasoned that the microscopic image could contain sufficient information to predict the proteome... This model reached an average precision of 0.94..., correctly assigning the proteome class of almost all cells."
> — Spatial context section · bears on: claim 8, Axis A/C (cross-modal inference) · imaging features predict proteome class.

> "We used the class probabilities as weights to predict the spatial proteome, which accurately approximated overall protein intensities (R = 0.78 between prediction and measurement...)"
> — Spatial context section · bears on: claim 8 · imaging-to-proteome prediction accuracy.

> "To date, MS-based scProteomics has been exclusively reported for cell suspensions."
> — Discussion · bears on: claim 2, Axis C · prior single-cell proteomics required dissociation into suspension (loses spatial context).

> "With our scDVP workflow, we achieved more than 1,700 proteins per single shape (and up to 2,700) despite working from sections that were fixed, stained, imaged and laser dissected."
> — Discussion · bears on: claim 6, Axis A · depth retained despite in-situ tissue processing.

> "More than half of quantified proteins were significantly different between portal and central zones, in line with scRNAseq data... and FACS-based proteomics data..."
> — Discussion · bears on: claim 7, claim 4 · spatial regulation of the proteome corroborated across modalities.

> "A rhythmic expression pattern has been previously shown for a large number of liver transcripts and proteins... While we have not covered the temporal aspect here, the scDVP approach could contribute to such studies by adding a spatial dimension."
> — Discussion · bears on: claim 3, Axis B (temporal) · explicit concession that the temporal dimension is not measured here.

> "By analyzing single cellular shapes without prior assumptions, scDVP now removes the dependency on established markers or features. This makes it a promising approach in heterogeneous tissues with partially or not defined subtypes of cells, such as in many tumor tissues."
> — Discussion · bears on: claim 6, claim 7 · marker-free spatial proteomics for heterogeneous/undefined cell populations.

> "scDVP can be a method of choice to map proteomic disturbances along gradients of, for instance, signaling factors, nutrients or gases, and in physiological settings that may create impediments for other omics methods, for instance, in extracellular fibrotic scars."
> — Discussion · bears on: claim 7, Axis C · proposes mapping proteome perturbations along microenvironmental gradients.

> "Our results demonstrate that the central challenge of scDVP is the sensitivity of the overall workflow... one excised hepatocyte shape contains approximately ten times more protein than the smallest cells of interest, such as typical resting lymphocytes."
> — Discussion · bears on: claim 10, Axis A · sensitivity ceiling limits applicability to small cells.

> "Given the more stable core proteome compared with single-cell transcriptomes... and the resulting lower required sample number, scDVP experiments encompassing a few hundred single shapes could be done in just a few days. Furthermore, because of the very low quantities and absence of proprietary reagents, marginal costs are extremely low."
> — Discussion · bears on: claim 4, claim 6, claim 10 · protein core proteome more stable than transcriptome; throughput and cost.

> "This can be further scaled to five-plex (effective four-plex) and 80 samples per day, scaling to 320 shapes per day."
> — Discussion · bears on: claim 6, claim 10 · throughput scaling of the method.

> "In combination with scDVP, this holds promise for single cells, although the biological information in single-cell phosphoproteomics data would currently be limited to a few high-abundance proteins with high modification stoichiometries. Subtle signaling events, such as the liver-dominant Wnt signaling, will require additional technological developments for in-depth biological description of signaling in single cells by MS."
> — Discussion · bears on: Axis A (PTM / signaling modality), claim 4 · single-cell PTM/signaling modalities remain technically scarce.

> "The modular nature of scDVP..., makes it widely applicable and also compatible with other spatial omics technologies such as spatial transcriptomics, epigenomics... or multiplexed imaging."
> — Discussion · bears on: claim 8, standard/integration · designed to interoperate with other spatial omics.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq / dissociation loses spatial info | "extends scProteomics technologies into the intact tissue context" / Intro; "exclusively reported for cell suspensions" / Discussion | supports |
| Claim 3 — destructive measurement cannot pair time | "we have not covered the temporal aspect here" / Discussion | supports (by concession) |
| Claim 4 — modalities orthogonal / non-substitutable | "correlation was low across all proteins and transcripts (Pearson's R = 0.12)... regulated only in the RNA or protein dimension, or even inversely correlated" / Results | supports |
| Claim 5 — protein/metabolite modalities indispensable for function/phenotype | "49% of all proteins... significantly different between zones" / Results; PPAR & urea-cycle zonation / Results | supports |
| Claim 6 — high-throughput spatial(-temporal) proteomics feasible | "median number of 1,712 proteins across... 455 single shapes" / Multiplex-DIA; "320 shapes per day" / Discussion | supports |
| Claim 7 — spatial organization/microenvironment shapes cell state | "determined by paracrine signaling, as well as oxygen and nutrient gradients" / Intro; "map proteomic disturbances along gradients" / Discussion | supports |
| Claim 8 — multimodal data orthogonal; need integration | "orthogonal insight... instead of merely complementing" / Results; "compatible with... spatial transcriptomics, epigenomics... multiplexed imaging" / Discussion | supports |
| Claim 9 — data islands / cross-paper incomparability / no standard | cross-omics & cross-dataset comparisons (scRNAseq, FACS proteome) / Results | nuances |
| Claim 10 — resolution × throughput × destructiveness trilemma | "scDVP requires the highest possible MS sensitivity" / Multiplex-DIA; "central challenge... is the sensitivity" + "ten times more protein than the smallest cells" / Discussion | supports |
| Axis A — modality (proteome; PTM/signaling scarce) | depth "more than 1,700 proteins per single shape" / Discussion; phospho "limited to a few high-abundance proteins" / Discussion | supports |
| Axis B — temporal | "we have not covered the temporal aspect here" / Discussion | challenges (gap) |
| Axis C — spatial (subcellular → cell → tissue) | subcellular compartment shifts PV→CV / Results; in-situ tissue context throughout | supports |
| standard / integration | "complements other spatial proteomics and spatial omics technologies" / Abstract | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | scDVP workflow (embedding, staining, high-content imaging, AI segmentation, laser microdissection, dimethyl-labeled mDIA on timsTOF SCP); liver "painting" with four stains marking PV (E-cadherin), CV (Glul), phalloidin segmentation, WGA counterstain. |
| Fig. 2 | Single-shape proteome depth ranked by intensity; histone intensity used to estimate nuclear content per slice; arterioles cut as technical controls. |
| Fig. 3 | Core zonation result: PCA where PC1 = measured PV/CV distance; 49% of proteins differ between 20 spatial bins; cross-omics directionality vs scRNAseq; subcellular compartment proportions vs bulk; OXPHOS decreasing PV→CV; urea-cycle and peroxisomal fatty-acid degradation zonation. |
| Fig. 4 | ML model (random forest) predicting proteome class from imaging features; average precision 0.94 (testing accuracy 0.90); prediction vs measurement R = 0.78 on a held-out section. |
| Extended Data Fig. 7 | Cross-omics correlations: markers vs scRNAseq R = 0.97 but all-protein R = 0.12; comparison to FACS-based proteome (markers R = 0.16 vs 0.12); proteins regulated in only one dimension or inversely. |
| Key numbers | 1,712 median proteins/shape (single-shape mDIA); up to 2,769 in one shape; 3,738 unique across all; ~250 pg input per slice; 49% proteins zonated (FDR<0.05); 5.8% spatially uniform; 400 hepatocytes + 6 arterioles after filtering; throughput up to 320 shapes/day (projected). |

---

## Primary Sources Behind Key Quotes
- scRNAseq liver zonation (cross-omics comparison; markers R=0.97, global R=0.12) → Halpern, K. B. et al. 2017, Nature 542:352–356, ref #6
- FACS-based spatial liver proteome comparison → Ben-Moshe, S. et al. 2019, Nat. Metab. 1:899–911, ref #8
- Original DVP (pooled "biological fractionation," marker-dependent) → Mund, A. et al. 2022, Nat. Biotechnol. 40:1231–1240, ref #4
- Liver zonation background review → Cunningham, R. P. & Porat-Shliom, N. 2021, Front. Physiol. 12:732929, ref #5
- Space–time logic of liver gene expression (temporal/spatial context) → Droin, C. et al. 2021, Nat. Metab. 3:43–58, ref #16
- Circadian phosphorylation control of metabolism (temporal/PTM context) → Robles, M. S., Humphrey, S. J. & Mann, M. 2017, Cell Metab. 25:118–127, ref #19
- "Making single-cell proteomics biologically relevant" (smallest-cell protein content benchmark) → Rosenberger, F. A., Thielert, M. & Mann, M. 2023, Nat. Methods 20:320–323, ref #20
- mDIA reference-channel doubling proteome depth (throughput/scaling claims) → Thielert, M. et al. 2023, Mol. Syst. Biol., ref #11
- Single-cell phosphoproteomics from ultra-low input (µPhos) → Oliinyk, D. et al. 2023, bioRxiv preprint, ref #22

---

## Flags
- [ ] Metadata unverified: journal is Nature Methods (confirmed by the peer-review/handling-editor statement and self-citations), year 2023 (Published online 2 October 2023); however the volume/issue/page numbers are NOT printed in the source text — left blank in the header.
- [ ] Metadata confirmed from text: DOI 10.1038/s41592-023-02007-6 (top of article and Online content); Received 9 December 2022; Accepted 15 August 2023; corresponding author Matthias Mann.
- [ ] Author affiliations only partially recoverable: source lists superscript markers (1, 2, 3) but the affiliation institution list is not included in the cleaned text; institutions not transcribed here.
- [ ] Verbatim oddities preserved as printed: "diferentially" (Abstract), "Cytochrom P450" (Results) — typos are in the cleaned source, not introduced here.
- [ ] Read at source (worth first-hand reading instead of via this paper): Halpern et al. 2017 (ref 6, scRNAseq zonation — the RNA-vs-protein comparison anchor for claim 4); Ben-Moshe et al. 2019 (ref 8, FACS-based spatial proteomics); Mund et al. 2022 (ref 4, original DVP).
- [ ] Scope note: detailed MS instrument parameters, labeling chemistry, and data-processing software versions (Methods/Reporting Summary) were deliberately not captured as off-roadmap filler.
