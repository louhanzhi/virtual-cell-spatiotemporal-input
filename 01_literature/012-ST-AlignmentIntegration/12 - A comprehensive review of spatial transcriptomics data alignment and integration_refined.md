# A comprehensive review of spatial transcriptomics data alignment and integration — Source Index

**Authors:** Muiz Khan, Suzan Arslanturk, Sorin Draghici (Dept. of Computer Science, Wayne State University, Detroit, MI; Sorin Draghici also Advaita Bioinformatics, Ann Arbor, MI; corresponding: sorin@advaitabio.com)
**Journal / Venue:** unverified; see Flags
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/12 - A comprehensive review of spatial transcriptomics data alignment and integration_cleaned.md

---

## In One Sentence
A methods review of 24 computational tools for aligning and integrating multiple spatial transcriptomics (ST) tissue slices into a common coordinate system; it formalizes the alignment/integration problem, proposes a generalized pipeline, sorts tools into statistical-mapping, image-processing/registration, and graph-based families, and concludes that robust alignment across heterogeneous slices and full 3D reconstruction remain unsolved.

## Orientation (non-binding)
Squarely on the **spatial axis (Axis C)** and on **Claim 2** (scRNA-seq / bulk dissociation destroys spatial context while ST preserves it). It also feeds **Claim 9 / Standard axis** (cross-platform/cross-protocol incomparability, batch effects, the explicit call for standardization and benchmark datasets) and **Claim 10** (resolution-vs-coverage trade-offs across ST technologies). It can serve as BOTH support and foil: support for "spatial context matters and is lost by dissociation," but also a concession that ST itself is essentially RNA-only and resolution-limited — the authors recommend adding **spatial proteomics and metabolomics** (touches **Claims 4/8, Axis A modality**). It bears on **Axis B / Claim 3** only weakly: temporal coverage here means aligning *different* slices sampled at *different* time points / developmental stages, never tracking the same cell — useful as nuance for the destructive-measurement constraint.

---

## Load-Bearing Excerpts

> "In contrast, single-cell “omics” methods provide higher resolution and capture rare cell areas, but they require cell isolation, which also disrupts spatial context information. Spatial transcriptomics (ST) technologies have significantly advanced our capacity to quantify gene expression within tissue sections while preserving crucial spatial context information."
> — Introduction · bears on: Claim 2, Axis C · single-cell sequencing requires isolation that destroys spatial context; ST preserves it.

> "traditional methods such as bulk “omics” approaches offer only a general perspective of cell populations within tissues, primarily emphasizing the dominant population. As a result, rare sub-populations can be masked by the more abundant populations. Furthermore, spatial information is completely disregarded."
> — Introduction · bears on: Claim 2, Claim 10, Axis C · bulk omics masks rare populations and discards spatial information entirely.

> "Several studies have demonstrated better biological insights derived from downstream analyses of single ST tissue slices compared to single-cell-RNA (scRNA) and bulk-RNA analyses, such as in cell-type identification and spatial clustering analysis [1–6]."
> — Introduction · bears on: Claim 2, Axis C · spatially resolved data yields better biological insight than scRNA/bulk for some tasks.

> "each data point representing a spot consisting of one to 100 cells and their corresponding messenger ribonucleic acid (mRNA) expression values. However, it is important to note that a single 2D coordinate space only represents a single slice of the tissue section, limiting the comprehensive analysis of the entire tissue context."
> — Introduction · bears on: Claim 10, Axis C · each ST spot pools 1–100 cells; a single 2D slice cannot represent full tissue context.

> "Advanced ST technologies such as Visium from 10 Genomics allows expression measurement of up to 5000 spots per slice, with each spot in the 2D space capturing between 1 and 30 cells [7]. Although this is a significant improvement over bulk RNA expressions while capturing the spatial information, the gene expression resolution and scale are lower than in scRNA expression."
> — Introduction · bears on: Claim 10, Axis C · Visium captures spatial info but at lower gene-expression resolution/scale than scRNA — explicit spatial-vs-resolution trade-off.

> "On the other hand, the 2D nature of the sliced tissue sections leads to the loss of z-axis information, making it challenging to accurately reconstruct the 3D structure of the tissue."
> — Introduction · bears on: Axis C, Claim 10 · sectioning into 2D slices loses z-axis / 3D spatial information.

> "This 3D reconstruction preserves the spatial relationships between tissue structures across slices, offering insights into cellular organization, interactions, and spatial gradients of gene expression that cannot be captured in isolated 2D slices."
> — Introduction · bears on: Axis C, Claim 7 · 3D reconstruction recovers cellular organization, interactions, and spatial gradients lost in isolated slices.

