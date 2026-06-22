# From modality-specific to compositional foundation models for cell biology — Source Index

**Authors:** Not printed in the cleaned source body; only initials appear in Acknowledgments — M.B., T.R., N.A.S., F.J.T. (see Flags)
**Journal / Venue:** Cell Systems (Perspective) — running header reads "Cell Systems Perspective"; year unverified (references extend to 2025) — see Flags
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/03 - From modality-specific to compositional foundation models for cell biology_cleaned.md

---

## In One Sentence
A perspective arguing that multimodal single-cell foundation models should be built by *compositional AI* — modularly assembling independently pre-trained, modality-specific expert models and aligning them through transformer attention — rather than as monolithic models, because paired multimodal measurements are rare relative to abundant unimodal data; it reviews attention building blocks, architectural designs (cross-encoder / bi-encoder / language encoding), early models (Table 2), integration of prior knowledge, multiscale modeling, and evaluation, charting a path toward "agentic virtual cell" models.

## Orientation (non-binding)
This paper sits on the *modeling/architecture* side of the virtual-cell conversation and is largely a methodological counterpart to our data-first thesis — making it useful as a **named "model/architecture-focused" foil**. But it repeatedly **concedes the very data-foundation facts we build on**: that biological modalities encode *complementary* (non-substitutable) information, that no single technology captures all modalities, that paired multimodal data are scarce, that samples cover only "a tiny fraction" of cellular states, and that "Observation" (modality diversity) is co-equal with modeling and scale. It therefore most likely feeds Axis A (modality / non-substitutability — claims 4, 8), Axis C (spatial — claims 2, 7), the standard/integration axis (claims 9, 1), and supplies measurement-cost/trade-off material (claim 10). It is lighter on the destructive-measurement-→-no-time-pairing argument (claim 3), which it does not frame as a hard constraint.

---

## Load-Bearing Excerpts

> "Unlike vision and language, biological modalities are fragmented and may encode useful complementary information, and no single technology currently captures all these distinct aspects simultaneously."
> — MULTI-MODALITY AND COMPOSITIONAL AI / p. (approx.) · bears on: claim 4 (modalities orthogonal/irreplaceable), claim 8 (need integration), Axis A · the paper states modalities carry complementary information and no single assay captures all of them.

> "By contrast, biological modalities often encode complementary information, while paired multimodal measurements are rare compared with unimodal data. In addition, cross-modal pairing is often imperfect due to technical effects or biological heterogeneity."
> — Challenges in modeling across modalities · bears on: claim 4, claim 8, claim 10 (pairing scarcity/cost), Axis A/standard · contrasts biological modalities (complementary) with redundant vision-language modalities.

> "While effective for retrieval or matching tasks, such objectives are poorly suited for settings in which modalities must be integrated to recover information absent from any single view. From a methodological perspective, this suggests a need to move beyond alignment-centric interfaces toward integration mechanisms that explicitly model how complementary biological signals interact under limited and noisy pairing."
> — Challenges in modeling across modalities · bears on: claim 4 (information absent from any single view), claim 8 · argues contrastive/alignment objectives (InfoNCE) cannot recover information that exists in no single modality.

> "In vision-language models, modalities are typically designed to be redundant, and large, high-quality paired datasets enable joint optimization of modality-specific encoders using alignment-based objectives. By contrast, biological modalities often encode complementary information…"
> — Challenges in modeling across modalities · bears on: claim 4, claim 8 · sets up the redundant (vision-language) vs. complementary (biology) distinction.

> "Functionally, interpretable integration seeks to uncover causal and mechanistic relationships across modalities, enabling the identification of regulatory programs, signaling pathways, and cell-cell communication processes that are not observable from any single modality alone."
> — INTRODUCTION · bears on: claim 4, claim 7 (cell-cell communication), claim 8 · states key biological processes are not observable from any single modality.

> "Each of these measurement modalities provides a unique perspective on cellular function and regulation, and together they offer a more comprehensive view of cellular states and processes than individual measurements."
> — MULTI-MODALITY AND COMPOSITIONAL AI · bears on: claim 4, claim 8, Axis A · each modality is a unique perspective; combined view exceeds individual measurements.

