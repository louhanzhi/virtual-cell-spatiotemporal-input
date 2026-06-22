# LIANA+ provides an all-in-one framework for cell–cell communication inference — Source Index

**Authors:** Daniel Dimitrov, Philipp Sven Lars Schäfer, Elias Farr, Pablo Rodriguez-Mier, Sebastian Lobentanzer, Pau Badia-i-Mompel, Aurelien Dugourd, Jovan Tanevski, Ricardo Omar Ramirez Flores & Julio Saez-Rodriguez
**Journal / Venue:** Nature Cell Biology, 2024 (Technical Report) — volume/issue/pages unverified; see Flags
**DOI:** doi:10.1038/s41556-024-01469-w
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/39 - LIANA+ - an all-in-one framework for cell-cell communication inference_cleaned.md

---

## In One Sentence
LIANA+ is a scalable Python framework that unifies and extends many existing cell–cell communication (CCC) inference methods into synergistic components, enabling CCC inference from dissociated single-cell and spatially resolved single- and multi-omics data (transcriptome plus metabolome), across single and multiple conditions, built on a shared prior-knowledge base and standardized scverse input/output formats.

## Orientation (non-binding)
This is a CCC methods/tool paper, not a virtual-cell or data-standard paper, so its case-study biology (dopamine/MSN signalling; FN1/SPP1 fibrosis mechanisms) is largely off-roadmap. Its value to our thesis is as a source of **concessions about the data foundation**: it repeatedly states that dissociated single-cell data loses tissue architecture (spatial), that transcriptomics-based inference is a co-expression proxy that "may not translate to the protein level," that spatial technologies face a coverage–resolution trade-off, and that CCC inference lacks ground-truth benchmarks. It most likely feeds Claims 2, 4, 7, 9 and 10, and (more weakly) the multi-omics-integration and temporal axes. It can serve as BOTH an example of the dissociated/RNA-proxy paradigm AND a self-aware critique of it — the downstream agent decides which.

---

## Load-Bearing Excerpts

> "The growing availability of single-cell and spatially resolved transcriptomics has led to the development of many approaches to infer cell–cell communication, each capturing only a partial view of the complex landscape of intercellular signalling."
> — Abstract · bears on: Claim 8 (multi-modal integration needed), Claim 9 (fragmentation / non-comparability) · each tool captures only a partial view, motivating a unifying framework.

> "All single-cell methods are based on multiple assumptions, including that gene co-expression across dissociated cells, or groups of cells, reflects CCC within tissues"
> — Introduction · bears on: Claim 2 (dissociation loses spatial), Claim 4 (RNA used as proxy) · single-cell CCC rests on the assumption that co-expression across dissociated cells stands in for communication within intact tissue.

> "Most methods have focused on protein-mediated interactions, predominantly inferred from transcriptomics data, and only a few from multi-omics data. As a consequence, other modes of intercellular signalling have been typically ignored except for limited metabolite-mediated CCC predictions from transcriptomics data."
> — Introduction · bears on: Claim 4 (modality narrowness — protein/metabolite inferred from RNA), Axis A (modality breadth) · the field is dominated by transcriptomics-derived protein interactions; other molecular mediators are typically ignored.

> "Emerging multi-omics technologies are anticipated to provide a broader picture of molecular mediators and in turn prompt the development of new CCC tools."
> — Introduction · bears on: Claim 4, Claim 8, Axis A · multi-omics is expected to broaden the set of measurable molecular mediators.

> "In some resources, the interactions are associated with pathways or transcriptional regulators, leading to multiple heterogeneous databases and potential inconsistencies caused solely by the choice of resource"
> — Introduction · bears on: Claim 9 (non-comparability / lack of standard) · results can differ purely because of which knowledge resource is chosen.

> "Finally, all these developments use various infrastructures, with each CCC tool being typically designed for a specific task or data type."
> — Introduction · bears on: Claim 9 (tool/infrastructure islands) · existing CCC tools are fragmented across incompatible infrastructures, each task- or data-type-specific.

> "LIANA+ uses standardized scverse input and output formats (Fig. 2a), enabling interoperability with external packages and the straightforward extensions of CCC approaches."
> — Results: LIANA+ as an all-in-one solution to model CCC · bears on: Claim 9 / Standard axis (standardization, interoperability) · adopts standardized formats to enable interoperability across packages.

> "A particular challenge of emerging spatial technologies is that, on a single tissue section, they can combine different technologies, and hence the observations from each technology may correspond to distinct spatial locations that need to be aligned."
> — Results: LIANA+ enables modelling CCC across spatial modalities · bears on: Claim 8, Claim 9 / Standard axis (cross-modality pairing, unified reference frame), Axis C (spatial) · multi-modal spatial data have non-coincident observations across modalities that must be aligned to a common coordinate system.

