# Grow AI Virtual Cells: Three Data Pillars and Closed-Loop Learning — Source Index

**Authors:** Liujia Qian, Zhen Dong, Tiannan Guo
**Journal / Venue:** Cell Research, 2025, 35:319–321 (Comment / Perspective)
**DOI:** doi:10.1038/s41422-025-01101-y
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/02 - Grow AI virtual cells - three data pillars and closed-loop learning_cleaned.md

---

## In One Sentence
A short Comment from the Guo lab proposing that AI Virtual Cells (AIVCs) should be "grown" on three data pillars — a priori knowledge, static (spatially resolved) architecture, and dynamic (perturbation) states — with perturbation proteomics as the critical growth factor, and argues for closed-loop active-learning systems (AI prediction + robotic experimentation) to generate the missing dynamic data, suggesting yeast as the first model.

## Orientation (non-binding)
This is the authoring group's own prior Comment and is almost certainly one of the perspective's anchor self-references. It supplies ready framing and ammunition for several roadmap claims at once: it foregrounds spatially resolved data (axis C), dynamic/perturbation states (axis B), multimodal profiling and the irreplaceable role of proteins (axis A / claims 4–6), AI-driven multimodal integration (claim 8), and it concedes concrete data gaps (matched perturbation omics + spatiotemporal imaging absent in early whole-cell models; perturbation proteomics "scarce"; datasets "lack systematic coverage of the parameter space"). It can also serve as a predecessor framing our perspective sharpens: its critique of single-cell data is pinned on state *similarity* rather than on the dissociation-driven loss of space/time that is our thesis's core, and it organizes around "three pillars" rather than our "spacetime × irreplaceable-multimodal × comparable/integrable standard." Routing hint only — the downstream agent decides whether to deploy it as support, as primary framing, or as a foil our argument refines.

---

## Load-Bearing Excerpts

> "cell-based experiments are resource intensive and prone to variability, contributing to the reproducibility concerns in biomedical research."
> — Intro (opening) · bears on: claim 9 (data islands / comparability), motivation · states that wet-lab cell experiments are variable and reproducibility-limited.

> "Pioneering whole-cell virtual models, such as those for Mycoplasma genitalium, Escherichia coli and Saccharomyces cerevisiae, were primarily based on a priori knowledge. However, they lack rigorously designed matched perturbation omics data and spatiotemporal imaging data."
> — Intro · bears on: claims 1, 2, 3, axis B, axis C · concedes that early whole-cell models lacked matched perturbation omics and spatiotemporal imaging data.

> "While groundbreaking, these early models are limited in their ability to fully capture the dynamic nature and complexity of living cells, underscoring the need for more comprehensive data integration and advanced modeling approaches."
> — Intro · bears on: claims 1, 3, 8 · states early models cannot capture cellular dynamics and complexity, needing more data integration.

> "Bunne et al. recently proposed the concept of Artificial Intelligence Virtual Cells (AIVCs), which integrate AI and multi-modal data to create comprehensive computational models of cellular functions."
> — Intro · bears on: claims 1, 8, axis A · defines AIVC as AI + multimodal data (ref 6).

> "the scientific community should collaborate to establish standards and best practices for AIVC development and validation."
> — Intro · bears on: claim 9, axis standard · calls for community standards and best practices for AIVC.

> "We propose here that the evolution or growth of AIVCs relies on three essential building blocks and nutrients: a priori knowledge, static architecture, and dynamic states."
> — THREE DATA PILLARS · bears on: claims 2, 3, 4, 8, axes A/B/C · states the paper's three-pillar data framework for AIVCs.

> "Despite its vast size and diversity, this knowledge base primarily consists of fragmented information across different cell types and populations. While it is unrealistic to build a fully functional AIVC for a specific cell type solely from these data, they encapsulate fundamental cell biological mechanisms essential for model construction."
> — THREE DATA PILLARS (a priori knowledge) · bears on: claims 1, 9 · concedes existing knowledge is fragmented across cell types and insufficient alone to build a specific AIVC.

