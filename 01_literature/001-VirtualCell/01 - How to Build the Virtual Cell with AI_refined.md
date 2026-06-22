# How to Build the Virtual Cell with Artificial Intelligence: Priorities and Opportunities — Source Index

**Authors:** Charlotte Bunne*, Yusuf Roohani*, Yanay Rosen*, Ankit Gupta, Xikun Zhang, Marcel Roed, Theo Alexandrov, Mohammed AlQuraishi, Patricia Brennan, Daniel B. Burkhardt, Andrea Califano, Jonah Cool, Abby F. Dernburg, Kirsty Ewing, Emily B. Fox, Matthias Haury, Amy E. Herr, Eric Horvitz, Patrick D. Hsu, Viren Jain, Gregory R. Johnson, Thomas Kalil, David R. Kelley, Shana O. Kelley, Anna Kreshuk, Tim Mitchison, Stephani Otte, Jay Shendure, Nicholas J. Sofroniew, Fabian Theis, Christina V. Theodoris, Srigokul Upadhyayula, Marc Valer, Bo Wang, Eric Xing, Serena Yeung-Levy, Marinka Zitnik, Theofanis Karaletsos‡, Aviv Regev‡, Emma Lundberg‡, Jure Leskovec‡, Stephen R. Quake‡
(* equal contribution; ‡ corresponding authors)
**Journal / Venue:** unverified — not stated in source text; see Flags
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/01 - How to Build the Virtual Cell with AI_cleaned.md  (raw is on disk; the section names below are jump-back anchors — the cleaned MD carries no page numbers)

---

## In One Sentence
A community Perspective (catalyzed by a Chan Zuckerberg Initiative workshop) that proposes the "AI Virtual Cell" (AIVC): a multi-scale, multi-modal neural-network framework built from Universal Representations (URs) of molecules/cells/tissues plus Virtual Instruments (decoders and manipulators), and lays out the data, evaluation, interpretability, and open-collaboration requirements needed to build it.

## Orientation (non-binding)
This is the canonical vision paper for the very AIVC paradigm our Perspective scrutinizes — it is simultaneously a foil and a corroborating witness. It repeatedly concedes, in its own "Data needs" framing, the exact gaps our thesis builds on: that the cellular representation "will initially rely on transcriptomics" (modality narrowness), that spatial data are "still limited," that data generation must add temporal + spatial scales it does not yet have, and that dynamics are modeled as transitions between *distributions* of representations (the destructive-measurement / non-paired-observation issue). It most likely feeds Claims 1, 2, 3, 4, 8, 9, 10 and all three axes (modality / temporal / spatial) plus the cross-cutting "standard" axis. Routing-key legend below uses the context file's own identifiers: **Claim 1–10** = the evidence-roadmap list in context §5; **Axis A** = modality, **Axis B** = temporal, **Axis C** = spatial, **Standard** = QC / comparability / integration (context §4).

---

## Load-Bearing Excerpts

> "an ambitious vision of an AI Virtual Cell (AIVC), a multi-scale, multi-modal, large neural network-based model that can represent and simulate the behavior of molecules, cells and tissues across diverse states"
> — Main · bears on: thesis framing, Axis A/B/C · the paper's own definition of the AIVC as multi-scale and multi-modal.

> "Cells operate on multiple scales across both time and space, from atomic to molecular to cellu[…]lar and histological, with functional properties emerging through nonlinear transformation from one scale to another."
> — Main (list of shortcomings of prior models) · bears on: Axis B, Axis C · states that cells span time and space across scales (source OCR interleaves figure text here; bracketed gap marks the interruption).

> "approaches to date fall short of capturing many aspects of the operations of both bacteria and more complex systems, such as human cells"
> — Main · bears on: Claim 1 · concedes that pre-existing (rule-based) cell models are inadequate.

> "the exponential increase in the throughput of measurement technologies has led to the collection of large and growing reference datasets within and across diferent cell and tissue systems, with data doubling every six months for the past several years, along with the ability to couple these measurements with systematic perturbations"
> — Main · bears on: Claim 1, Axis A · quantitative claim about data growth and perturbation coupling.