> "it provides a single statistic for the importance of each interaction in a slide but does not provide information about the region or locations where the interactions occur."
> — Results: LIANA+ infers local interactions at individual locations · bears on: Claim 7 (spatial localization), Axis C (subcellular→tissue resolution) · global spatial statistics lose where in the tissue an interaction happens, motivating location-level metrics.

> "However, it remains limited by a common coverage–resolution trade-off in most spatial technologies: they either quantify a limited fraction of molecules or they capture multiple cells within spots, relying on deconvolution to quantify cell-type frequencies within them."
> — Results: Ligand–receptor inference weakly reflects co-localization · bears on: Claim 10 (resolution × throughput trade-off), Axis C · spatial technologies trade molecular coverage against single-cell resolution, often needing deconvolution.

> "Leveraging Slide-tags, a recent technology capable of measuring full transcriptome single-nucleus data while also preserving spatial information, we evaluated spatially uniformed CCC methods using cell type and gene expression co-localization as an indirect ground truth—assuming that co-localization is a proxy of communication"
> — Results: Ligand–receptor inference weakly reflects co-localization · bears on: Claim 2 (spatial preservation vs dissociation), Claim 10, Axis C, Claim 9 (indirect ground truth) · uses a technology that preserves spatial information to test spatially agnostic methods, with co-localization standing in for true communication. [Note: "spatially uniformed" appears in the source; likely "spatially uninformed."]

> "We found weak associations between ligand–receptor interactions predicted in a spatially agnostic manner and the co-localization of their ligands, receptors and cell types"
> — Results: Ligand–receptor inference weakly reflects co-localization · bears on: Claim 2 (dissociated/spatially agnostic inference loses spatial truth), Claim 7 · spatially agnostic predictions correlate only weakly with actual spatial co-localization.

> "While early methods analysed CCC from single-condition datasets, increasing sample numbers and experimental design complexity have prompted various strategies to extract differential CCC insights."
> — Introduction · bears on: Claim 3 (cross-condition vs paired temporal — nuance) · differential CCC is extracted by comparing across conditions/samples rather than tracking the same cells over time.

> "These have previously been used to identify co-expression patterns between genes across spatial and pseudotime contexts"
> — Results: LIANA+ enables modelling CCC across spatial modalities · bears on: Claim 3 / Axis B (temporal as pseudotime, not paired observation — nuance) · temporal structure here is handled as pseudotime context, not real-time paired tracking.

> "In conclusion, using LIANA+ we captured perturbation-driven changes in dopamine's distribution and its associations with its canonical D2R receptor and MSN cell types 1 and 2."
> — Results: LIANA+ enables modelling CCC across spatial modalities · bears on: Claim 7 (perturbation response read out spatially), Axis A (metabolome) · a perturbation's effect on a metabolite's spatial distribution and its receptor/cell-type associations is recovered from spatial multi-omics.

> "Dissociated and spatially resolved data generation has commonly focused on transcriptomics, limiting CCC method development to protein-mediated interactions. Yet emerging multi-omics technologies enable the quantification of diverse molecules"
> — Discussion · bears on: Claim 4 (transcriptomics focus limits modality coverage), Axis A · concedes that the transcriptomics-centric data supply has constrained methods to protein-mediated interactions, with multi-omics needed to broaden them.

> "Single-cell technologies capture cellular heterogeneity but typically lose tissue architecture information during dissociation, leading to many false positives in spatially agnostic CCC inference, as our evaluations demonstrate."
> — Discussion · bears on: Claim 2 (dissociation erases spatial / tissue architecture), Claim 7 · dissociation discards tissue architecture, and spatially agnostic inference consequently yields many false positives.

> "Second, CCC from dissociated single-cell data remains limited to the co-expression of communication partners, which may not translate to the protein level, let alone imply a functional interaction."
> — Discussion (limitations) · bears on: Claim 4 (RNA co-expression ≠ protein ≠ function), Axis A · concedes that RNA co-expression is not equivalent to protein-level presence or to a functional interaction.

> "Likewise, while spatially resolved data is a step further from its dissociated counterparts, it is limited to the co-localization of molecules."
> — Discussion (limitations) · bears on: Claim 7 (spatial is co-localization proxy, not communication), Axis C · even spatial data only reports co-localization, not communication itself.

> "First, while each of its methods can flexibly infer interactions between any set of variables, they typically use prior knowledge, which is limited, often exhibiting biases and a trade-off between coverage and quality"
> — Discussion (limitations) · bears on: Claim 9 (knowledge-base bias / coverage–quality trade-off), Claim 1 · prior knowledge is limited and biased, with a coverage-versus-quality trade-off.