> "Cells contain diverse molecular entities such as genetic material, transcripts, proteins, and metabolites that interact to carry out biological functions."
> — MULTI-MODALITY AND COMPOSITIONAL AI · bears on: claim 4, claim 5 (protein/metabolite functional layers), Axis A · enumerates the molecular modalities (incl. proteins, metabolites) underlying function.

> "Observation: the number and type of modalities included in the training data. Without diverse observations, even the most effective models and largest datasets will fall short of capturing the true complexity of the underlying biology."
> — MULTI-MODALITY AND COMPOSITIONAL AI (Figure 1A directions) · bears on: claim 1 (data/observation is the bottleneck, not model), claim 4, Axis A · names "Observation" (modality diversity) as a third pillar alongside Modeling and Scale; models and scale alone fall short.

> "The overall progress in multimodal single-cell foundation models will depend on jointly advancing modeling strategies, scaling principles, and the diversity of observed modalities to ensure that increased capacity translates into deeper and more faithful representations of cellular biology."
> — MULTI-MODALITY AND COMPOSITIONAL AI · bears on: claim 1, claim 4 · progress requires data-modality diversity, not just bigger models.

> "By contrast, recent large-scale single-cell studies only capture a tiny fraction of possible cellular states and conditions given the complexity of biological systems. This scarcity of samples, combined with the high dimensionality and heterogeneity of biological data, makes it challenging to learn robust representations that generalize across different biological contexts and experimental conditions while enabling the inference of biological mechanisms."
> — Challenges in modeling across modalities · bears on: claim 1 (generalization limited by data), claim 10 · concedes current data cover only a tiny fraction of cellular states; generalization is data-limited.

> "Furthermore, the scarcity of biological samples relative to the immense complexity and dimensionality of cellular systems makes it challenging for monolithic architectures to learn robust, generalized representations without the modular flexibility offered by a compositional approach."
> — MULTI-MODALITY AND COMPOSITIONAL AI · bears on: claim 1, claim 10 · sample scarcity vs. system complexity undermines robust/generalized representations.

> "While single-cell transcriptomics has been a primary driver of this endeavor thanks to substantial efforts in collecting, organizing, and maintaining a wealth of publicly available datasets."
> — INTRODUCTION · bears on: claim 1, Axis A (RNA over-relied-upon) · concedes transcriptomics has been the primary driver because of data availability.

> "However, in cell biology, training a unified non-compositional model is significantly more difficult because paired multimodal measurements are rare relative to the vast amount of available unimodal data."
> — MULTI-MODALITY AND COMPOSITIONAL AI · bears on: claim 8, claim 9 (fragmentation), claim 10 · paired multimodal data are rare vs. abundant unimodal data.

> "Single-cell proteomics quantifies protein levels and modifications, offering a functional perspective on cellular states."
> — Multi-modal measurements · bears on: claim 5 (protein as functional layer), Axis A · proteomics gives a functional view incl. PTMs.

> "Imaging techniques offer spatial and temporal context, capturing subcellular structures and live dynamics."
> — Multi-modal measurements · bears on: claim 3 (temporal via live imaging), Axis B/C, claim 2 · imaging supplies spatial + temporal/live-dynamics context and subcellular structure.

> "Highthroughput capabilities enable datasets covering millions of cells, with some technologies capturing genetic perturbations and images or full modalities in spatial omics, revealing cellular neighborhoods in tissues."
> — Multi-modal measurements · bears on: claim 6 (high-throughput feasible), claim 7 (cellular neighborhoods), Axis C · spatial omics reveal cellular neighborhoods in tissue.

> "Technologies such as CITE-seq, REAP-seq, ASAP-seq, and DOGMA-seq integrate transcriptomics with protein quantification (cell surface or intracellular), bridging the gap between gene expression and functional protein measurements. Trimodal assays, such as TEA-seq, allow simultaneous measurement of RNA, chromatin accessibility, and proteins."
> — Multi-modal measurements · bears on: claim 5, claim 8, Axis A · co-assays bridge gene expression and functional protein measurement; trimodal RNA+ATAC+protein exists.