> "Virtual cells must work across biological scales, over time, and across data modalities, and should help reveal the programming language of cellular systems"
> — AI Virtual Cells · bears on: Axis A/B/C · states the AIVC must span scales, time, and modalities.

> "Create a universal representation of biological states across species, modalities, datasets and contexts, including cell types, developmental stages and external conditions"
> — AI Virtual Cells · bears on: Axis A, Standard · the aspiration to represent across modalities/datasets/contexts.

> "By training on a wide range of snapshots, time-resolved, non-interventional and interventional datasets collected across contexts and scales, the AIVC can develop an understanding of the molecular, cellular, and tissue dynamics that occur under natural or engineered signals."
> — Predicting cell behavior and understanding mechanisms · bears on: Claim 3, Axis B · distinguishes "snapshots" from "time-resolved" datasets as inputs to dynamics.

> "The AIVC should also have the capability to simulate the temporal evolution of alterations in cell states in response to both intrinsic or extrinsic factors, along with the resulting multicellular spatial arrangements."
> — Predicting cell behavior and understanding mechanisms · bears on: Axis B, Axis C · the desired joint temporal + spatial capability.

> "By altering universal representations of molecules, cells and tissues, Manipulators can abstract complex dynamic processes more simply as transitions between (distributions of) their representations."
> — Predicting cell behavior and understanding mechanism (Virtual Instruments) · bears on: Claim 3, Axis B · dynamics modeled as transitions between distributions of representations.

> "a starting point for the AIVC will be to model the three types of molecules of the central dogma: DNA, RNA and proteins. These can all be represented as sequences of characters; nucleotides or amino acids"
> — Building universal representation across physical scales / Molecular scale · bears on: Axis A · names the initial molecular modalities (central-dogma sequences).

> "While language modeling approaches have been extensively studied for these core molecules and have proven successful for some of their chemical modifications and various other molecules such as glycans, lipids and metabolites, they may struggle with other molecular constituents of the cell."
> — Molecular scale · bears on: Claim 4, Axis A · acknowledges that non-sequence molecular constituents (e.g., metabolites, lipids, glycans) are harder to model.

> "Data for the cellular UR consist of measurements mapped to a single cell level such as measurements of the transcriptome (scRNA-seq), chromatin accessibility (scATAC-seq), chromatin modification transcription factor binding, and proteome."
> — Cellular scale · bears on: Axis A · enumerates the single-cell modalities feeding the cellular representation.

> "fluorescence confocal microscopy can help resolve the subcellular location of the human proteome. Live-cell imaging enables the study of proteins in living cells using time-lapse microscopy."
> — Cellular scale · bears on: Claim 6, Axis A, Axis B, Axis C · spatial (subcellular) and temporal protein measurement via imaging.

> "Complementing imaging approaches, mass spectrometry and proximity-dependent labeling can unveil proteinprotein associations and provide deeper insights into cell structure and signaling network rewiring."
> — Cellular scale · bears on: Claim 5, Claim 6, Axis A · proteomics / interactome measurement of structure and signaling.

> "it is crucial to also model cellular organelles and membraneless compartments as units that play specific roles within the cell. Robustly capturing the functions of these units is vital to ensure accurate predictions, mechanistic interpretability and model generalizability."
> — Cellular scale · bears on: Axis C · subcellular spatial organization matters for accurate prediction.

> "Given their prevalence, the cellular UR will initially rely on transcriptomics measurements, while imaging modalities will be key for continued modeling of cellular spatial organization and dynamics."
> — Cellular scale · bears on: Claim 4, Axis A, Axis C · concedes that the cellular representation will initially depend on transcriptomics, with spatial organization left to imaging.

> "Multicellular interactions can be analyzed after tissue dissociation (such as in scRNA-seq) or in situ in a 2D section or 3D volume, where the tissue structure is preserved."
> — Multicellular scale · bears on: Claim 2, Axis C · contrasts dissociation (scRNA-seq) against in situ measurement that preserves tissue structure.