> "Finally, while our preliminary evaluations support the ability of LIANA+ to generate CCC insights across a range of technologies, systematic benchmarks of CCC methods are still pending. Ours and other evaluations remain limited by the lack of ground truth, using instead orthogonal modalities, such as spatial data or downstream signalling."
> — Discussion (limitations) · bears on: Claim 9 (benchmark comparability / lack of ground truth), Claim 1 · CCC lacks systematic benchmarks and ground truth; evaluation relies on orthogonal proxies.

> "In the meantime, LIANA+—like other CCC inference methods—remains a tool for hypothesis generation."
> — Discussion (limitations) · bears on: Claim 1 (inference yields hypotheses, not validated cell biology) · positions current CCC inference as hypothesis generation rather than established fact.

> "Additionally, LIANA+ facilitates the flexible construction of models, allowing for the integration of an arbitrary number of modalities, as illustrated by our application of multi-view modelling to study the relationships among metabolites, cell types and receptors."
> — Discussion · bears on: Claim 8 (multi-omics integration), Axis A · supports integrating an arbitrary number of modalities within one model.

> "we combined spatially informed multi-view modelling with local spatial metrics to examine the interactions of metabolites, receptors and cell types in a murine Parkinson's disease model. Our analysis revealed dopamine-mediated interactions in specific brain subregions, highlighting how LIANA+ addresses challenges to integrate different data modalities"
> — Discussion · bears on: Claim 5 (metabolite modality carries functional signal), Claim 8, Claim 7, Axis A (metabolome), Axis C · demonstrates a metabolite (dopamine) modality and its spatial localization, integrated with transcriptome/cell-type data.

> "We further envision LIANA+ to be a versatile tool for the study of CCC driven by diverse mediators, beyond protein-mediated and metabolite-mediated interactions, expanding the range of CCC events that could be studied, such as host–microbiome interactions"
> — Discussion · bears on: Claim 4, Axis A (modality breadth beyond protein/metabolite) · anticipates CCC studied via additional, non-protein, non-metabolite mediators.

> "Moreover, contextualizing prior knowledge to specific cell types, tissues or diseases can help to reduce erroneous predictions."
> — Discussion (limitations) · bears on: Claim 7 (tissue/context specificity matters), Claim 9 · context-specific knowledge reduces erroneous predictions.

> "For the inference of ligand–receptor interactions throughout this work, we used LIANA's consensus resource—a resource combining the curated ligand–receptor resources in OmniPath"
> — Methods: Spot calling evaluation using local metrics · bears on: Claim 9 / Standard axis · uses a consensus resource to mitigate resource-choice inconsistency.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data/inference bottleneck, weak generalization | "remains a tool for hypothesis generation" / Discussion; "systematic benchmarks … still pending" / Discussion | supports |
| Claim 2 — scRNA-seq / dissociation loses spatial | "typically lose tissue architecture information during dissociation" / Discussion; "gene co-expression across dissociated cells … reflects CCC" / Intro; "weak associations … spatially agnostic" / Results | supports |
| Claim 3 — destructive seq can't observe time in pairs | "various strategies to extract differential CCC insights" / Intro; "spatial and pseudotime contexts" / Results | nuances |
| Claim 4 — modalities orthogonal / RNA can't measure protein | "may not translate to the protein level, let alone … functional interaction" / Discussion; "protein-mediated interactions, predominantly inferred from transcriptomics" / Intro | supports |
| Claim 5 — protein/metabolite modalities indispensable to function | "dopamine-mediated interactions in specific brain subregions" / Discussion | supports |
| Claim 6 — high-throughput spatiotemporal proteomics feasible | (not addressed — paper is transcriptome/metabolome CCC, no proteomics measurement) | — |
| Claim 7 — spatial organization / microenvironment shapes state & perturbation | "does not provide information about the region or locations" / Results; "perturbation-driven changes in dopamine's distribution" / Results; "limited to the co-localization of molecules" / Discussion | supports / nuances |
| Claim 8 — multi-modal orthogonal info, need integration | "each capturing only a partial view" / Abstract; "integration of an arbitrary number of modalities" / Discussion | supports |
| Claim 9 — data/tool islands, non-comparability, lack of standard | "each CCC tool … designed for a specific task or data type" / Intro; "inconsistencies caused solely by the choice of resource" / Intro; "lack of ground truth" / Discussion; "standardized scverse input and output formats" / Results | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "a common coverage–resolution trade-off in most spatial technologies" / Results; "Slide-tags … full transcriptome … preserving spatial information" / Results | supports |
| Axis A — modality breadth | "other modes of intercellular signalling have been typically ignored" / Intro; "diverse mediators, beyond protein-mediated and metabolite-mediated" / Discussion | supports |
| Axis B — temporal | "pseudotime contexts" / Results; "differential CCC insights" across conditions / Intro | nuances |
| Axis C — spatial resolution (subcellular→tissue) | "distinct spatial locations that need to be aligned" / Results; "region or locations where the interactions occur" / Results | supports |
| Standard / integration | "standardized scverse input and output formats" / Results; "LIANA's consensus resource … combining … OmniPath" / Methods | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 4 | Benchmark of multiple ligand–receptor methods (re-implemented in LIANA+) against spatial co-localization of cell types and ligand–receptors as an assumed ground truth, across n = 5 slide-tags datasets; metrics AUROC, balanced accuracy, normalized F1 (0.5 = random). |
| Extended Data Fig. 1 | Scalability/efficiency benchmark of dissociated CCC methods and spatial local metrics on simulated datasets of 1,000–100,000 cells (runtime, peak RAM). |
| Dopamine R² (Results / Extended Data Fig. 3a) | Multi-view model explains dopamine intensity in the intact hemisphere (R² = 0.535) vs lesioned hemisphere (R² ≈ 0) — a perturbation (6-OHDA lesion) eliminates the spatial signal. |
| Tool count (Introduction) | "over 100 tools" have contributed to CCC inference — quantifies field fragmentation. |
| LR methods coupled (Results) | LIANA+ couples nine ligand–receptor methods with higher-order factorizations; eight local spatial metrics implemented. |

