# Spatial omics: applications and utility in profiling the tumor microenvironment — Source Index

**Authors:** Ji‑Eun See, Sarah Barlow, Wani Arjumand, Hannah DuBose, Felipe Segato Dezem, Jasmine Plummer [printed in full names in the source]
**Journal / Venue:** unverified; see Flags (labeled "MINI REVIEW"; "© The Author(s) 2025"; Open Access CC BY-NC-ND; "Springer Nature" Publisher's Note — journal name not printed in body text)
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/15 - Spatial omics - applications and utility in profiling the tumor microenvironment_cleaned.md

---

## In One Sentence
A mini-review surveying current spatial-omics technologies (sequencing-based and imaging-based, transcriptomic and proteomic) and computational pipelines, then cataloguing their application to mapping the tumor microenvironment (TME) and the open challenges (resolution, multi-omics integration, standardization, cost) on the path to clinical precision oncology.

## Orientation (non-binding)
Strongly feeds our spatial axis (axis C) and claim 2 (single-cell/bulk lose spatial context): the paper repeatedly states that bulk and single-cell sequencing cannot resolve spatial context or physical cell–cell interactions, and that spatial assays preserve native tissue architecture. It also feeds claim 7 (microenvironment/spatial organization shapes cell state and therapy response), claim 6 / axis A (high-multiplex spatial proteomics is feasible and clinically near-term), claim 8 (multi-omics integration), claim 9 (absence of standardized protocols → poor cross-platform reproducibility), and claim 10 (the resolution × coverage × scalability × cost trade-off). It can serve as BOTH support (spatial/proteomic data are needed and increasingly tractable) and as a candid catalogue of the exact gaps our thesis is about (no standards, sparse/noisy data, integration unsolved). It is cancer/TME-scoped; treat the oncology specifics as illustrative, not as our subject.

---

## Load-Bearing Excerpts

> "Traditional genomic approaches, such as bulk RNA sequencing, have been instrumental in analyzing RNA to infer overall tissue characteristics. However, these methods lack spatial resolution, which limits their ability to identify where specifc transcripts originate within the tissue architecture and hinders the understanding of cellular interactions in situ."
> — §1.1 The evolution of spatial omics technology · bears on: claim 2, axis C · bulk RNA-seq lacks spatial resolution and cannot localize transcripts or in-situ interactions.

> "The advent of single-cell transcriptomics marked a major advance, enabling the dissection of transcriptomes at the level of individual cells… Yet, despite this granularity, single-cell approaches could not defnitively resolve spatial context or confrm physical interactions between cells within native tissue environments [1, 2]."
> — §1.1 · bears on: claim 2, axis C · single-cell transcriptomics still cannot resolve spatial context or confirm physical cell–cell interactions.

> "Spatial transcriptomics technologies were developed to bridge this gap. Initial methods such as laser-capture microdissection and targeted region-specifc RNA sequencing enabled transcriptomic analysis in defned tissue areas, but were limited in throughput and scalability [3–5]."
> — §1.1 · bears on: claim 10, axis C · early spatial methods traded throughput/scalability for spatial localization.

> "These methods rely on spatially indexed surfaces—such as barcoded glass slides (e.g., 10 × Genomics Visium), patterned DNA nanoball arrays (e.g., BGI Stereo-seq), or barcoded beads (e.g., Curio Slide-seq)—to capture RNA molecules in a spatially informed manner [9]."
> — §1.2 Sequencing-based spatial omics · bears on: axis C, claim 2 · named sequencing-based spatial platforms and their spatial-indexing chemistry.

> "Platforms like GeoMx Digital Spatial Profler—combining sequencing with region-specifc profling—and DBIT-seq—using fuidic delivery of the barcodes, allowing for multimodal spatial profling assays (e.g., RNA, protein and epigenomics)—further expand the utility of sequencing-based approaches [10, 11]."
> — §1.2 · bears on: claim 8, axis A, axis C · spatial platforms already extend to multimodal (RNA + protein + epigenomic) profiling.

> "These methods require prior knowledge of target transcripts, as they rely on the design of specifc, barcoded oligonucleotide probes that hybridize to selected mRNA species."
> — §1.3 Imaging-based spatial transcriptomics · bears on: claim 10 · imaging-based ISH/ISS require predefined target panels (no de-novo discovery).

> "A signifcant advantage of imaging-based transcriptomics is the preservation of tissue architecture and single-cell spatial resolution, which is particularly valuable for resolving fne-grained structures such as tumor margins, immune cell niches, and developmental gradients [15]."
> — §1.3 · bears on: claim 2, claim 7, axis C · imaging-based spatial omics preserves architecture and single-cell spatial resolution down to niches and gradients.

> "Imaging-based spatial proteomics leverages similar principles to transcriptomic assays but focuses on detecting and spatially mapping protein expression across tissues."
> — §1.4 Imaging-based spatial proteomics · bears on: claim 6, axis A, axis C · spatial proteomics maps protein expression in situ.

> "Sequential immunofuorescence (seqIF-COMET) and other cyclic immunofluorescence (CycIF) methods expand on traditional immunohistochemistry by performing repeated rounds of staining, imaging, and signal removal to profle up to 100 protein targets in the same tissue section [16, 17]."
> — §1.4 · bears on: claim 6, axis A · cyclic-IF spatial proteomics profiles up to 100 protein targets in one section.

> "Other platforms, such as MIBI (multiplexed ion beam imaging) and IMC (imaging mass cytometry), use metal isotope-tagged antibodies and time-of-fight mass spectrometry to detect dozens of proteins in parallel, ofering exceptional multiplexing without the limitations of spectral overlap in fuorescence-based systems."
> — §1.4 · bears on: claim 6, axis A · mass-spectrometry-based spatial proteomics (MIBI, IMC) detects dozens of proteins in parallel.

> "Proteomic assays are often integrated with transcriptomic spatial data to provide a more comprehensive, multimodal view of tissue organization and cellular phenotypes."
> — §1.4 · bears on: claim 4, claim 8, axis A · proteomic + transcriptomic spatial data are integrated for a more comprehensive multimodal view.

> "While proteomics is inherently limited by the availability and specifcity of antibodies, advances in antibody validation and new multiplexing chemistries continue to expand target panels."
> — §1.4 · bears on: claim 6, axis A · spatial proteomics is constrained by antibody availability/specificity but panels are expanding.

> "Imaging-based proteomics also benefts from high spatial fdelity, making it ideal for mapping protein expression at the level of cell–cell contacts and tissue microenvironments (Fig. 1)."
> — §1.4 · bears on: claim 6, claim 7, axis A, axis C · spatial proteomics resolves protein expression at cell–cell-contact and microenvironment scale.

> "Trajectory inference methods adapted for spatial contexts (e.g., Monocle 3 with spatial anchoring or spatial pseudotime models) can reveal developmental or pathological gradients across tissue landscapes [31, 32]."
> — §1.5 Computational methods for spatial data analysis · bears on: claim 3, axis B · trajectory/pseudotime methods are used to infer temporal gradients from (static) spatial data.

> "For example, statistical models such as SpatialDE [26] and SPARK [28] assume smooth spatial variation, which may not fully capture abrupt transitions in heterogeneous tissues such as tumors."
> — §1.5 · bears on: claim 1, claim 9 · spatial analysis tools carry built-in assumptions that fail on heterogeneous/abrupt tissue.

> "Similarly, reference-based mapping frameworks such as Tangram and InsitutypeML depend heavily on the quality and robustness of single-cell reference atlases, potentially including biased cell-type annotation in poorly characterized tissue areas."
> — §1.5 · bears on: claim 1, claim 9 · reference/atlas-dependent annotation methods inherit reference-atlas quality limits and bias.

> "SiGra [33] and xSiGra [34] employ graph neural networks to integrate spatial transcriptomics and proteomics information, revealing latent spatial domains and higher-order cellular interactions… These methods represent a shift toward multi-modal, predictive spatial OMICs analysis, expanding its analytical depth and translational potential."
> — §1.5 · bears on: claim 8, axis A · GNN frameworks integrate spatial transcriptomics + proteomics toward multimodal predictive analysis.

> "Spatial omics uniquely revealed how immune and tumor cells were organized and interacted within the PCNSL TME— specifically, the location-dependent immune suppression and signaling patterns that traditional single-cell or bulk analyses could not detect."
> — §2 Application of spatial omics technology to cancer research · bears on: claim 2, claim 7, axis C · spatial omics detected location-dependent immune suppression/signaling invisible to single-cell or bulk.

> "These spatial patterning—distancebased segregation of cell clusters and EcoCellTypes enrichments—correlate with patient outcomes."
> — §2 (Croizer et al.) · bears on: claim 7, axis C · spatial arrangement (cell-cluster distance, niche enrichment) correlates with clinical outcome.

> "These studies demonstrate that spatial omics goes beyond conventional bulk or single-cell analyses to understand cellular identity and interactions within the TME in a spatial context. Spatial information allows researchers to understand not only the role of each cell, but also where and how they communicate with one another, providing crucial insights for a deeper understanding of cancer behavior and treatment response."
> — §2 · bears on: claim 2, claim 7, axis C · spatial context adds where/how cells communicate, beyond bulk/single-cell identity alone.

> "Pseudotime spatial omics analysis showed that the activation of oncogenic pathways and higher copy number variations were observed in IDC, and T cells were converted to exhaustion through co-inhibitory interactions such as NECTIN2–TIGIT."
> — §2 (Cai et al.) · bears on: claim 3, claim 7, axis B · pseudotime applied to spatial data to order tumor progression and T-cell exhaustion.

> "Sun et al. mapped spatial gene expression in hypoxic and normoxic tumor regions and found that hypoxia induced signifcant changes in tumor cell subpopulations that increase resistance and promote invasion, particularly in hypoxic areas."
> — §2 · bears on: claim 7, axis C · local microenvironment (hypoxia) drives changes in tumor-cell state, resistance and invasion.

> "Vahid et al. performed spatial proteomics profling of tumor and stromal compartments in 102 non-small-cell lung cancer (NSCLC) patients to identify protein signatures associated with overall survival rates… stromal CD56 expression correlates with better survival, whereas tumoral B-cell lymphoma extra large (BCLXL) and B7-H3 were linked to poorer outcomes."
> — §2 (Vahid et al. / YaghoubiNaei) · bears on: claim 5, claim 6, axis A · spatial proteomics yields prognostic protein signatures (function/phenotype) at cohort scale.

> "As these technologies evolve beyond simple mapping tools into integrated platforms, they are revealing that core functional characteristics of tumor biology such as subclonal evolution, immune evasion, metabolic adaptation, and therapeutic resistance are intimately linked to spatial organization."
> — §2 · bears on: claim 7, axis C · subclonal evolution, immune evasion, metabolic adaptation and resistance are tied to spatial organization.

> "A major technical challenge with current spatial omics platforms is their limited resolution, especially when it comes to distinguishing individual cells… because it is not assigned at an individual cell level, it becomes computationally challenging to separate gene activity accurately and restricts the analysis of cellular heterogeneity, which is important for cancer research."
> — §3 Unanswered questions and challenges · bears on: claim 10, axis C · many platforms lack true single-cell resolution, limiting heterogeneity analysis.

> "High-resolution imagingbased transcriptomic approaches ofer greater resolution but are limited in scale and gene coverage and require predefned probe panels, which may limit the discovery of novel transcripts or rare cell populations."
> — §3 · bears on: claim 10 · resolution gained at the cost of scale, gene coverage, and discovery breadth (the trade-off).

> "Developing platforms that balance high resolution, comprehensive transcriptome coverage (which was recently launched by the CosMX platform) and scalability is still a signifcant challenge, particularly when studying tumors where the spatial distribution of rare cell populations is important."
> — §3 · bears on: claim 10 · explicit statement of the resolution × coverage × scalability trilemma as an unsolved challenge.

> "Tumors are formed for various reasons, including gene expression, mutations, chromatin state, protein expression, and metabolic state, each of which has its own impact on cancer progression and treatment resistance. Integrating spatial omics with multiomics data can provide a more comprehensive understanding of cancer biology."
> — §3 · bears on: claim 4, claim 8, axis A · distinct molecular layers (expression, mutation, chromatin, protein, metabolism) each contribute independently → motivates multi-omics integration.

> "However, spatial omics data tend to be sparse and noisy, and in certain cases, genes can be under-detected due to molecular capture limitations, which limit biological interpretability and reduce the accuracy of integration with other modalities at single-cell resolution [52]."
> — §3 · bears on: claim 8, claim 9 · spatial data are sparse/noisy with under-detection, degrading cross-modality integration.

> "Moreover, spatial datasets may contain novel or rare cell types that are not present in scRNA-seq references, and assuming complete overlap in cell populations during data integration can introduce bias or misinterpretation [53]."
> — §3 · bears on: claim 1, claim 9 · reference-overlap assumptions in integration introduce bias when populations differ.

> "Few standardized protocols and analytical frameworks exist for integrating multi-modal datasets, which hinder efective data alignment among data sets."
> — §3 · bears on: claim 9, axis standard · few standardized protocols exist for multimodal integration → poor data alignment.

> "SPIRAL, developed by Guo et al., is an analytical tool that performs well in batch integrations and tissue structure delineation across samples from diferent spatial technologies, but the integration of datasets with varying spatial resolution is still a challenge and has limitations under particular experimental conditions and platforms [54]."
> — §3 · bears on: claim 9, axis standard · cross-technology/variable-resolution integration remains unsolved even for purpose-built tools.

> "There is a need for robust and generalizable algorithms and integration tools capable of handling multiomics data at the single-cell level across diferent experimental settings and biological contexts [56]."
> — §3 · bears on: claim 8, claim 9 · explicit call for generalizable single-cell multi-omics integration across settings.

> "The absence of these standardized protocols reduces reproducibility across platforms and laboratories, preventing spatial omics from being efectively implemented in the clinical area [57]."
> — §3 · bears on: claim 9, axis standard · lack of standards → poor cross-platform/cross-lab reproducibility blocking clinical use.

> "Moreover, the clinical predictive or prognostic utility of spatial omics has not been sufciently validated through large-scale clinical trials to date."
> — §3 · bears on: claim 9 · spatial-omics clinical utility not yet validated at scale.

> "In addition, the high cost of spatial omics experiments is a hurdle to clinical translation… These economic constraints limit the scale of studies that include heterogeneous patient cohorts and ultimately slow the clinical translation of spatial omics in cancer research."
> — §3 · bears on: claim 10 · high cost/infrastructure constrains cohort scale (throughput-vs-cost dimension).

> "To move toward clinical translation, spatial omics assays must meet stringent regulatory and technical standards akin to those that facilitated the clinical adoption of next-generation sequencing (e.g., MACQC guidelines)."
> — §3 · bears on: claim 9, axis standard · calls for NGS-like regulatory/QC standards (e.g., MAQC-type guidelines) for spatial assays.

> "However, spatial proteomics has a clear path to clinical practice because it is uniquely positioned with current diagnostic use antibodybased panels."
> — §3 · bears on: claim 6, axis A · spatial proteomics has a near-term clinical path via existing antibody-based diagnostics.

> "Foundation models like CellLM and scFoundation link cellular states to drug response and metastatic potential, highlighting the increasingly important role AI and ML play as predictive engines for precision oncology [58]."
> — §3 · bears on: claim 1 · foundation models proposed as predictive engines linking cell state to drug response (the data-driven modeling direction we critique).

> "A major frontier lies in the development of standardized protocols for integrating multi-omics modalities— such as spatial transcriptomics, proteomics, epigenomics, and metabolomics—which would allow for a more holistic understanding of tumor biology and disease progression."
> — §4 Conclusion and future perspectives · bears on: claim 8, claim 9, axis A, axis standard · names the multi-omics integration frontier (transcriptomics + proteomics + epigenomics + metabolomics) and the need for standardized protocols.

> "Importantly, spatial omics not only identifes molecular features but also uncovers functional landscapes within tumors, including spatial gradients of tumor evolution, immune–tumor crosstalk, and localized microenvironmental infuences on therapy response."
> — §4 · bears on: claim 7, axis C · spatial gradients and microenvironmental context shape tumor evolution and therapy response.

> "Ultimately, the convergence of high-resolution spatial measurements, multi-modal integration, and advanced computational tools will redefne how we study human disease—bringing spatial biology from bench to bedside."
> — §4 · bears on: claim 8, axis C, axis standard · positions spatial resolution + multi-modal integration + computation as the convergence needed.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data bottleneck / data-driven generalization | "reference-based mapping frameworks… depend heavily on the quality and robustness of single-cell reference atlases" §1.5; "Foundation models like CellLM and scFoundation…" §3 | nuances |
| Claim 2 — scRNA-seq/bulk lose spatial | "single-cell approaches could not defnitively resolve spatial context" §1.1; "location-dependent immune suppression… that traditional single-cell or bulk analyses could not detect" §2 | supports |
| Claim 3 — destructive measurement / no paired temporal | "Trajectory inference methods adapted for spatial contexts… spatial pseudotime models" §1.5; "Pseudotime spatial omics analysis…" §2 | nuances |
| Claim 4 — modalities orthogonal / non-substitutable | "gene expression, mutations, chromatin state, protein expression, and metabolic state, each of which has its own impact" §3; "more comprehensive, multimodal view" §1.4 | supports |
| Claim 5 — protein/metabolic modalities essential to phenotype | "stromal CD56… better survival, whereas tumoral BCLXL and B7-H3… poorer outcomes" §2 | supports |
| Claim 6 — high-throughput spatial proteomics feasible | "profle up to 100 protein targets in the same tissue section" §1.4; "spatial proteomics has a clear path to clinical practice" §3 | supports |
| Claim 7 — spatial organization shapes cell state / response | "core functional characteristics… intimately linked to spatial organization" §2; "hypoxia induced signifcant changes in tumor cell subpopulations" §2 | supports |
| Claim 8 — multimodal orthogonal info / needs integration | "Integrating spatial omics with multiomics data can provide a more comprehensive understanding" §3; "standardized protocols for integrating multi-omics modalities" §4 | supports |
| Claim 9 — data islands / incomparable / no standard | "absence of these standardized protocols reduces reproducibility across platforms and laboratories" §3; "Few standardized protocols and analytical frameworks exist" §3 | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "balance high resolution, comprehensive transcriptome coverage… and scalability is still a signifcant challenge" §3; "limited in scale and gene coverage and require predefned probe panels" §3 | supports |
| Axis A — modality (protein / epigenomic / metabolomic) | "multimodal spatial profling assays (e.g., RNA, protein and epigenomics)" §1.2; "spatial transcriptomics, proteomics, epigenomics, and metabolomics" §4 | supports |
| Axis B — temporal | "spatial pseudotime models… developmental or pathological gradients" §1.5; "Stelar… Models tissue evolution across timepoints" Table 2 | nuances |
| Axis C — spatial | "preservation of tissue architecture and single-cell spatial resolution" §1.3 | supports |
| Axis standard — QC / cross-platform / integration | "stringent regulatory and technical standards akin to… next-generation sequencing (e.g., MACQC guidelines)" §3 | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 | Comparison of spatial-omics platforms across Resolution / Gene throughput / Tissue type / Advantages / Limitations. Sequencing-based: GeoMx (20–300 cells per ROI, whole transcriptome + proteins, non-destructive — slides reusable, not single-cell), Stereo-seq (~0.5–2 µm spot, subcellular, whole transcriptome), Visium (~55 µm spot, 10–20 cells), Visium HD (~2 µm pixel, single-cell/subcellular, large data size), Slide-seq (~10 µm bead, low cost, not FFPE), DBiT-seq (~10 µm pixel, RNA + protein + epigenetic marks). Imaging-based: CosMx (~0.5–1.2 µm, ~1000–whole-transcriptome + proteins), Xenium (~200 nm, ~5000-gene targeted panels, high cost), MERSCOPE (~100–200 nm, ~10,000-gene targeted panels). |
| Table 2 | Computational pipeline catalogue grouped by category: spatial-transcriptomics core analysis (Seurat+STUtility, Giotto, BayesSpace, SpatialDE/2, SPARK/SPARK-X, SpatialScope, Spiral, Spacia, SpaCell, Cell2location, Tangram, Stelar), spatial cell–cell communication (CellPhoneDB, NicheNet, Transceek, InsituTypeML), spatial proteomics/imaging (QuPath, histoCAT, Vitessce), segmentation/visualization (CellPose, StarDist, Napari, Monocle3), AI/DL/ML models (ScFoundation, scGPT, Sigra/XSigra, SpaGCN, spaLLM, STAGATE, SpatialGlue, stLearn) — with method, I/O formats and references. Note: "Stelar … Models tissue evolution across timepoints" (time-series ST) is the only explicitly temporal entry. |
| Fig. 1 | Schematic overview of three fundamental spatial-omics methodologies and high-multiplex tissue profiling. |
| Fig. 2 | Schematic of spatial-omics applications in cancer research and clinical translation. |
| Fig. 3 | Schematic of current challenges and future directions (technological, analytical, biological) for spatial omics in cancer. |
| Cohort numbers | TNBC spatial study: 92 patients, 9 spatial archetypes (Wang et al.); NSCLC spatial proteomics: 102 patients (Vahid et al.); rare breast-cancer study: 11 triple-negative tumors incl. 3 claudin-low + 4 MpBC (Coutant et al.). |

---

## Primary Sources Behind Key Quotes
- Single-cell cannot resolve spatial context / physical interactions [1, 2] → Tang, F., et al. (2009). mRNA-Seq whole-transcriptome analysis of a single cell. Nature Methods, 6:377–382 (ref 1); Macosko, E. Z., et al. (2015). Highly parallel genome-wide expression profiling of individual cells using nanoliter droplets. Cell, 161:1202–1214 (ref 2).
- MERFISH subcellular RNA profiling [6] → Chen, K. H., et al. (2015). Spatially resolved, highly multiplexed RNA profiling in single cells. Science, 348:aaa6090 (ref 6).
- GeoMx multiplex digital spatial profiling of proteins + RNA [10] → Merritt, C. R., et al. (2020). Multiplex digital spatial profiling of proteins and RNA in fixed tissue. Nature Biotechnology, 38:586–599 (ref 10).
- DBiT-seq high-spatial-resolution multi-omics [11] → Liu, Y., et al. (2020). High-spatial-resolution multi-omics sequencing via deterministic barcoding in tissue. Cell, 183:1665–1681.e18 (ref 11).
- CODEX multiplexed protein imaging [18] → Goltsev, Y., et al. (2018). Deep profiling of mouse splenic architecture with CODEX multiplexed imaging. Cell, 174:968–981.e15 (ref 18).
- MIBI / IMC metal-tagged spatial proteomics [19, 20] → Angelo, M., et al. (2014). Multiplexed ion beam imaging of human breast tumors. Nature Medicine, 20:436–442 (ref 19); Giesen, C., et al. (2014). Highly multiplexed imaging of tumor tissues with subcellular resolution by mass cytometry. Nature Methods, 11:417–422 (ref 20).
- Gene representation bias / under-detection in spatial data [52] → Li, X., & Qiu, P. (2024). Gene representation bias in spatial transcriptomics. Journal of Bioinformatics and Computational Biology, 22:2450007 (ref 52).
- Reference-overlap bias in integration [53] → Yuan, M., et al. (2024). SPANN: Annotating single-cell resolution spatial transcriptome data with scRNA-seq data. Briefings in Bioinformatics. doi:10.1093/bib/bbad533 (ref 53).
- SPIRAL cross-technology integration [54] → Guo, T., et al. (2023). SPIRAL: Integrating and aligning spatially resolved transcriptomics data across different experiments, conditions, and technologies. Genome Biology, 24:241 (ref 54).
- Principles/challenges of modeling temporal AND spatial omics [56] → Velten, B., & Stegle, O. (2023). Principles and challenges of modeling temporal and spatial omics data. Nature Methods, 20:1462–1474 (ref 56). [Highest-value primary read for our temporal+spatial axes.]
- Standards/reproducibility → GESTALT alliance [57] → Plummer, J. T., et al. (2025). Introducing the global alliance for spatial technologies (GESTALT). Nature Genetics, 57:275–279 (ref 57).
- Foundation models linking cell state to drug response [58] → Pan, Y., et al. (2025). Large language models for translational cancer informatics. JCO Clinical Cancer Informatics, 9:2500108 (ref 58).

---

## Flags
- [ ] Metadata unverified: Journal/venue name is not printed in the body text. Source only shows "MINI REVIEW", "Received: 10 August 2025 / Accepted: 21 November 2025 © The Author(s) 2025", Open Access CC BY-NC-ND, and a "Publisher's Note … Springer Nature" line. Venue should be confirmed externally before citation.
- [ ] Metadata unverified: The paper's own DOI is not present in the cleaned text (only reference DOIs appear). "not found in text."
- [ ] Author-initial inconsistency in source: Author contribution lists "S.B., A.W., and H.C. generated figures," but the author list gives Hannah DuBose (would be H.D., not H.C.) and Wani Arjumand (listed first-name-first); initials in the contribution block do not cleanly map to the printed full names. Initials reproduced as printed.
- [ ] Read at source (temporal + spatial axes): Velten & Stegle 2023 (Nature Methods, ref 56) — "Principles and challenges of modeling temporal and spatial omics data" — is the directly on-thesis primary source for our axes B and C; cite first-hand rather than via this review.
- [ ] Read at source (standards axis): Plummer et al. 2025 GESTALT (Nature Genetics, ref 57) — primary statement on the standards/reproducibility gap; cite first-hand for claim 9.
- [ ] OCR artifacts preserved verbatim: the cleaned source contains broken fi/ff ligatures (e.g., "profling", "ofering", "infltration", "fbroblasts", "MACQC" where MAQC is likely intended). Quotes are reproduced exactly as in the source; flag for the writer not to propagate typos into the final draft.
- [ ] Scope note: This is a cancer/TME-focused review; all biological specifics (PCNSL, PDAC, NSCLC, TNBC, etc.) are illustrative for our perspective, not subject matter. Captured only where they substantiate a roadmap claim (spatial/microenvironment/proteomic/standardization).