> "We define this second essential pillar of AIVC construction as static architecture, which integrates nanoscale molecular structures and spatially resolved data from molecular modeling, cryo-electron microscopy, cryo-electron tomography, correlative light and electron microscopy, super-resolution fluorescence imaging, spatial omics, and other multi-scale analyses."
> — THREE DATA PILLARS (static architecture) · bears on: claims 2, 8, axis C · defines static architecture as spatially resolved, multi-scale structural/imaging data.

> "Additionally, tissue expansion techniques can further enhance spatial resolution, complementing the high-resolution imaging methods and omics technologies mentioned above. This integrated approach provides a detailed three-dimensional context essential for accurate AIVC modeling."
> — THREE DATA PILLARS · bears on: claim 2, axis C · states spatial resolution / 3D context is essential for accurate AIVC modeling (refs 7, 8).

> "While static data provide a bona fide snapshot of the cell, they fail to capture the dynamic nature of living systems. To construct a live AIVC, we introduce dynamic states as the third pillar for AIVC development."
> — THREE DATA PILLARS (dynamic states) · bears on: claim 3, axis B · states static snapshots cannot capture temporal dynamics, motivating a dynamic-states pillar.

> "These data encompass natural processes such as aging, development, and carcinogenesis, as well as induced perturbations including physical, chemical, and genetic interventions."
> — THREE DATA PILLARS · bears on: axis B, claim 7 · enumerates natural temporal processes and induced perturbations as dynamic-state data.

> "Cellular dynamics are historically studied by measuring the expression or activity of one or a few molecules at a time. With advancements in high-throughput omics technologies — such as transcriptomics, proteomics, and metabolomics — it is now possible to profile thousands of molecules across diverse cellular states."
> — THREE DATA PILLARS · bears on: axis A, claims 4, 5 · states high-throughput multi-omics now profiles thousands of molecules across states.

> "To build an effective AIVC, it is essential to comprehensively capture a wide range of cellular states and maximize their diversity to ensure high accuracy in differentiating them, requiring large volumes of dynamic, cell-specific data."
> — THREE DATA PILLARS · bears on: claim 1, axis B · states effective AIVCs require large volumes of diverse, cell-specific dynamic data.

> "Given the limited number of naturally occurring states, artificial perturbations serve as effective tools to generate different cellular states. Among these, perturbation proteomics is particularly valuable, as proteins are the primary structural components and catalysts of cellular biochemical processes."
> — THREE DATA PILLARS · bears on: claims 4, 5, 7, axis A · argues proteins are primary structural/catalytic components, making perturbation proteomics particularly valuable (ref 9).

> "A recent AIVC pilot study integrating perturbation proteomics and AI algorithms demonstrates accurate prediction of drug efficacy and synergistic combinations, highlighting the critical role of dynamic perturbation proteomics data in constructing robust virtual cell models for drug discovery and cellular simulation."
> — THREE DATA PILLARS · bears on: claims 5, 6, axis A · reports a perturbation-proteomics + AI pilot predicting drug efficacy and synergy (ref 10).

> "Although single-cell omics technologies have generated large datasets of millions of cells isolated from bulk tissues, their value for constructing AIVC is limited due to the similarity of the cells' states."
> — THREE DATA PILLARS · bears on: claims 1, 10, axis C · argues single-cell datasets, though large and dissociated from tissue, are of limited AIVC value because of state similarity.

> "mass spectrometry-based proteomics offers distinct advantages in analyzing thousands of proteins, protein post-translational modifications, and complex dynamics without the need for affinity-based reagents."
> — THREE DATA PILLARS · bears on: claims 4, 6, axis A (proteome / PTM / complexes) · states MS proteomics measures thousands of proteins, PTMs, and complex dynamics reagent-free (ref 12).

