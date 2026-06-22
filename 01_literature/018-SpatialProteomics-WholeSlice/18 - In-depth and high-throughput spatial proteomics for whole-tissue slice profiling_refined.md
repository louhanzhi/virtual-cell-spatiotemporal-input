# In-depth and high-throughput spatial proteomics for whole-tissue slice profiling by deep learning-facilitated sparse sampling strategy — Source Index

**Authors:** Ritian Qin, Jiacheng Ma, Fuchu He, Weijie Qin (affiliations 1,2,3; He and W. Qin are corresponding authors)
**Journal / Venue:** Cell Discovery, 2024 (volume/issue/pages unverified; see Flags)
**DOI:** doi:10.1038/s41421-024-00764-y
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/18 - In-depth and high-throughput spatial proteomics for whole-tissue slice profiling_cleaned.md

---

## In One Sentence
The paper introduces S4P (sparse sampling for spatial proteomics) with a deep-learning reconstruction model (DeepS4P) that uses multi-angle parallel-strip microdissection plus image-reconstruction to map >9000 proteins across a whole mouse-brain slice at ~525 µm resolution in ~200 h of MS time, and reports large-scale spatial discordance between mRNA and protein distributions.

## Orientation (non-binding)
This is a method/resource paper (field progress, not our own group's data) most directly feeding Axis A (modality) and Axis C (spatial) plus roadmap Claim 6 (high-throughput spatial proteomics is feasible). Its strongest ammunition is for Claim 4 (RNA cannot proxy for protein: explicit mRNA–protein correlation figures and large-scale spatial discordance) and Claim 10 (the resolution × throughput × proteome-depth trilemma, quantified). It can serve as BOTH support (proteomics CAN reach whole-tissue depth; protein information is non-substitutable) AND foil (spatial proteomics is "still rare," far behind transcriptomics; the method is a static z-averaged snapshot conceding the temporal axis to future work) — downstream agent decides.

---

## Load-Bearing Excerpts

> "While genome mutations and transcriptome alterations act as drivers of diseases, the proteins that they encode regulate essentially all biological functions and constitute the majority of biomarkers and drug targets for disease diagnostics and treatment."
> — Abstract · bears on: Claim 5 (protein indispensable for function/phenotype), Claim 4, Axis A · asserts proteins, not the genes/transcripts encoding them, execute biological function and dominate biomarkers/drug targets.

> "unlike transcriptomics, which has a recent explosion in high-throughput spatial technologies with deep coverage, spatial proteomics capable of reaching bulk tissue-level coverage is still rare in the field, due to the non-amplifiable nature of proteins and sensitivity limitation of mass spectrometry (MS)."
> — Abstract · bears on: Claim 6, Claim 2, Claim 10, Axis A/C · states spatial proteomics lags far behind spatial transcriptomics because proteins cannot be amplified and MS sensitivity is limited.

> "More importantly, due to the limited multiplexing capability of the current proteomics methods, whole-tissue slice mapping with high spatial resolution requires a formidable amount of MS matching time."
> — Abstract · bears on: Claim 10 (resolution × throughput trade-off), Axis C · names the throughput bottleneck for high-resolution whole-slice proteomics.

> "we generated the largest spatial proteome to date, mapping more than 9000 proteins in the mouse brain, and discovered potential new regional or cell type markers."
> — Abstract · bears on: Claim 6, Axis C · headline result: deepest whole-slice spatial proteome to date.

> "The spatial organization of these biomolecules plays a crucial role in determining their function and interaction with their spatial neighborhood in physiological and pathological tissue environments."
> — Introduction · bears on: Claim 7 (spatial organization/microenvironment shapes cell state), Axis C · motivates spatial resolution: function depends on spatial neighborhood.

> "it is the gene-encoded proteins that actually regulate essentially all cellular functions and therefore need to be investigated to reveal tissue spatial heterogeneity."
> — Introduction · bears on: Claim 5, Claim 4, Axis A · argues protein (not transcript) must be measured to capture spatial heterogeneity.

> "Accumulating proteogenomic comparisons revealed that typical Pearson correlation coefficients for mRNA–protein in mammalian tissues are ~0.35–0.6, and can be even lower at single-cell level."
> — Introduction · bears on: Claim 4 (modality orthogonality / mRNA cannot substitute for protein), Axis A · quantifies weak mRNA–protein correlation, worse at single-cell level. (ref 7)

> "Discordant spatial distribution was also revealed by the different zonation patterns of the enterocyte proteins and mRNAs along the villus axis."
> — Introduction · bears on: Claim 4, Axis A/C · cites spatially discordant mRNA vs protein patterns in intestinal epithelium. (ref 8)

> "The poor mRNA–protein correlation may result in biased inference of gene expression distribution using transcriptional data, especially for mammalian brains, considering the large distances between the locations where the proteins are synthesized and transported."
> — Introduction · bears on: Claim 4 (RNA-based inference is biased), Axis A/C · transcript data mislocate proteins because synthesis and destination sites differ, particularly in brain. (refs 9–11)

> "Only several dozen proteins can be analyzed, which makes IMC less attractive for the discover-driven screening of cellular phenotypes."
> — Introduction · bears on: Claim 10 (multiplexing limit of targeted methods), Axis A · antibody/IMC approaches are limited to dozens of targets.

> "liquid chromatography-coupled biological mass spectrometry (LC-MS), which routinely measures ~10,000 unique proteins from bulk cell and tissue samples, is advantageous in capturing the spatial complexity of tissue proteome."
> — Introduction · bears on: Claim 6, Claim 10 (bulk depth vs spatial trade-off), Axis A · LC-MS reaches ~10,000 proteins in bulk, motivating its use for spatial work.

> "Although 3000 proteins at 50-µm resolution was reached in a recent work, a larger scale of proteome identification is more desirable to deeply cover regulatory pathways in tissues for spatially resolved physiological and pathological investigation at the molecular level."
> — Introduction · bears on: Claim 10, Claim 6, Axis C · prior spatial proteomics capped at shallow depth; deeper coverage needed. (refs 17–19)

> "2000 proteins can be obtained at 100-µm spatial resolution due to the limited sample amount."
> — Introduction · bears on: Claim 10 (resolution–depth trade-off), Axis C · quantifies the depth penalty at fine resolution. (refs 17,18)

> "the samples that need to be analyzed expand exponentially with the increased resolution. Taking a circle tissue slice with a diameter of 1 cm as an example, ~8000 samples, corresponding to more than 8000–10,000 h of MS machine time, are required to achieve whole-tissue-slice coverage with a 100 μm resolution, which makes it a formidable task in routine studies."
> — Introduction · bears on: Claim 10 (the resolution × throughput trilemma, quantified), Axis C · explicit cost: ~8000 samples / 8000–10,000 h MS for 1 cm slice at 100 µm.

> "whole-tissue-slice-based spatial proteomic approaches that provide reasonable throughput without compromising spatial resolution and proteome depth are urgently needed."
> — Introduction · bears on: Claim 10, Claim 6, Axis C · frames the unmet need as simultaneous throughput + resolution + depth.

> "we developed a sparse sampling strategy for spatial proteomics (S4P) that is capable of achieving ~500 μm or higher resolution, while covering centimeter-sized tissue slices within a reasonable MS matching time frame."
> — Introduction · bears on: Claim 6, Axis C · the method claim.

> "we successfully reconstructed the spatial proteome (SP) of a whole-tissue slice of a mouse brain, consisting of the distribution and expression of 9204 proteins with a spatial resolution of 525 μm"
> — Introduction · bears on: Claim 6, Axis C · key quantitative result (9204 proteins, 525 µm).

> "the MS data acquisition was completed within ~200 h of MS time, half of the time required by the 'gridding'-like strategy."
> — Introduction · bears on: Claim 10 (throughput gain), Claim 6 · sparse sampling halves MS time vs gridding at this resolution.

> "an MS time 15–20 times shorter than that of the 'gridding'-like strategy can be achieved for a 100 μm spatial resolution"
> — Introduction · bears on: Claim 10, Axis C · projected throughput advantage scales with resolution.

> "The first large-scale discovery of different levels of spatial distribution inconsistency between RNAs and proteins in various biological processes, such as synaptic secretion of proteins and neurotransmitters, cellular metabolism, and cognitive & motor function integration, is invaluable for future brain science study."
> — Introduction · bears on: Claim 4 (RNA–protein spatial discordance), Axis A/C · the paper's biological discovery: RNA and protein localize differently across processes.

> "In order to minimize batch effects that are commonly observed in large-scale proteome analysis, a sliding window strategy for sample randomization was adopted"
> — Results (QC) · bears on: Claim 9 (QC / batch effects / comparability), standard axis · randomization design to control batch effects.

> "Highly stable protein identification and quantification (identified 7583–8502 proteins, median CV = 0.16, and Pearson correlation coefficients > 0.93) of the quality control samples ... were achieved across the whole data acquisition process"
> — Results (QC) · bears on: Claim 9, standard axis · reproducibility metrics for interspersed QC samples.

> "PCA and UMAP plots showed highly overlapped and randomly distributed proteome quantification without any subgrouping among tissue slices, sample plates, and sample batches ..., indicating no obvious batch effect in the datasets."
> — Results (QC) · bears on: Claim 9, standard axis · claims no detectable batch effect after design.

> "a total of 234,768 peptides and 9318 unique proteins ... were mapped and quantified in the brain strips."
> — Results (QC) · bears on: Claim 6, Axis A · total identifications across strips.

> "IHC, which is currently considered as the 'gold standard' method for in-situ protein expression analysis in a whole-tissue slice ..., was used to validate the SP distribution reconstructed by S4P."
> — Results (SP reconstruction) · bears on: Claim 9 (validation / standard), Claim 6 · IHC used as ground-truth check on reconstruction.

> "Overall SP comparison between the two methods displayed relatively high consistency with a median CS of 0.869"
> — Results (SP reconstruction) · bears on: Claim 9, Claim 6 · cross-method agreement (S4P vs gridding) quantified.

> "Considering that the two sets of data were obtained from tissue slices of two different mice, some inconsistency is expected."
> — Results (SP reconstruction) · bears on: Claim 9 (cross-sample comparability), Claim 3 · concedes that the "ground truth" came from a different animal, so the two datasets are not the same physical sample.

> "No data imputation was used in S4P to avoid possible distortion of the proteome spatial distribution."
> — Results (SP reconstruction) · bears on: Claim 9 (data handling / standard), Axis A · explicit choice against imputation to preserve true distribution.

> "8691 pairs of gene expression products were found from both ST and spatial proteome SP data"
> — Results (S4P vs ST) · bears on: Claim 8 (multimodal pairing/integration), Claim 4, Axis A · number of co-detected transcript–protein pairs for direct comparison.

> "The correlation between different molecule pairs varies greatly, ranging from –0.47 to 0.62"
> — Results (S4P vs ST) · bears on: Claim 4 (modality orthogonality, spatial mRNA–protein discordance), Axis A/C · spatial transcript–protein correlation spans strongly negative to moderately positive.

> "For gene products with poor correlation, their inconsistency may be attributed to the complex brain tissue, which comprises hundreds to thousands of cell types, each with potentially different spatial distribution patterns of mRNAs and proteins."
> — Results (S4P vs ST) · bears on: Claim 4, Claim 7, Axis A/C · attributes RNA–protein discordance to cellular/spatial heterogeneity.

> "Although we cannot fully explain this spatially inconsistent distribution between RNAs and proteins, the results further indicate the advantage of directly mapping protein quantity and location in the tissue."
> — Results (S4P vs ST) · bears on: Claim 4, Claim 5, Axis A · author-conceded uncertainty + argument that protein must be measured directly, not inferred from RNA.

> "direct characterization of the quantity and location of proteins at whole-tissue level is indispensable for both biological function and disease mechanism studies, due to the widely discovered low correlation between RNA and protein."
> — Discussion · bears on: Claim 4, Claim 5, Axis A · core thesis-aligned statement: RNA cannot substitute for protein.

> "Especially for tissues like the brain, where large-scale proteins are transported away from the sites where they are synthesized, unbiased proteome location measurement is highly demanded to promote elucidation of the spatially organized molecular regulations in the most complex organ."
> — Discussion · bears on: Claim 4, Claim 2, Axis C · spatial separation of synthesis and protein location makes RNA-based localization unreliable.

> "S4P is capable of large-scale measuring in centimeter-sized samples with the potential to reach micrometer spatial resolution using 5–10 times less MS machine time compared to the current 'gridding' methods."
> — Discussion · bears on: Claim 6, Claim 10, Axis C · summary throughput claim.

> "S4P can be used as a complementary strategy to reveal protein distribution that cannot be inferred by spatial transcriptome, especially for the metabolic signaling and protein expression-related genes"
> — Discussion · bears on: Claim 4, Claim 8 (complementary modalities, integration), Axis A · positions proteomics as orthogonal/complementary to spatial transcriptomics.

> "The current version of S4P is not without limitations. ... the laser damages the adjacent tissue while cutting the target area. For S4P, the damaged area becomes substantial with the reduced strip width. According to our attempts, ~100 µm in strip width is the current limit for LMD-based sample collection."
> — Discussion · bears on: Claim 10 (resolution limit of the destructive sampling), Axis C · conceded hard limit on spatial resolution from laser microdissection.

> "Another limitation is that eight adjacent slices are needed for spatial proteome reconstruction currently ... the final spatial proteome profile obtained is the average result of the eight slices spanning 80 μm along the z axis."
> — Discussion · bears on: Claim 10, Axis C · conceded z-axis averaging; the map is not a single physical plane.

> "future studies using a combination of S4P and time-resolved mouse models may provide information on the dynamic distribution and functional variation of synaptic vesicle proteins under different physiological and pathological conditions"
> — Results (KEGG) / Discussion · bears on: Claim 3 (temporal axis), Axis B · concedes the method is a static snapshot; temporal dynamics are deferred to future time-resolved models.

---

## Claim Touchpoints (router — the downstream aggregation key)

| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq loses spatial info / spatial-omics methods (Axis C) | "unlike transcriptomics, which has a recent explosion…" / Abstract; "Especially for tissues like the brain…" / Discussion | supports |
| Claim 3 — destructive measurement cannot observe time / pairing (Axis B) | "future studies using a combination of S4P and time-resolved mouse models…" / Discussion; "two different mice, some inconsistency is expected" / Results | nuances (conceded gap) |
| Claim 4 — modalities orthogonal, RNA cannot substitute for protein (Axis A) | "typical Pearson correlation coefficients for mRNA–protein … ~0.35–0.6" / Intro; "ranging from –0.47 to 0.62" / Results; "indispensable … due to the widely discovered low correlation" / Discussion | supports |
| Claim 5 — protein indispensable for function/phenotype (Axis A) | "the proteins that they encode regulate essentially all biological functions…" / Abstract; "gene-encoded proteins that actually regulate…" / Intro | supports |
| Claim 6 — high-throughput spatial proteomics is feasible (Axis A/C) | ">9000 proteins in the mouse brain" / Abstract; "9204 proteins with a spatial resolution of 525 μm" / Intro | supports |
| Claim 7 — spatial organization/microenvironment shapes cell state (Axis C) | "spatial organization … plays a crucial role in determining their function and interaction with their spatial neighborhood" / Intro | supports |
| Claim 8 — multimodal orthogonal info, need integration (Axis A) | "complementary strategy to reveal protein distribution that cannot be inferred by spatial transcriptome" / Discussion; "8691 pairs … from both ST and SP" / Results | supports |
| Claim 9 — data islands / comparability / QC / standards (standard axis) | "sliding window strategy for sample randomization" / Results; "median CS of 0.869" / Results; "No data imputation was used" / Results | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma (Axis C) | "~8000 samples … 8000–10,000 h of MS machine time … formidable task" / Intro; "~100 µm … current limit for LMD-based sample collection" / Discussion | supports |
| Claim 1 — data is the bottleneck, not the model | (no direct statement; method paper, not a modeling/benchmark critique) | — |

---

## Figures / Tables / Numbers

| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Schematic of S4P sampling/data generation (a) and DeepS4P spatial reconstruction (b). |
| Fig. 2 | QC of S4P data: per-slice protein counts (9107–9228), Venn overlap (>96% shared across slices), per-strip protein counts (~8000), log10 summed intensity (6.5–7, 1.48% low-edge outliers), peptide intensity vs injection order with QC dots, housekeeping-protein even distribution. |
| Fig. 3 | Pixel-wise pairwise correlation matrix (Ward's linkage) of the spatial proteome; spatial maps of selected proteins (e.g., DAO cerebellum, PRRT1 hippocampus, KCNH3 cortex). |
| Fig. 4 | S4P maps of regional markers and cell-type markers; co-localized protein pairs/complexes (e.g., GABBR1–GABBR2 CS 0.99, TUBA4A–TUBB4B 0.98, SYN1–SYN2 0.94, CTNNB1–CDH2 0.93, NSF–NAPA 0.90). |
| Fig. 5 | Spatial maps of proteins in key brain GO processes (morphogenesis; neurotransmitter uptake/transport/secretion; synaptic transmission/organization). SV2B–SLC17A7 CS up to 0.99; NRXN3–SNAP25 CS 0.96. |
| Fig. 6 | Spatial patterns of 20 KEGG pathways; coverage examples: SNARE interactions 66% (mmu04130), GABAergic synapse 59% (mmu04727), synaptic vesicle cycle 53% (mmu04721). |
| Fig. 7 | S4P vs ST (Visium) comparison: 8691 co-detected pairs; Pearson correlations −0.47 to 0.62; GO over-representation for positively, non-, and negatively correlated transcript–protein pairs. |
| Key numbers | 9204 reconstructed protein maps; 9318 unique proteins / 234,768 peptides quantified; ~525 µm resolution; ~200 h MS time (½ of gridding at this resolution; projected 15–20× faster at 100 µm; 5–10× overall); ~200 strips at 300 µm width; 8 adjacent 10-µm slices spanning 80 µm in z; QC: median CV 0.16, Pearson >0.93; gridding cross-method median CS 0.869; mRNA–protein bulk r ~0.35–0.6. |

---

## Primary Sources Behind Key Quotes
- mRNA–protein correlation ~0.35–0.6 (and lower at single-cell) → Jiang, Y. R. et al., Cell Rep. 42, 113455 (2023), ref 7.
- Spatial discordance of mRNA vs protein along villus axis → Harnik, Y. et al., Nat. Metab. 3, 1680–1693 (2021), ref 8.
- Biased inference from transcript data / emerging principles of gene expression control → Buccitelli, C. & Selbach, M., Nat. Rev. Genet. 21, 630–644 (2020), ref 9 (also refs 10–11).
- ~2000 proteins at 100-µm resolution → Piehowski, P. D. et al., Nat. Commun. 11, 8 (2020), ref 17; Li, L. et al. (tissue expansion), Nat. Commun. 13, 7242 (2022), ref 18.
- 3000 proteins at 50-µm resolution (recent work) → Kwon, Y. et al., Mol. Cell Proteom. 23, 100841 (2024), ref 19.
- "Gridding"-like / microscaffold-assisted spatial proteomics (MASP) comparison → Ma, M. et al., Nat. Commun. 13, 7736 (2022), ref 24.
- Image-reconstruction / Tomographer / STRPseq design matrix → Schede, H. H. et al. (imaging-free molecular tomography), Nat. Biotechnol. 39, 968–977 (2021), ref 25.
- Twice-deeper coverage at same resolution / tissue expansion route to single-cell resolution → Li, L. et al., Nat. Commun. 13, 7242 (2022), ref 18.
- Local translation / synaptic transcriptome supporting RNA–protein colocalization → Holt et al., Nat. Struct. Mol. Biol. 26, 557–566 (2019), ref 55; Biever et al., Curr. Opin. Neurobiol. 57, 141–148 (2019), ref 56; Bourke et al., Mol. Cell 83, 452–468 (2023), ref 57.

---

## Flags
- [ ] Metadata unverified: Volume/issue/page numbers not present in cleaned text (only "Cell Discovery; https://doi.org/10.1038/s41421-024-00764-y" appears). Year 2024 inferred from the DOI string and from references dated 2024 (e.g., ref 19); not stated as an explicit publication date.
- [ ] Metadata unverified: No received/accepted/published dates in the cleaned text.
- [ ] Source inconsistency: In the Introduction the cleaned text has a broken sentence ("enables systemwide study of spatial 2000 proteins can be obtained at 100-µm spatial resolution…") where cleaning appears to have dropped text; the quoted clause "2000 proteins can be obtained at 100-µm spatial resolution due to the limited sample amount" is taken from that damaged passage.
- [ ] Source artifact: Original "fi"/"fl" ligatures were encoded as `<sup>fi</sup>`/`<sup>fl</sup>` markup in the cleaned file; quotes above restore the intended words (e.g., "profiling", "field") — no lexical change, markup only.
- [ ] Read at source: Harnik et al. 2021 (ref 8) and Jiang et al. 2023 (ref 7) for first-hand mRNA–protein (spatial) discordance numbers; Li et al. 2022 (ref 18) for the same-resolution depth comparison; Schede et al. 2021 (ref 25) for the reconstruction/tomography method this paper builds on.
- [ ] Affiliation detail: Author affiliation institutions (numbered 1,2,3) are not spelled out in the cleaned text body; corresponding authors are Fuchu He and Weijie Qin (from "Correspondence" and Author Contributions).