> "In addition to spatial omics, spatial multiomics technologies, including DBiT-seq, spatial CITE-seq, SPOTS, SM-OMICS, Stereo-seq-based multiomics, SlideseqV2 extensions, and spatial ATAC-RNA co-profiling methods … enable joint modality measurements, providing spatial organization of cells and subcellular structure."
> — Multi-modal measurements · bears on: claim 6 (spatial multi-omics feasible), claim 2, claim 8, Axis C · catalogs spatial-multiomics assays that give spatial organization + subcellular structure.

> "However, since no single technology currently captures all modalities simultaneously, an anchoring strategy is required to align and integrate different modalities into a shared space… transcriptomics can serve as an anchor modality (a modality shared between different multimodal assays) to integrate Multiome and CITE-seq datasets, connecting chromatin accessibility and protein abundance."
> — Multi-modal measurements · bears on: claim 8 (integration), claim 9 (shared reference/standard), Axis A/standard · no assay captures all modalities; an anchor modality is needed to integrate into a shared space.

> "By contrast, unpaired multimodal assays measure different modalities from different biological samples. For instance, scRNA-seq and spatial transcriptomics performed on similar or replicate samples still measure different cells."
> — Multi-modal measurements · bears on: claim 3 (different cells, not paired), claim 8, claim 10 · most multimodal data are unpaired — different cells, not the same cell observed jointly.

> "However, the restricted amount of paired multimodal measurements limits their capabilities for learning from independent modalities."
> — Multi-modal measurements · bears on: claim 8, claim 9, claim 10 · paired-data scarcity limits multimodal learning.

> "The relative abundance of unpaired measurements motivates the use of distribution alignment strategies, such as optimal transport-based methods, which align feature distributions across modalities without requiring direct cell-to-cell correspondence."
> — Multi-modal measurements · bears on: claim 3 (distribution-to-distribution, no cell-to-cell correspondence), claim 8 · because cell-to-cell correspondence is unavailable, methods align distributions (OT/flow matching).

> "Cross-modal pairing is often imperfect due to technical effects or biological heterogeneity. These constraints motivate compositional multimodal architectures that reuse pretrained unimodal models and restrict cross-modal learning to lightweight interfaces."
> — Challenges in modeling across modalities · bears on: claim 8, claim 9, claim 10 · cross-modal pairing is imperfect from technical/biological effects.

> "Different biological measurements are naturally represented by different data structures… Gene expression data, for instance, is a sparse and highly dispersed count vector for each cell… DNA sequences are typically represented as strings of nucleotides, while imaging data captures spatial information in pixel arrays."
> — Challenges in modeling across modalities · bears on: claim 8 (heterogeneous structures to integrate), claim 9 · each modality has a structurally different representation, complicating integration/standardization.

> "Recent large-scale single-cell studies only capture a tiny fraction of possible cellular states and conditions… Language and vision foundation models benefit from training data that densely sample their underlying distributions—for instance, internetscale corpora… By contrast, recent large-scale single-cell studies only capture a tiny fraction…"
> — Challenges in modeling across modalities · bears on: claim 1, claim 10 · biology lacks the dense data sampling that language/vision enjoy.

> "Spatial transcriptomics and time-series single-cell data provide insights into the organization of cells within tissues and their progression over time during development, differentiation, or disease."
> — Integrating prior knowledge · bears on: claim 2 (spatial), claim 3 / Axis B (temporal trajectory), claim 7 · spatial + time-series data inform tissue organization and temporal progression.

> "Likewise, longstanding insights from developmental biology and time-resolved lineage tracing studies have immense potential to provide critical context for modeling dynamic cellular processes."
> — Integrating prior knowledge · bears on: claim 3 (lineage tracing / temporal), Axis B · lineage tracing / time-resolved studies anchor dynamic-process modeling.

> "Regularization techniques and multi-task learning frameworks can be designed to enforce biological constraints (for example, local continuity in spatial transcriptomics data or temporal smoothness in time-course experiments) during mode[l] training."
> — Integrating prior knowledge · bears on: claim 3 (time-course), claim 7 (spatial continuity), Axis B/C · spatial continuity and temporal smoothness are biological priors to enforce.