---

## Primary Sources Behind Key Quotes
- Dissociated CCC assumptions / choice-of-resource inconsistency / lack of ground truth → Dimitrov, D. et al. "Comparison of methods and resources for cell–cell communication inference from single-cell RNA-seq data." Nat. Commun. 13, 3224 (2022) [ref. 3]
- Emerging single-cell multi-omics broadening molecular mediators → Baysoy, A., Bai, Z., Satija, R. & Fan, R. "The technological landscape and applications of single-cell multi-omics." Nat. Rev. Mol. Cell Biol. 24, 695–713 (2023) [ref. 15]
- Coverage–resolution trade-off; single-cell & spatial multi-omics methods → Vandereyken, K., Sifrim, A., Thienpont, B. & Voet, T. "Methods and applications for single-cell and spatial multi-omics." Nat. Rev. Genet. 24, 494–515 (2023) [ref. 39]
- Spatial profiling technology landscape (coverage–resolution) → Moffitt, J. R., Lundberg, E. & Heyn, H. "The emerging landscape of spatial profiling technologies." Nat. Rev. Genet. 23, 741–759 (2022) [ref. 40]
- Slide-tags: full-transcriptome single-nucleus with preserved spatial information → Russell, A. J. C. et al. "Slide-tags enables single-nucleus barcoding for multimodal spatial genomics." Nature 625, 101–109 (2024) [ref. 41]
- Spatially resolved metabolome–transcriptome dataset (Parkinson's model) → Vicari, M. et al. "Spatial multimodal analysis of transcriptomes and metabolomes in tissues." Nat. Biotechnol. (2023), doi:10.1038/s41587-023-01937-y [ref. 26]
- Human myocardial infarction spatial multi-omic dataset → Kuppe, C. et al. "Spatial multi-omic map of human myocardial infarction." Nature 608, 766–777 (2022) [ref. 27]
- Cross-condition CCC factorization (Tensor-cell2cell) → Armingol, E. et al. "Context-aware deconvolution of cell–cell communication with Tensor-cell2cell." Nat. Commun. 13, 3665 (2022) [ref. 20]

---

## Flags
- [ ] Metadata unverified: Volume, issue and page numbers are not present in the cleaned text; only "Nature Cell Biology" (confirmed via peer-review line and Technical Report header) and year 2024 are confirmed. DOI, received/accepted/published dates confirmed in body (Received 15 March 2024; Accepted 2 July 2024; Published online 2 September 2024).
- [ ] Source transcription note: "spatially uniformed CCC methods" appears in the cleaned MD where the published wording is almost certainly "spatially uninformed"; quoted verbatim as it stands in the source.
- [ ] Read at source: ref. 3 (Dimitrov et al., Nat. Commun. 2022) — the benchmark/comparability and lack-of-ground-truth critique is most authoritative first-hand; ref. 39/40 (Nat. Rev. Genet. reviews) for the coverage–resolution trade-off; ref. 41 (Slide-tags, Nature 2024) for spatially preserving single-nucleus technology.
- [ ] Scope note: The paper's detailed biological case studies (dopamine/MSN/D2R signalling; FN1/SPP1/integrin fibrosis mechanisms; intracellular TF networks) are out-of-scope for our data-standard thesis and were deliberately NOT captured except where a high-level sentence doubles as a data-foundation concession.
- [ ] Claim 6 (high-throughput spatiotemporal proteomics) is not supported here — LIANA+ infers protein-mediated CCC from transcriptomics, it does not measure proteins; treat any proteomics framing as absent in this paper.