> "Tools focusing solely on single-slice ST analysis or multi-omics data integration tools, such as those integrating ST data with scRNAseq data, were excluded from this review."
> — Review selection criteria · bears on: Claim 8, Axis A · the review explicitly scopes out multi-omics integration; its subject matter is RNA-only spatial data.

> "histology images are often used as input, which are microscopic images of tissue sections stained to reveal cellular and structural features... These images are often used to derive structural attributes, including cell density, tissue boundaries, and histological patterns, contributing to the multimodal nature of ST data."
> — Problem description · bears on: Axis A (imaging/morphology), Axis C · histology/H&E images add morphological structure as a second modality alongside expression.

> "This integration process must maintain the spatial relationships and gene expression patterns across all tissue slices."
> — Problem description · bears on: Axis C, Standard · the integration objective is defined as preserving spatial relationships and expression jointly.

> "For example, aligning heart tissue slices taken at different stages of development, such as from early embryonic stages to mature adult tissue, requires handling variations in structure, cell composition, and spatial organization as the heart grows and changes over time, but these slices still exhibit overlap or share similar spatial regions [10]."
> — Scope (Heterogeneous alignment) · bears on: Axis B, Claim 3 · temporal analysis is done by aligning distinct slices sampled across developmental stages (cross-sample, not same-cell pairing).

> "When samples are collected from across datasets or experiments, they often share similar spatial regions with partial overlap... Additionally, batch effect removal is needed to ensure the accuracy of the alignment and integration process [10, 11]."
> — Scope (Heterogeneous alignment) · bears on: Claim 9, Standard · cross-dataset/cross-experiment slices require batch-effect removal.

> "Furthermore, as ST data can be collected at different time-points or stages, it allows for the observation and analysis of tissue development or growth, providing insights into cell progression, disease dynamics, and the impact of marker genes [10, 13, 16–19]."
> — Significance · bears on: Axis B, Claim 3 · time-point / stage sampling enables study of development and progression.

> "One key characteristic is the highdimensionality and multi-modality of ST data... ST datasets also exhibit variability, noise, and uncertainty, which can arise from various factors such as experimental conditions, tissue preparation, and sequencing artifacts [16]. They may be collected over different time-points and represent varying tissue architectures or conditions [10]. Spatial warping also refers to distortions or deformations in the spatial coordinates of the data points, often caused by tissue processing or imaging techniques [16]."
> — Inherent challenges · bears on: Claim 9, Standard, Axis C · ST data carry technical/biological variability, noise, spatial warping, and cross-time-point heterogeneity that complicate integration.

> "Moreover, ST data have spatial dependency and spatial heterogeneity [2, 20], meaning that neighboring regions in the tissue may have similar gene expression profiles, and spatially distinct regions may exhibit different expression patterns."
> — Inherent challenges · bears on: Claim 7, Axis C · expression depends on spatial neighborhood (spatial dependency/heterogeneity).

> "10 Visium [30] technology achieves a spatial resolution of 55 μm, with each capture site (spot) containing ∼1–10 cells. Slide-seq [40] enhances the spatial resolution to nearly cellular level (10 μm), while Stereo-seq [43] achieves subcellular resolution (0.22 μm) [10]."
> — Across dataset & technologies · bears on: Claim 10, Axis C · concrete spatial-resolution spread across ST platforms (55 μm → 10 μm → 0.22 μm).

> "some technologies require 8–10 μm tissue thickness, which may lead to challenges such as cells overlapping within sections. This overlap can obscure spatial relationships, necessitating the use of bioinformatics tools designed to deconvolute mixed signals and infer underlying cellular compositions. To the best of our knowledge, no computational tool currently exists to specifically address this challenge."
> — Experiments · bears on: Claim 10, Axis C · section thickness causes cell overlap that obscures spatial relationships; an open gap.

> "fresh frozen tissues commonly utilize oligo-dT primed libraries for capturing polyadenylated transcripts, enabling whole-transcriptome analysis, whereas formalin-fixed paraffin-embedded (FFPE) samples typically rely on probe-based chemistries that are designed to detect targeted gene sets even in the presence of RNA degradation which happens in FFPE samples [58]."
> — Experiments · bears on: Claim 9, Standard · sample-prep chemistry (fresh-frozen vs FFPE) changes what transcripts are captured — a source of cross-protocol incomparability.

> "While progress has been made in aligning and integrating heterogeneous tissue slices across datasets, challenges remain in achieving automatic alignment that is independent of dataset origins, experimental conditions, or technical configurations, relying solely on tissue context."
> — Discussion · bears on: Claim 9, Standard · alignment independent of dataset origin / protocol / configuration is still unachieved.