> "Biological systems operate across scales, from molecular mechanisms to ecosystems-level phenomena. While most foundation models focus on individual scales… pioneering works envision how to bridge scales… Extending uni-scale foundation models to integrate both across modalities and across biological scales will be crucial for the vision of a virtual cell."
> — Multiscale · bears on: claim 7 (subcellular → tissue scales), claim 8, Axis C · cross-scale (subcellular→tissue) integration is needed for the virtual cell.

> "While multimodal measurements naturally include diverse information, unimodal readouts are often cheaper, and one modality may be more economic than another… it is important to determine optimal strategies for balancing data quantity, modality diversity, and measurement depth…"
> — Multimodal data management · bears on: claim 10 (cost/throughput/depth trade-offs), claim 8 · explicitly frames a quantity vs. diversity vs. depth/cost trade-off across modalities.

> "Images, for example, are often cheap to acquire and comparatively simple to add as an additional modality… However, imaging data, due to the absence of rich spatial labels by default, are usually harder to interpret than, for example, transcriptomics data. In contrast to imaging, profiling the transcriptome jointly with molecular modalities such as chromatin accessibility or protein abundance is more limited in depth and throughput."
> — Multimodal data management · bears on: claim 10 (depth × throughput × cost trade-off), claim 6, Axis A · joint transcriptome+chromatin/protein profiling is depth- and throughput-limited; imaging is cheap but hard to interpret.

> "A significant imbalance persists between unimodal and paired multimodal measurements."
> — Multimodal data management · bears on: claim 8, claim 9, claim 10 · states the structural unimodal-vs-paired data imbalance.

> "A key limitation is that most metrics used to evaluate multimodal models are inherited from unimodal settings and primarily quantify downstream performance, without indicating whether improvements arise from true cross-modal integration or from aggregating redundant information already present in a dominant modality. This obscures whether a model actually exploits complementary signals across modalities."
> — Evaluation · bears on: claim 4 (complementarity), claim 9 (benchmark/standard inadequacy) · current benchmarks cannot tell true cross-modal integration from exploiting a dominant (RNA-like) modality.

> "Addressing this gap will require evaluation criteria and benchmark tasks that are explicitly sensitive to cross-modal complementarity, rather than accuracy alone, particularly in settings where relevant information is distributed across modalities."
> — Evaluation · bears on: claim 9 (need new standards/benchmarks), claim 4 · calls for benchmarks sensitive to cross-modal complementarity.

> "An example is cross-modality prediction, which evaluates a model's ability to predict one modality from another, for example predicting protein abundance from transcriptomics data. This task can provide a metric for mutual information across different modalities…"
> — Evaluation · bears on: claim 4 (RNA→protein only partially predictable), claim 5, claim 8 · proposes predicting protein from transcriptome as a cross-modal mutual-information probe.

> "Gaining a comprehensive understanding of cellular states and dynamics through the development of large, diversely pretrained, and adaptable multimodal single-cell foundation models will require comparable efforts to build and maintain integrated repositories of single-cell multi-omics measurements."
> — INTRODUCTION · bears on: claim 9 (integrated repositories / standards), claim 1 · multimodal progress will require building/maintaining integrated multi-omics data repositories.

> "These approaches typically rely on classical supervised or unsupervised learning techniques applied to a limited number of datasets… they are not designed to generalize knowledge across diverse samples and datasets… they require training exclusively on the same set of samples that are intended for subsequent analyses, limiting their capacity for broader applicability and cross-sample knowledge transfer."
> — INTRODUCTION · bears on: claim 1 (poor generalization), claim 9 (cross-sample non-transfer) · pre-foundation-model methods do not generalize across datasets; each new dataset needs independent training.

> "Despite significant progress, challenges remain, particularly concerning the structural differences of modality representations, data availability, and the scarcity of biological samples relative to the complexity of cellular systems."
> — CONCLUSIONS · bears on: claim 1, claim 8, claim 10 · concedes data availability and sample scarcity as the standing challenges.