> "Antibody-based methods, such as those used in the Human Protein Atlas, are valuable, while mass spectrometry-based proteomics offers distinct advantages..."
> — THREE DATA PILLARS · bears on: claim 6, axis A · cites antibody-based proteomics (Human Protein Atlas) as valuable (ref 11).

> "emerging spatial omics technologies enable large-scale mapping of molecular distribution, providing insights into how perturbations alter cellular processes in their native spatial context. In particular, spatial proteomics represents the forefront of this advancement."
> — THREE DATA PILLARS · bears on: claims 2, 7, axis C · states spatial omics maps molecular distribution and reveals how perturbations act in native spatial context, with spatial proteomics at the forefront (refs 8, 13).

> "innovative sample preparation methods now allow simultaneous multi-omics analysis of the same sample."
> — THREE DATA PILLARS · bears on: claim 8, axis standard · states new prep methods enable paired multi-omics from the same sample (ref 14).

> "We argue that the AI-driven integration of static and dynamic data is essential for constructing a functionally robust and predictive AIVC."
> — THREE DATA PILLARS · bears on: claim 8, axis standard · asserts AI integration of static and dynamic data is essential for predictive AIVCs.

> "The integration of multimodal data from a priori knowledge, static architecture, and dynamic states demands sophisticated AI frameworks capable of hierarchical reasoning, cross-modal alignment, and predictive simulation."
> — THREE DATA PILLARS · bears on: claim 8, axis standard · states multimodal integration requires AI capable of cross-modal alignment.

> "AIVCs aim to infer molecular states across omics layers, forecast molecular states based on physiological inputs, and predict cellular outcomes following perturbations or in specific conditions based on baseline molecular states."
> — THREE DATA PILLARS · bears on: claims 4, 7, axis A · states AIVC goals include cross-omics-layer inference and perturbation-outcome prediction.

> "A critical challenge in modeling dynamic states is the combinatorial complexity of cellular responses to perturbations. While existing datasets capture snapshots of induced or natural states, they often lack systematic coverage of the parameter space."
> — CLOSED-LOOP ACTIVE LEARNING · bears on: claims 1, 10, axis B · concedes existing perturbation datasets are snapshots lacking systematic parameter-space coverage.

> "Our proposed closed-loop active learning systems could prioritize high-impact perturbations — such as CRISPR-based gene knockouts, small-molecule treatments, or optogenetic triggers — based on their potential to reduce model uncertainty or reveal novel regulatory mechanisms."
> — CLOSED-LOOP ACTIVE LEARNING · bears on: claim 7, axis B · proposes active-learning prioritization of high-impact perturbations to reduce model uncertainty.

> "an AIVC trained on baseline proteomic profiles might identify understudied phosphorylation events in stress response pathways, prompting robotic platforms to perform time-resolved phosphoproteomics under targeted metabolic perturbations."
> — CLOSED-LOOP ACTIVE LEARNING · bears on: axis A (PTM), axis B (time-resolved), claim 5 · example coupling baseline proteomics to time-resolved phosphoproteomics under perturbation.

> "While extensive experimental data exist for these cell types, significant gaps remain across the three pillars, particularly in their dynamic states. Notably, perturbation proteomics data, which are essential for building a comprehensive and dynamic AIVC, are scarce across all the candidate cell types."
> — LOW-HANGING FRUITS · bears on: claims 1, 6, axis A, axis B · concedes that perturbation proteomics data are scarce across all candidate cell types despite extensive other data.

> "Developing an AIVC for these simpler organisms can serve as a proof of concept, allowing us to address fundamental questions posed by Bunne et al.: What are the specific data needs and requirements for building an AIVC? How much data is necessary to construct a robust and predictive AIVC? How can we develop a comprehensive and adaptable benchmarking framework to evaluate AIVC performance?"
> — LOW-HANGING FRUITS · bears on: claims 1, 9 · frames open questions about AIVC data needs, data sufficiency, and benchmarking frameworks (ref 6).