> "However, heterogeneity, technical variability, and biological differences arising from developmental stages or disease progression often lead to misalignment in soft tissues. Additionally, scalability poses a major hurdle, as existing methods struggle with large datasets and lack efficient strategies for accurate volumetric reconstruction."
> — Discussion · bears on: Claim 9, Claim 10, Standard · technical/biological variability causes misalignment; methods do not scale to large datasets or accurate 3D reconstruction.

> "Furthermore, while histology images are often included as auxiliary input in ST alignment and integration, very few existing tools effectively leverage their full potential."
> — Discussion · bears on: Axis A (imaging), Claim 8 · the morphology/imaging modality is under-exploited even when available.

> "While this review serves as a detailed guide and highlights the potential for robust ST alignment and integration solutions, it remains theoretical in nature and does not provide a proof of concept."
> — Conclusion · bears on: Claim 9 · self-conceded limitation: no empirical benchmarking, theoretical guide only.

> "Integrating multi-omics spatial data, including spatial proteomics and metabolomics, alongside ST could provide more insightful biological context for understanding complex molecular interactions."
> — Conclusion · bears on: Claim 4, Claim 8, Axis A (proteome/metabolome) · authors concede that ST alone is insufficient and that spatial proteomics/metabolomics would add biological context.

> "Another key direction is improving cross-species ST alignment and integration techniques, allowing the comparison of gene expression patterns across model organisms and human tissues for better translational research. Additionally, developing methods that incorporate single-cell resolution data while preserving spatial context will further improve alignment precision."
> — Conclusion · bears on: Claim 10, Axis C · future need to combine single-cell resolution with preserved spatial context (resolution × spatial trade-off).

> "Moreover, ensuring standardization and reproducibility in ST data alignment through benchmark datasets and evaluation frameworks is crucial for advancing the field."
> — Conclusion · bears on: Claim 9, Standard · explicit call for standardization, reproducibility, and benchmark datasets/evaluation frameworks.

> "Currently, there exist at least 24 different methodologies (as shown in Table 2) proposed to address the specific challenge of aligning and integrating multiple tissue slices in ST (a few of them are still in preprint)."
> — Introduction · bears on: Claim 2, Claim 9 · ≥24 tools target multi-slice ST alignment/integration (scale of activity).

> "To date, only a handful of review papers exist; notably, one by Liu et al. [8], which compares a mere five alignment and integration tools, and another by Hu et al. [9], which benchmarks five alignment tools and five integration tools separately."
> — Introduction · bears on: Claim 9, Standard · prior benchmarking/review coverage of the field is thin.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq loses spatial info | "single-cell “omics” methods… require cell isolation, which also disrupts spatial context" / Introduction | supports |
| Claim 2 — ST > scRNA/bulk for some tasks | "better biological insights… compared to… scRNA and bulk-RNA" / Introduction | supports |
| Axis C — Spatial (subcellular→tissue) | "loss of z-axis information… reconstruct the 3D structure"; "spatial dependency and spatial heterogeneity" / Intro, Challenges | supports |
| Claim 3 / Axis B — temporal trajectory | "heart tissue slices taken at different stages of development"; "collected at different time-points or stages" / Scope, Significance | nuances |
| Claim 4 — modalities orthogonal / RNA insufficient | "Integrating multi-omics spatial data, including spatial proteomics and metabolomics… could provide more insightful biological context" / Conclusion | supports |
| Claim 8 — multimodal integration needed | "multi-omics data integration tools… were excluded"; "very few existing tools effectively leverage [histology images]" / Selection, Discussion | supports |
| Claim 9 / Standard — silos, incomparability, no standards | "ensuring standardization and reproducibility… through benchmark datasets"; "independent of dataset origins, experimental conditions, or technical configurations" / Conclusion, Discussion | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "resolution and scale are lower than in scRNA"; "55 μm… 10 μm… 0.22 μm"; "8–10 μm tissue thickness… cells overlapping" / Intro, Across-datasets, Experiments | supports |
| Claim 7 — microenvironment / neighborhood shapes state | "neighboring regions… similar gene expression profiles"; reconstruct "tissue micro-environments" / Challenges, IPR | supports |
| Axis A — imaging/morphology modality | "histology images… cell density, tissue boundaries… multimodal nature of ST data" / Problem description | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 | Task-scope matrix: homogeneous vs heterogeneous alignment × within-dataset vs across-dataset; rows for input source, overlap (full / maximum / partial / none), protocols, mapping requirements, pre-alignment adjustments. |
| Table 2 | The 24 reviewed tools sorted into 3 families: Statistical mapping (10 tools — Splotch, GPSA, Eggplant, PRECAST, PASTE, PASTE2, OTVI, DeST-OT, ST-GEARS, GraphST), Image processing & registration (4 — STIM, STaCker, STalign, STUtility), Graph-based (10 — SpatiAlign, STAligner, Graspot, ATAT, MaskGraphene, STAIR, SLAT, SPIRAL, BiGATAE, SPACEL); with datasets, downstream analyses, evaluation measures, and homogeneous/heterogeneous scope per tool. |
| Table 3 | ST technology resolutions (μm): 10x Genomics / Visium 55; Slide-seq 10; Slide-seqV2 10; MERFISH 0.1; SeqFISH+ 0.6; Stereo-seq 0.5; GeoMX DSP "Varies"; Xenium 0.2; Visium HD 2; HDST 2; STARmap 2 — plus input material (fresh frozen / FFPE / fixed cells) and species. |
| Numbers | Visium: up to 5000 spots/slice, 1–30 cells/spot; ST spot generally 1–100 cells; cross-platform resolution 55 μm → 10 μm → 0.22 μm; ≥24 alignment/integration tools; prior reviews covered only ~5 tools each; tissue section thickness 8–10 μm; DLPFC dataset 12 slices from 3 samples (4 adjacent each). |