> "Building the AIVC will require integration across available modalities that provide spatial insights, i.e., both spatial molecular profiling as well as non-molecular tissue imaging data."
> — Multicellular scale · bears on: Claim 8, Axis C, Standard · spatial insight requires integrating spatial molecular profiling and tissue imaging.

> "This layer allows for the exploration of how cell-cell interactions, largely governed by spatial proximity, combine into tissues, organs and, ultimately, whole organisms."
> — Multicellular scale · bears on: Claim 7, Axis C · cell–cell interactions are largely governed by spatial proximity.

> "Spatial molecular biology is currently a very active area of research and method development. While publicly available data are still limited, we foresee a rapid development in this domain providing multi-omic 2D and 3D datasets."
> — Multicellular scale · bears on: Claim 2, Axis C · concedes that publicly available spatial data are still limited.

> "A more generalized data generation efort together with open frameworks for spatial data could greatly accelerate modeling at the multicellular scale."
> — Multicellular scale · bears on: Claim 9, Axis C, Standard · calls for generalized data generation and open frameworks for spatial data.

> "A key consideration for the AIVC is which datasets and modalities must be collected to enable its efective construction. Unlike traditional experimental design, where data are generated to test specific scientific hypotheses, data collection for training the AIVC should be focused on ensuring the broad applicability and generalizability expected of the AIVC."
> — Data needs and requirements · bears on: Claim 1, Standard · frames data/modality selection as the key constraint.

> "data would ideally span diferent domains and modalities, capture the heterogeneity and diversity of biological variability, and enable models to distinguish between technical (measurement) noise, stochastic biological variation and physiological diferences."
> — Data needs and requirements · bears on: Claim 1, Claim 8, Standard · the breadth and quality requirements on training data.

> "Data generation will require simultaneous exploration of temporal and physical scales, while allowing for system perturbations."
> — Data needs and requirements · bears on: Axis B, Axis C, Claim 10 · data must jointly cover temporal and physical (spatial) scales plus perturbations.

> "biological processes span a vast range of timescales, from the fastest reactions happening in picoseconds, to a cell division happening in a day, tumor development occurring over years, and neurodegeneration over decades."
> — Data needs and requirements · bears on: Axis B · quantitative span of biological timescales.

> "New approaches will be needed to build comparable data sets which capture the behavior of cells on shorter times scales, e.g., through methods such as live-cell imaging."
> — Data needs and requirements · bears on: Claim 3, Axis B, Standard · concedes that comparable, short-timescale (live) datasets do not yet exist.

> "datasets which bridge molecular and spatial scales, such as single cell transcriptomics data combined with histology to understand how cells interact and what molecular signatures underpin the formation of specialized spatial niches"
> — Data needs and requirements · bears on: Claim 7, Claim 8, Axis C · multi-modal datasets bridging molecular and spatial scales are a key driver.

> "Further technological development is needed to collect multi-modal data that better captures the relationship between molecular signatures, cell behavior, cellular regulation and organization."
> — Data needs and requirements · bears on: Claim 8 · concedes current multi-modal data are insufficient.

> "human datasets are limited in our ability to perform controlled experimentation and perturbations in vivo. Here, the field of 3D tissue biology, including culture systems such as organoids, is emerging as a tool to study the complexities of tissue architecture and function in a 3D environment while allowing perturbations of the system."
> — Data needs and requirements · bears on: Claim 10 · in vivo human experimentation is limited; organoids offered as a 3D, perturbable alternative.

> "biological spaces are commonly high dimensional, and enumerating their variants is intractable in general… As combinatorial possibilities quickly expand well beyond what is practical experimentally, or even computationally, new methods for their exploration must be developed."
> — Data needs and requirements · bears on: Claim 10 · the combinatorial perturbation space is experimentally and computationally intractable.

> "the Short Read Archive of biological sequence data holds over 14 petabytes of information which is more than one thousand times larger than the dataset used to train ChatGPT."
> — Data needs and requirements · bears on: Claim 1, Claim 4 · quantitative; note the abundance cited is *sequence* data.