> "Strategic management of increasingly large and diverse multimodal datasets, considering the balance between data quantity, modality diversity, and measurement cost, is paramount."
> — CONCLUSIONS · bears on: claim 9, claim 10 · names data management / quantity-diversity-cost balance as paramount.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data/observation is the bottleneck, data-driven models generalize poorly | "Without diverse observations, even the most effective models…" / MULTI-MODALITY; "only capture a tiny fraction…" / Challenges; "not designed to generalize…" / INTRODUCTION | supports |
| Claim 2 — scRNA-seq loses spatial information | "spatial transcriptomic data … capturing cell-cell interactions within tissue environments" / INTRODUCTION; spatial multiomics list / Multi-modal measurements | nuances |
| Claim 3 — destructive sequencing can't observe time pairs | "unpaired … still measure different cells" / Multi-modal measurements; "align feature distributions … without … cell-to-cell correspondence" / Multi-modal measurements; "live dynamics" via imaging / Multi-modal measurements; lineage tracing / Integrating prior knowledge | nuances |
| Claim 4 — modalities orthogonal / mutually irreplaceable | "biological modalities often encode complementary information" / Challenges; "recover information absent from any single view" / Challenges; "not observable from any single modality alone" / INTRODUCTION | supports |
| Claim 5 — protein / metabolite essential for function & phenotype | "Single-cell proteomics … functional perspective" / Multi-modal measurements; "proteins, and metabolites that … carry out biological functions" / MULTI-MODALITY | supports |
| Claim 6 — high-throughput spatial proteomics feasible | spatial CITE-seq / SPOTS / spatial multiomics list / Multi-modal measurements; "datasets covering millions of cells" / Multi-modal measurements | supports |
| Claim 7 — spatial organization / microenvironment shapes cell state | "revealing cellular neighborhoods in tissues" / Multi-modal measurements; "cell-cell communication processes" / INTRODUCTION; cross-scale subcellular→tissue / Multiscale | supports |
| Claim 8 — multimodal provide orthogonal info, need integration | "integration and alignment of data across modalities" / Multi-modal measurements; "anchoring strategy … into a shared space" / Multi-modal measurements | supports |
| Claim 9 — data islands / cross-paper incomparability / lack of standards | "imbalance … unimodal and paired" / Multimodal data management; "metrics … inherited from unimodal settings" / Evaluation; "integrated repositories" / INTRODUCTION | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma / measurement trade-offs | "balancing data quantity, modality diversity, and measurement depth" / Multimodal data management; "more limited in depth and throughput" / Multimodal data management | supports |
| Whole-paper stance (model/architecture-first vs. our data-first thesis) | compositional AI as "engineering and architectural solution" / MULTI-MODALITY; framing focuses on architectures not data standards | challenges |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Figure 1A | Three directions for building single-cell foundation models: Modeling, Scale, Observation. |
| Figure 1B | Compositional foundation model = modular assembly of independently pre-trained modality-specific FMs (e.g., RNA-seq, microscopy, molecular graphs); also depicts the differing data structures per modality. |
| Figure 2 | Cross-modality alignment/integration via paired or co-assayed measurements; within- vs. cross-modality attention. |
| Figures 3A–3D | Four attention building blocks: (A) fused self-attention, (B) all-to-all self-attention, (C) within-modality self-attention, (D) cross-modality attention. |
| Box 1 | Definitions of the four attention building blocks (fused / all-to-all / within-modality / cross-modality). |
| Box 2 | Evaluation tasks, split into Expert-annotation-based (subcellular/function, cell-type/state, niche/spatial-domain, disease-state, trajectory/lineage) and Intrinsic/expert-agnostic (masked-feature reconstruction, cross-modality prediction/matching, perturbation-response prediction, joint embedding). |
| Table 1 | Compares bi-encoder vs. cross-encoder vs. language-encoding (LLM) integration approaches across architecture, interaction point, output, accuracy, efficiency, scalability, typical use cases. |
| Table 2 | Catalog of existing multimodal single-cell models with architecture / modalities / key traits: scCLIP (bi-encoder, RNA+ATAC), SCARF (bi-encoder, RNA+ATAC), Nicheformer (cross-encoder, RNA+spatial), CellPLM (cross-encoder, RNA+spatial), scGPT-spatial (cross-encoder, RNA+spatial), CellWhisperer (bi-encoder, bulk/scRNA+text), Precious3GPT (cross-encoder; transcriptomics/epigenetics/proteomics/knowledge graphs), STPath (WSI image+spatial transcriptomics), GenePT/Cell2Sentence/CELLama/scELMo/scChat (language encoding, RNA/spatial+text), LangCell/OKR-Cell/spEMO (bi-encoder, RNA or spatial+text/pathology), CellHermes (language encoding; scRNA+PPI+text), CAPTAIN (bi-encoder, scRNA+proteomics, cross-modal attention fusion). |