> "Among these, perturbation-based omics data — transcriptomics, proteomics, and metabolomics — emerge as the critical growth factors."
> — CONCLUSION AND OUTLOOK · bears on: claims 4, 5, axis A · names perturbation transcriptomics/proteomics/metabolomics as the critical data for AIVC growth.

> "We envision Closed-Loop Active Learning Systems as the next evolutionary step. These systems, inspired by autonomous chemistry laboratories, will seamlessly integrate AI-driven predictions with robotic experimentation. Like a skilled gardener, they will identify knowledge gaps, design targeted experiments, and continuously refine our understanding of cellular complexities."
> — CONCLUSION AND OUTLOOK · bears on: claim 7, axis B, axis standard · describes closed-loop AI + robotics generating purpose-built perturbation data (ref 15).

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data is the bottleneck; models limited by input | "they lack rigorously designed matched perturbation omics…" / Intro; "lack systematic coverage of the parameter space" / Closed-Loop; "requiring large volumes of dynamic…" / Pillars | supports |
| Claim 2 — scRNA-seq loses spatial info; need spatial omics | "spatially resolved data from… spatial omics" / Pillars; "spatial proteomics represents the forefront" / Pillars; "detailed three-dimensional context essential" / Pillars | supports |
| Claim 3 — destructive sequencing can't pair-observe time | "static data… fail to capture the dynamic nature" / Pillars; "lack… spatiotemporal imaging data" / Intro | nuances (frames temporal gap via static-vs-dynamic, not via destructiveness) |
| Claim 4 — modalities orthogonal / mutually irreplaceable | "proteins are the primary structural components and catalysts" / Pillars; "infer molecular states across omics layers" / Pillars; "transcriptomics, proteomics, and metabolomics" / Conclusion | supports |
| Claim 5 — protein/metabolism modalities indispensable for function/phenotype | "perturbation proteomics is particularly valuable…" / Pillars; "accurate prediction of drug efficacy and synergistic combinations" / Pillars | supports |
| Claim 6 — high-throughput (spatio)temporal proteomics is feasible | "mass spectrometry-based proteomics offers distinct advantages…" / Pillars; "spatial proteomics represents the forefront" / Pillars; "perturbation proteomics data… are scarce" / Low-Hanging Fruits | supports (and concedes scarcity) |
| Claim 7 — spatial microenvironment alters cell state / perturbation response | "how perturbations alter cellular processes in their native spatial context" / Pillars; "prioritize high-impact perturbations" / Closed-Loop | supports |
| Claim 8 — multimodal data give orthogonal info; need integration | "simultaneous multi-omics analysis of the same sample" / Pillars; "AI-driven integration of static and dynamic data is essential" / Pillars; "cross-modal alignment" / Pillars | supports |
| Claim 9 — data islands / cross-paper incomparability / no standard | "fragmented information across different cell types" / Pillars; "establish standards and best practices" / Intro; "adaptable benchmarking framework" / Low-Hanging Fruits | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "single-cell omics… value… limited due to the similarity of the cells' states" / Pillars; "lack systematic coverage of the parameter space" / Closed-Loop | nuances (limits single-cell data, but via state similarity, not the trilemma framing) |
| Axis A — modality (measure what) | "transcriptomics, proteomics, and metabolomics" / Pillars + Conclusion; "post-translational modifications, and complex dynamics" / Pillars | supports |
| Axis B — temporal (time course / trajectory) | "aging, development, and carcinogenesis… induced perturbations" / Pillars; "time-resolved phosphoproteomics" / Closed-Loop | supports |
| Axis C — spatial (subcellular → tissue) | "nanoscale molecular structures and spatially resolved data" / Pillars; "native spatial context" / Pillars | supports |
| Axis standard — QC / comparability / integration / reference frame | "establish standards and best practices" / Intro; "simultaneous multi-omics… same sample" / Pillars; "adaptable benchmarking framework" / Low-Hanging Fruits | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Schematic of the three pillars for growing AIVCs (a priori knowledge, static architecture, dynamic states) integrated by AI algorithms, with example model organisms (E. coli, yeast, cell lines), and the closed-loop active-learning evolution where computational predictions guide automated perturbation-omics experimentation. |