> "Large parts of this data may be redundant, or have diminishing returns if used for training, and the scaling laws for models' performances must be investigated thoroughly."
> — Data needs and requirements · bears on: Claim 1 · concedes that more raw data may have diminishing returns; scaling laws unverified.

> "Data from humans and model organisms like mice and E. coli are unequally represented in sequence and literature databases, which when used for training, encode strong species biases."
> — Data needs and requirements · bears on: Claim 1, Standard · training data carry strong species (and disease/ancestry) biases.

> "A more important question for the development of AI Virtual Cells may not be 'How to build them?', but rather 'How to build trust in their competence and fidelity?' To this end, a comprehensive and adaptable benchmarking framework will be needed."
> — Model evaluation · bears on: Claim 9, Standard · benchmarking/trust is framed as the more important open problem.

> "the AIVC will need to demonstrate generalizability across numerous biological contexts and downstream tasks. It must account for dynamic distributions that evolve due to environmental changes, infections, genetic variants and other such factors causing distribution shifts."
> — Model evaluation · bears on: Claim 1 · generalization across contexts and distribution shifts is a core requirement.

> "Establishing such cross-modal benchmarks to link scales and modalities in cell biology is of imminent priority to the research community, as these tasks are both biologically useful and well-defined."
> — Model evaluation · bears on: Claim 8, Claim 9, Standard · cross-modal benchmarks to link scales/modalities are an imminent priority.

> "When creating virtual cells, we may have to forgo our ability to build fully mechanistic models, in favor of learning interactions that will generalize from data and predict beyond the observations."
> — Interpretability and interaction · bears on: Claim 1 · acknowledges a shift from mechanistic to data-driven, generalize-from-data modeling.

> "These eforts would greatly benefit from open data resources and data standards, a collaborative platform for cell modeling, and especially open benchmark datasets and common validation strategies to ensure their biological fidelity and real-world utility."
> — An open collaborative approach · bears on: Claim 9, Standard · calls for open data standards, benchmarks, and common validation.

> "Model predictions should also be agnostic to their input and output modalities. The same entity, profiled with diferent technologies, should have the same internal representation in an AIVC."
> — Box 1 (Establishing self-consistency across varying contexts) · bears on: Claim 9, Claim 8, Standard · modality-invariance / cross-platform comparability requirement.

> "A fundamental question for the collaborative development of AIVCs is which data and modalities should be collected to enable generalization across biological contexts and scales… A key aspect of data generation will be the simultaneous measurement of temporal and physical scales, while also allowing perturbations of the system."
> — Box 1 (Understanding the value of diferent data types) · bears on: Claim 1, Axis B, Axis C · reiterates that which-data/which-modality is fundamental and that temporal + physical scales must be measured simultaneously.

> "For every capability, proper metrics must be designed and comprehensive evaluation data be collected."
> — Box 1 (Outlining capabilities and designing evaluation frameworks) · bears on: Claim 9, Standard · evaluation data and metrics must be purpose-built per capability.

> "Spatial structures in cancer, specifically within the tumor microenvironment (TME) are critical drivers of cancer progression, and can drive resistance to the immune system and limit drug eficacy."
> — Unlocking the power of spatial biology to fight cancer · bears on: Claim 7, Axis C · spatial tumor-microenvironment structure drives progression and resistance.

> "immune resistance must be understood in the spatial context of the cellular neighborhood in order to identify the specific cell states and gene signatures involved."
> — Unlocking the power of spatial biology to fight cancer · bears on: Claim 7, Axis C · cell state must be read in its spatial-neighborhood context.

> "While the AIVC would already accurately qualify the change in the expression of genes, tumor sequencing data would allow it to model the change of function of those genes, for example through loss of function, change in post-translational modifications, or rewiring of protein-protein interactions and signaling networks."
> — Unlocking the power of spatial biology to fight cancer · bears on: Claim 4, Claim 5, Axis A · concedes that gene expression alone does not capture functional change, which lives at the PTM / protein-protein-interaction / signaling layer.