---

## Primary Sources Behind Key Quotes
- Single-cell proteomics as a functional layer (and feasibility, single cells → clinical) → Guo, T., Steen, J.A., and Mann, M. (2025), *Nature* 638:901–911, ref 67. [Note: "Guo, T." = T. Guo — verify whether this is the group's own line of work; flagged for first-hand reading.]
- Deep Visual Proteomics / spatial proteomics depth → Rosenberger, F.A., et al. (2025), *Nature* 642:484–491, ref 77.
- CITE-seq (joint transcript + surface protein in single cells) → Stoeckius, M., et al. (2017), *Nat. Methods* 14:865–868, ref 93.
- Single-cell multimodal omics overview ("the power of many") → Zhu, C., Preissl, S., and Ren, B. (2020), *Nat. Methods* 17:11–14, ref 84.
- Virtual-cell vision (priorities & opportunities) → Bunne, C., et al. (2024), *Cell* 187:7045–7063, ref 49.
- Transformers in single-cell omics review → Szałata, A., et al. (2024), *Nat. Methods* 21:1430–1443, ref 50.
- Toward multimodal foundation models in molecular cell biology → Cui, H., et al. (2025), *Nature* 640:623–633, ref 51.
- scPairing (inferring/synthesizing cross-modal pairs) → Niu, J., Vasquez-Rios, C., and Ding, J. (2025), *Cell Rep. Methods* 5:101211, ref 122.
- SCimilarity (cell-ontology-aware atlas FM) → Heimberg, G., et al. (2025), *Nature* 638:1085–1094, ref 170.
- Cross-scale foundation-model proposal (cross-attention + cross-scale fine-tuning) → Kalfon, J., Cantini, L., and Peyre, G. (2025), bioRxiv 2025.05.16.653447, ref 183.
- scRNA-seq foundational drivers cited for the field — Geneformer: Theodoris, C.V., et al. (2023), *Nature* 618:616–624, ref 4; scGPT: Cui, H., et al. (2024), *Nat. Methods* 21:1470–1480, ref 5.

---

## Flags
- [ ] Metadata unverified: The cleaned source body does NOT contain the paper's own author byline, DOI, or received/accepted/published dates. Venue is inferred only from the running header "Cell Systems Perspective" (line 229). Year inferred as ~2025 because references extend to 2025 — not confirmed in text.
- [ ] Reconstructed (NOT in source text): Author identities are only initials in Acknowledgments — M.B., T.R., N.A.S., F.J.T. F.J.T. is consistent with "Theis, F.J." (recurring senior author across the reference list); N.A.S. is consistent with "Schmacke, N.A." (refs 68, 78); these are inferences, not stated authorship. Do not print full names as fact.
- [ ] Read at source: Guo, T., Steen & Mann 2025 (*Nature* 638:901–911, ref 67) — single-cell→clinical mass-spec proteomics, directly on-thesis for the protein-modality gap; read first-hand. Also Bunne et al 2024 (ref 49, virtual-cell priorities) and Cui et al 2025 (ref 51, multimodal FMs in molecular cell biology) are the closest review counterparts to our perspective.
- [ ] Source inconsistency / OCR: The cleaned MD has OCR artifacts in tables (Table 1, Table 2, Box 2) and minor typos ("a virtua cell", "mode training", "digital histopathology 52"). Reference superscript numbers are sometimes rendered inline (e.g., "152", "37", "63"). Some excerpts above lightly normalize spacing/typos to read as sentences; for exact characters consult the source path. Figure/Box page numbers are unknown (no page markers in the cleaned text) → page anchors omitted / marked approximate.
- [ ] Temporal-axis caveat (claim 3): This paper treats time mainly via imaging "live dynamics", time-series data, and lineage-tracing priors; it does NOT frame destructive measurement as a hard constraint preventing same-cell temporal pairing. Its strongest adjacent concession is that unpaired assays "measure different cells" and that methods align distributions rather than cell-to-cell correspondences.