---

## Primary Sources Behind Key Quotes
- ST preserves spatial context / original spatial transcriptomics method → Stahl PL, Salmén F, Vickovic S et al. Science 2016;353:78–82 (ref 30).
- PASTE (optimal-transport slice alignment, foundational tool) → Zeira R, Land M, Strzalkowski A et al. Nat Methods 2022;19:567–75 (ref 7).
- STAligner (cross-condition/technology/developmental-stage integration; mouse embryo time stages) → Zhou X, Dong K, Zhang S. Nat Comput Sci 2023;3:894–906 (ref 10).
- STalign (diffeomorphic registration; cross-resolution MERFISH↔Visium alignment) → Clifton K, Anant M, Aihara G et al. Nat Commun 2023;14:8123 (ref 12).
- GPSA (deep Gaussian-process alignment; breast-cancer multi-slice) → Jones A, Townes FW, Li D et al. Nat Methods 2023;20:1379–87 (ref 16).
- DeST-OT (spatiotemporal alignment across developmental stages, axolotl) → Halmos P, Liu X, Gold J et al. RECOMB 2024, pp. 434–7 (ref 18).
- Benchmarking of clustering/alignment/integration methods (comparability) → Hu Y, Xie M, Li Y et al. Genome Biol 2024;25:212 (ref 9).
- Stereo-seq spatiotemporal atlas of mouse organogenesis (time-stage slices) → Chen A, Liao S, Cheng M et al. Cell 2022;185:1777–92 (ref 43).
- DLPFC reference dataset (6-layer human cortex, ground-truth annotations) → Maynard KR, Collado-Torres L, Weber LM et al. Nat Neurosci 2021;24:425–36 (ref 47).
- GeoMX DSP multiplex protein + RNA spatial profiling (relevant to spatial-proteomics direction) → Merritt CR, Ong GT, Church SE et al. Nat Biotechnol 2020;38:586–99 (ref 58).

---

## Flags
- [ ] Metadata unverified: **Journal/venue not stated anywhere in the cleaned text.** Internal cues (NSF Open Access funding note; author-contribution + "Conflict of interest / Funding / Data availability" section layout; "Brief Bioinform" appearing as a *cited* journal in ref 48) are suggestive of an Oxford journal such as Briefings in Bioinformatics but are NOT confirmation — do not cite a venue without checking the DOI/landing page.
- [ ] Metadata unverified: **No DOI for this article and no received/accepted/published dates appear in the text.** All `10.xxxx/…` strings found by grep belong to the reference list, not to this paper. Several references cite 2025 works (refs 22, 23), so the article is plausibly 2025, but this is inference, not text-confirmed.
- [ ] Read at source: PASTE (ref 7) and STAligner (ref 10) for spatial slice integration and developmental-stage alignment; DeST-OT (ref 18) for spatiotemporal optimal transport; Hu et al. benchmark (ref 9) for cross-method comparability; Stahl 2016 (ref 30) for the founding spatial transcriptomics claim — cite these first-hand rather than via this review.
- [ ] Interpretation caveat (not a source error): "multi-modality" in this paper means gene expression + spatial coordinates + histology image, NOT multi-omics; the review explicitly excludes multi-omics (e.g., ST+scRNA) integration tools. "Temporal" coverage means aligning different physical slices sampled at different time points/stages, never tracking the same cell over time — relevant when deploying for Claim 3 / Axis B.
- [ ] Source inconsistency (minor, OCR/cleaning artifacts in cleaned MD): "10 Genomics" / "10 Visium" appear where "10x Genomics" / "10x Visium" is meant; ref 19 (Graspot) journal line is split across lines 267–269; ref 31 contains stray markup ("0:italic …"). Quotes above reproduce the cleaned text as-is.