> "approaches such as flow matching methods can also model the distributional evolution over time… making them especially powerful in biological applications where dynamic changes and temporal progression are critical."
> — Box 3 (Difusion models) · bears on: Claim 3, Axis B · temporal progression is modeled as the distributional evolution of states over time.

---

## Claim Touchpoints (router — keyed to context file §5 claims and §4 axes)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 (data is the bottleneck; data-driven generalization) | "diminishing returns… scaling laws must be investigated" / Data needs; "demonstrate generalizability… distribution shifts" / Model evaluation; "forgo… fully mechanistic models" / Interpretability | supports |
| Claim 2 (scRNA-seq loses spatial info) | "after tissue dissociation (such as in scRNA-seq) or in situ… where the tissue structure is preserved" / Multicellular scale; "publicly available data are still limited" / Multicellular scale | supports |
| Claim 3 (destructive seq → no paired temporal observation) | "transitions between (distributions of) their representations" / VIs; "snapshots, time-resolved…" / Predicting behavior; "comparable data sets… shorter times scales" / Data needs | nuances |
| Claim 4 (modalities non-substitutable; RNA over-relied) | "cellular UR will initially rely on transcriptomics" / Cellular scale; "change of function… post-translational modifications… protein-protein interactions" / Spatial-cancer; "may struggle with other molecular constituents" / Molecular scale | supports |
| Claim 5 (protein/metabolism etc. indispensable for function) | "change of function… PTMs… signaling networks" / Spatial-cancer; "mass spectrometry and proximity-dependent labeling… signaling network rewiring" / Cellular scale | supports |
| Claim 6 (high-throughput spatiotemporal proteomics feasible) | "fluorescence confocal microscopy… subcellular location of the human proteome" + "Live-cell imaging… time-lapse" / Cellular scale | supports |
| Claim 7 (spatial organization/microenvironment changes state & response) | "spatial structures in cancer… TME… critical drivers" + "spatial context of the cellular neighborhood" / Spatial-cancer; "cell-cell interactions, largely governed by spatial proximity" / Multicellular scale | supports |
| Claim 8 (multi-modal orthogonal info; needs integration) | "datasets which bridge molecular and spatial scales… histology" / Data needs; "Further technological development is needed to collect multi-modal data" / Data needs; "cross-modal benchmarks… imminent priority" / Model evaluation | supports |
| Claim 9 (data silos / cross-paper incomparability / no standards) | "open data resources and data standards… common validation strategies" / Open collaborative; "same entity, profiled with diferent technologies, should have the same internal representation" / Box 1; "build trust in their competence and fidelity… benchmarking framework" / Model evaluation | supports |
| Claim 10 (resolution × throughput × destructiveness trilemma) | "simultaneous exploration of temporal and physical scales… perturbations" / Data needs; "human datasets are limited… in vivo… organoids" / Data needs; "combinatorial possibilities… intractable" / Data needs | supports |
| Axis A (modality / measure what) | central dogma "DNA, RNA and proteins" / Molecular scale; cellular-UR modality list / Cellular scale | — |
| Axis B (temporal) | "vast range of timescales… picoseconds… decades" / Data needs; "distributional evolution over time" / Box 3 | — |
| Axis C (spatial) | "in situ… tissue structure is preserved" / Multicellular scale; "organelles and membraneless compartments" / Cellular scale | — |
| Standard (QC / comparability / integration) | "open data resources and data standards" / Open collaborative; "modality-agnostic… same internal representation" / Box 1 | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Quant: data growth | "data doubling every six months for the past several years" (Main). |
| Quant: data scale | Short Read Archive "over 14 petabytes," stated as ">1,000× larger than the dataset used to train ChatGPT" (Data needs). |
| Quant: timescales | Biological processes from "picoseconds" → cell division "in a day" → tumor development "over years" → neurodegeneration "over decades" (Data needs). |
| Fig. 1 | Capabilities of the AIVC: Universal Representation across species/conditions/modalities/scales; generalization to unobserved states; modality-invariant reference; dynamics across state transitions; in silico experimentation; human-interaction layers (Figure Descriptions). |
| Fig. 2 | Architecture overview: URs at molecular / cellular / multicellular scales, each integrating the prior scale; Virtual Instruments (Manipulators simulate state changes; Decoders read out phenotypes) (Figure Descriptions). |
| Box 1 | Five grand challenges: define+evaluate capabilities; self-consistency across scales/contexts/modalities; interpretability vs utility; collaborative framework; value-of-data-types for prioritizing data generation. |
| Box 3 | AI architectures for the AIVC: transformers, CNNs, diffusion (+ flow matching), graph neural networks — mostly off-roadmap method detail; only data-bearing clauses captured above. |