*(No data tables in the paper. No standalone quantitative measurements reported; numeric content is limited to citation metadata and the three-pillar count.)*

---

## Primary Sources Behind Key Quotes
- AIVC concept / open data-need questions → Bunne, C. et al., Cell 187:7045–7063 (2024), ref 6.
- Perturbation proteomics + AI pilot predicting drug efficacy/synergy → Sun, R. et al., bioRxiv https://doi.org/10.1101/2025.02.07.637070 (2025), ref 10.
- Proteins as primary structural components and catalysts → Qian, L. et al., Cell Genomics 4:100691 (2024), ref 9.
- MS-based proteomics advantages (proteins, PTMs, complexes) → Guo, T., Steen, J. A. & Mann, M., Nature 638:901–911 (2025), ref 12.
- Antibody-based proteomics / Human Protein Atlas → Sjöstedt, E. et al., Science 367:eaay5947 (2020), ref 11.
- Spatial proteomics at the forefront → Dong, Z. et al., Nat. Commun. 15:9378 (2024), ref 8; Nordmann, T. M., Mund, A. & Mann, M., Nat. Methods 21:2220–2222 (2024), ref 13.
- Simultaneous multi-omics from the same sample → Li, W. et al., Anal. Chem. 97:1190–1198 (2025), ref 14.
- Tissue expansion enhancing spatial resolution → Wang, S. et al., Nat. Methods 21:2128–2134 (2024), ref 7; Dong, Z. et al., Nat. Commun. 15:9378 (2024), ref 8.
- Closed-loop / autonomous-chemistry-lab inspiration → Dai, T. et al., Nature 635:890–897 (2024), ref 15.
- Early whole-cell models → Karr, J. R. et al., Cell 150:389–401 (2012), ref 2; Macklin, D. N. et al., Science 369:eaav3751 (2020), ref 3; Ye, C. et al., Biotechnol. Bioeng. 117:1562–1574 (2020), ref 4; Österlund, T. et al., BMC Syst. Biol. 7:36 (2013), ref 5.

---

## Flags
- [ ] Metadata unverified: received/accepted dates not present in the source text; only publication year/volume/pages confirmed ("Cell Research (2025) 35:319–321"). Article type ("Comment / Perspective") inferred from venue and format, not stated verbatim.
- [ ] Source inconsistency: the Human Protein Atlas sentence carries an inline citation rendered as superscript "1" in the cleaned text, but the matching reference is #11 (Sjöstedt et al., Science 367:eaay5947, 2020) — treated as an OCR/cleaning digit-truncation, not a real ref to #1.
- [ ] Source inconsistency: trailing citation markers for perturbation proteomics ("…cellular simulation. 10") and closed-loop ("…discovery and understanding. 15") appear as floating numbers in the cleaned text; mapped to refs 10 and 15 respectively by context.
- [ ] Verbatim normalization: the cleaned source contains OCR ligature artifacts (`<sup>fi</sup>`, `<sup>fl</sup>`, `<sup>fl</sup>uorescence`, etc.); quotes above restore the intended words (e.g., "first", "specific", "fluorescence", "refine") without other alteration.
- [ ] Authorship note: corresponding author Tiannan Guo (guotiannan@westlake.edu.cn), Westlake University — this is the authoring group's own Comment, i.e. a self-reference / companion piece to the perspective being written, not a third-party source.
- [ ] Read at source: Bunne et al. 2024 (ref 6, AIVC definition + open questions) and Sun et al. 2025 bioRxiv (ref 10, perturbation-proteomics AIVC pilot) are worth reading first-hand rather than via this Comment; Guo, Steen & Mann 2025 (ref 12) for the proteomics-advantage claim.