---

## Primary Sources Behind Key Quotes
- Spatiotemporal single-cell proteomics (subcellular proteome over the cell cycle) → Mahdessian, D. et al. Nature 590 (2021), ref #75.
- Subcellular map of the human proteome (confocal imaging) → Thul, P. J. et al. Science 356 (2017), ref #79 (also #126).
- Spatial proteomics as a discovery tool → Lundberg, E. & Borner, G. H. H. Nature Reviews Molecular Cell Biology 20:285–302 (2019), ref #106.
- Spatial transcriptomics (in-tissue gene expression) → Ståhl, P. L. et al. Science 353 (2016), ref #105.
- Multi-scale map of cell structure fusing protein images and interactions → Qin, Y. et al. Nature 600 (2021), ref #87.
- Emerging landscape of spatial profiling technologies → Mofitt, J. R., Lundberg, E. & Heyn, H. Nature Reviews Genetics 23:741–759 (2022), ref #131.
- Methods/applications for single-cell and spatial multi-omics → Vandereyken, K. et al. Nature Reviews Genetics 24:494–515 (2023), ref #132.
- Single-cell time-lapse of mouse prenatal development (temporal/trajectory) → Qiu, C. et al. Nature (2024), ref #114.
- scRNA-seq via droplet barcoding (dissociation paradigm) → Macosko, E. Z. et al. Cell 161 (2015), ref #104.
- Spatial gene expression + tumour morphology via deep learning (niches) → He, B. et al. Nature Biomedical Engineering 4:827–834 (2020), ref #135.
- Number of human proteoforms (modality complexity beyond RNA) → Aebersold, R. et al. Nature Chemical Biology 14 (2018), ref #171.
- First whole-cell model (M. genitalium) → Karr, J. R. et al. Cell 150 (2012), ref #9.

---

## Flags
- [ ] Metadata unverified: Journal/Venue, DOI, and received/accepted/published dates are NOT present anywhere in the cleaned source text (`grep` for `10.xxxx/` DOI pattern and for received/accepted/published/doi returned nothing). Header marks them "unverified." Reference years extend to 2024, suggesting a 2024 vintage, but this is inference, not stated in the text.
- [ ] No page numbers: the cleaned MD has no pagination; excerpt anchors are section names only (`(approx. p.X)` not available).
- [ ] Source OCR artifacts: the cleaned text contains systematic missing-letter typos from OCR (e.g., "diferent," "efective," "eficient," "afect"); quotes are reproduced verbatim including these artifacts so they remain searchable against the raw. The Main-section paragraph on multi-scale modeling has figure text interleaved into the prose (bracketed gap in that excerpt).
- [ ] Read at source: for first-hand citation prefer the primary papers listed above — especially Mahdessian 2021 (#75) and Lundberg & Borner 2019 (#106) for spatiotemporal/spatial proteomics, Ståhl 2016 (#105) for spatial transcriptomics, and Karr 2012 (#9) for the whole-cell-model precedent — rather than citing them through this Perspective.
- [ ] Scope note: Box 3 architecture descriptions (transformer/CNN/diffusion/GNN internals) and most "Virtual Instruments" mechanics are out-of-scope per context §6 ("do not write modeling methods") and were deliberately NOT captured, except clauses that bear on data needs (e.g., distributional temporal modeling, spatial graphs).
