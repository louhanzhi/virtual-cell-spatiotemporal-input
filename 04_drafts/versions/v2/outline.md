# Perspective Outline · The Compute-Data Standard for the AI Virtual Cell

> **Genre:** Perspective (a paper with a stated position), not a systematic review.
> **Length:** 1,500–2,000 words, English.
> **Source of thesis:** locked from `00_admin/虚拟细胞数据Perspective_Foundational-Context.md` (which itself fuses the AIVC Webinar extraction with the data-direction doc). The v1 outline (`v1/outline.md`) treated only space + time; this v2 adopts the **broader, authoritative thesis** the Foundational-Context settled on — space **and** time **and** irreplaceable modalities **and** integrability.
> **Citation rule applied throughout:** only peer-reviewed / formally published work is cited. Preprints (bioRxiv/arXiv), editorials, and "Method of the Year"-type news pieces are **not** cited; where an idea comes from such a source, it is flagged `[idea, not cited]` and a published replacement is named. Reference pool = `01_literature/` folders + `candidate-40-literature_2026-06-17.md` (already vetted for eligibility) + `references.bib`. Webinar material is used as **motivation/voice only, never as a citation**.

---

## THESIS (one sentence — the whole paper argues only this)

> **The AI virtual cell is racing ahead on models while standing on a data foundation that structurally discards space and time, is nearly RNA-only, and is balkanized into non-comparable islands; what the field actually needs is a *compute-data standard* — data that explicitly encode spatiotemporal resolution, span the mutually-irreplaceable modalities, and are integrable and comparable.**

**Compressed:** the virtual cell's bottleneck is not the model but the data — *spatiotemporally resolved, integrable, multimodal* data. This Perspective defines what that standard must contain.

**Organizing principle (the spine of the body):** `compute-data standard = modality × spatiotemporal resolution × integrability`. The current paradigm has a *systematic deficit on every one of these axes.*

---

## 0. Opening hook (~150 words)

- **Move:** Everyone answering "what data does a virtual cell need?" slides to the same shopping list — transcriptome, proteome, epigenome, metabolome, "the more scales/modalities the better." That list hides a default assumption: each cell is treated as one homogeneous tube of molecules. Real cells are not. A cell has an **address** (who its neighbors are, what tissue structure it sits in) and a **history** (which state it came from, which fate it is sliding toward). The most mainstream input — **dissociation-based single-cell sequencing** — washes both away at the very first step of sample prep.
- **Land the thesis:** cell-level spatiotemporal, multimodal, integrable data is not a luxury 5th/6th omics; it is the *structurally under-weighted* input dimension that caps model ceilings.
- **Citations:** vision anchor **Bunne et al., *Cell* 2024** (`bunne2024virtualcell`); modality "shopping-list" framing is exactly what **AIVC-Preclinical review, *npj Digital Medicine* 2025** (`aivcpreclinical2025`) enumerates — cite as the representative stance being displaced.
- *(Motivation voice only, not cited: Guo Tiannan's webinar remark that single-cell data "generally has no time information … and spatiotemporal data is actually quite scarce." Use as a one-line epigraph-style observation, attributed to the AIVC Webinar, **not** as a reference.)*

## 1. The bottleneck is the data, not the model (~250 words)

- **Claim:** Foundation models "run ahead," but swap the dataset and they collapse — the ceiling is set by the input, for both mechanistic and data-driven models.
- **Ammunition:**
  - Mainstream single-cell foundation models are trained on tens of millions of **dissociated** cells — *exactly the data that has had space and time washed out*: **Geneformer, *Nature* 2023** (`theodoris2023geneformer`); **scGPT, *Nat. Methods* 2024** (`cui2024scgpt`). Use to name the paradigm under critique.
  - Generalization is weak: zero-shot single-cell FMs often lose to simple baselines — **"Zero-shot evaluation reveals limitations of single-cell foundation models," *Genome Biology* 2025** (candidate #4). Hard evidence for "bottleneck = data, not model."
  - Cross-paper benchmarks are not comparable / generalization is over-estimated — **"Benchmarking algorithms for generalizable single-cell perturbation response prediction," *Nat. Methods* 2025** (candidate #5). (This is the *published* replacement for the CZI arXiv preprint — cite this, not the preprint.)
  - Field-level framing of "data as a pillar": **"Grow AI virtual cells: three data pillars and closed-loop learning," *Cell Research* 2025** (candidate #2) — directly adjacent to our "compute-data standard" framing.
- **Position this paper among reviews (novelty guard):** existing AIVC reviews enumerate modalities but never theorize data requirements as orthogonal axes — **Multi-scale AIVC review, *Briefings in Bioinformatics* 2026** (`multiscaleaivc2026`) and **AIVC-Preclinical, *npj Digital Medicine* 2025** (`aivcpreclinical2025`) as the gap we fill.
- *(Webinar, motivation only: 高张扬 — "I don't believe the pure data-driven, data-specific foundation-model paradigm … swap one dataset and it collapses." Voice, not citation.)*

## 2. The data lost time (~350 words)

- **Claim:** Sequencing is destructive → the same cell cannot be observed before-and-after → time can only be *back-inferred from distributions*, never recorded as a real per-cell clock.
- **The binary the section is built on** *(this two-way framing — destructive snapshot vs. non-destructive live imaging — originally crystallized from the LivecellX preprint; `[idea, not cited]`. Cite the published anchors below instead.)*:
  - **Destructive / inferred time:**
    - Canonical proof that destructiveness forecloses real temporal observation — **Waddington-OT, Schiebinger et al., *Cell* 2019** (`schiebinger2019waddingtonot`). Use its own words ("scRNA-seq destroys cells … one cannot follow the same cell"; "connect discrete snapshots into continuous movies"); note its Markov assumption *explicitly discards history* — strongest ally-and-foil. (See `提取_WaddingtonOT.md`.)
    - Pseudotime ≠ real clock: **Monocle, Trapnell et al., *Nat. Biotechnol.* 2014** (`trapnell2014monocle`); RNA velocity = snapshot extrapolation, not observation: **La Manno et al., *Nature* 2018** (`lamanno2018rnavelocity`).
    - Inference methods are themselves limited/non-comparable — **Saelens et al., "A comparison of single-cell trajectory inference methods," *Nat. Biotechnol.* 2019** (candidate #26).
    - Spatiotemporal version of the same destructive bind, closest to our angle (snapshots not in one coordinate system) — **stVCR, Peng, Zhou & Li, *Nat. Methods* 2026** (`peng2026stvcr`). *(Published in Nat. Methods — citable; the bib's bioRxiv note is just preprint history.)*
  - **Non-destructive / observed time (the contrast solution):** live-cell imaging directly records trajectories + lineage but at lower molecular depth/throughput — **Cellpose, Stringer et al., *Nat. Methods* 2021** (candidate #29) and **Mesmer/DeepCell, Greenwald et al., *Nat. Biotechnol.* 2022** (candidate #28) as the segmentation/tracking substrate; **TrackMate 7, *Nat. Methods* 2022** and **Ultrack, *Nat. Methods* 2025** (reading-list 010/012) for tracking + lineage reconstruction. *(These published papers replace the Caliban/LivecellX preprints — the live-imaging idea is `[idea from Caliban preprint, not cited]`; cite these instead.)*
  - **Lineage as a first-class field, not a downstream add-on** — **lineage-tracing reviews:** "Connecting past and present: single-cell lineage tracing," *Protein & Cell* 2022 (candidate #23); "Evolving strategies for lineage tracing," *Cell Stem Cell* 2026 (candidate #22).
- **Required time fields (what a time input must carry):** timestamp/pseudotime, lineage, trajectory/velocity, division–apoptosis events.
- *(Webinar, motivation only: 高/袁 independently — "the cell dies once measured … it can't be paired before-and-after," supervision is "distribution-to-distribution.")*

## 3. The data lost space (~350 words)

- **Claim:** Dissociation rips the cell out of its spatial organization/microenvironment → subcellular localization and tissue-niche information vanish; reconstructing them by model from dissociated data is imputation, not measurement.
- **Ammunition:**
  - Strongest "space must be an input" evidence: dissociated data cannot train spatial-microenvironment complexity — **Nicheformer, *Nat. Methods* 2025** (`tejadalapuerta2025nicheformer`).
  - Spatial transcriptomics as a measurable input axis — cite **original research, not the Method-of-the-Year editorial** `[editorial, not cited: marx2021methodoftheyear]`: sequencing-based **Ståhl et al., *Science* 2016** (candidate #8a) + imaging-based **MERFISH, Chen et al., *Science* 2015** (candidate #8b).
  - Co-expression graph ≠ spatial adjacency graph; inferring CCI without coordinates is high false-positive — **NCEM, Fischer et al., *Nat. Biotechnol.* 2022** (candidate #38); communication-inference limits — **LIANA+, *Nat. Cell Biology* 2024** (candidate #39).
  - How coordinates actually enter a model / input spec to copy — **CellPLM, Wen et al., ICLR 2024** (`wen2024cellplm`, positional encoding of coordinates) and **Spateo, *Cell* 2024** (`qiu2024spateo`, AnnData `.obsm` coords / `.X` / `.obs`, CCI framework).
- **Required space fields:** absolute coordinates (x, y[, z]); neighborhood graph / niche composition; cell–cell communication (ligand–receptor); morphology/imaging features; subcellular localization.
- *(Webinar, motivation only: 高张扬 — "perturbed spatial microenvironment … is the next problem cell-perturbation models must solve.")*

## 4. The data is too narrow — modalities are mutually irreplaceable (~300 words)

- **Claim:** The input is almost only transcriptome; but RNA, protein, PTM/activity, complexes, metabolism each carry information the others **cannot** compensate. You cannot reconstruct a whole cell from RNA alone. *(This is the paper's distinctive payload and aligns with Guo lab's spatial-proteomics production strength.)*
- **Ammunition (orthogonality = core):**
  - mRNA and protein diverge: a large fraction of loci show inconsistent mRNA–protein direction — **"Simultaneous quantification of mRNA and protein in single cells," *eLife* 2020** (candidate #33); low mRNA–protein correlation w/ methodological correction — **Cell Reports Methods 2022** (candidate #34).
  - Protein is feasible *and* irreplaceable at depth — **"Mass-spectrometry-based proteomics: from single cells to clinical applications," *Nature* 2025** (candidate #31); single-cell proteome depth "beyond cell-type classification," **Nat. Commun. 2024** (candidate #32).
  - PTM / signaling-activity layer that RNA cannot read out — **Phospho-seq, *Nat. Commun.* 2025** (candidate #35).
  - Metabolism = the readout closest to phenotype — **integrative single-cell metabolomics, *Nat. Commun.* 2025** (candidate #36).
  - Modalities each add value → integration is needed (multimodal anchor) — **WNN / Seurat v4, Hao et al., *Cell* 2021** (candidate #37); compositional / multimodal turn — **"From modality-specific to compositional foundation models for cell biology," *Cell Systems* 2026** (candidate #3).
- **Bridge to space+protein (Guo-lab adjacency):** spatial proteomics shows RNA-invisible functional zonation — **single-cell spatial MS hepatocyte zonation, *Nat. Methods* 2023** (candidate #19); high-throughput whole-slice spatial proteomics — **Cell Discovery 2024** (candidate #18); CODEX original research **Goltsev et al., *Cell* 2018** (candidate #14, replaces the spatial-proteomics editorial `[editorial, not cited]`); same-section co-measurement — **DBiTplus, *Nat. Methods* 2025** (candidate #16); AI-guided spatial single-cell proteomics — **Deep Visual Proteomics, *Nat. Biotechnol.* 2022** (candidate #17).

## 5. The data is islands — not comparable, not integrable (~250 words)

- **Claim:** Datasets are produced in isolation, with no shared standard; cross-paper benchmarks aren't comparable; control choice / random splits swing results → you cannot assemble one cell from many islands.
- **Ammunition:**
  - Community-scale corpus is almost entirely dissociated data + serves as a standardized-schema exemplar — **CZ CELLxGENE Discover, *Nucleic Acids Research* 2025** (candidate #40). *(Upgrade `czi2023cellxgene` from the bioRxiv version in the bib to this NAR 2025 published version before citing.)*
  - Standardization/integration challenges at atlas scale — **"Insights, opportunities and challenges provided by large cell atlases," *Genome Biology* 2025** (candidate #6).
  - Spatial-data alignment / unified reference frame is unsolved — **"A comprehensive review of spatial transcriptomics data alignment and integration," *Nucleic Acids Research* 2025** (candidate #12); cross-platform comparability — **subcellular ST benchmark, *Nat. Commun.* 2025** (`subcellularst2025`).
  - Benchmark non-comparability (re-cite from §1) — **Nat. Methods 2025** (candidate #5).
- *(Webinar, motivation only — and the project's live hook: 郭天南 — "existing data are produced separately, with no standard … the same model is completely non-comparable across papers"; Westlake AIVC Week (Aug 3–8, 2026) will discuss AIVC data standards / QC / how to benchmark across datasets. Frame our "ideal spec" as a contribution to that agenda — voice, not citation.)*

## 6. The hard constraint: the resolution × throughput × destructiveness trilemma (~250 words)

- **Claim:** You cannot simultaneously max out resolution, throughput, and non-destructiveness. The *ideal* spatiotemporal-multimodal input does not physically exist today; the data agenda must own this boundary.
- **Ammunition:**
  - At single-cell spatial scale, sequencing-type ST measures only hundreds–to-~thousand genes — **ST selection guide, Lim et al., *BMC Genomics* 2025** (`lim2025stselectionguide`).
  - What each platform can actually output (hard numbers) — **subcellular ST benchmark, *Nat. Commun.* 2025** (`subcellularst2025`); cross-cancer platform comparison (candidate #11); clinical-translation constraints — **Annual Review of Pathology 2024** (candidate #13).
  - Cost of the destructive workaround — Waddington-OT needed 315k cells × 18 days × dense sampling to *approximate* a movie it could not record (**`schiebinger2019waddingtonot`**, see `提取_WaddingtonOT.md` §3).
- *(Webinar, motivation only: bulk vs. single-cell, in-vitro vs. in-vivo trade-offs — note these are an *adjacent* set of measurement trade-offs, not literally the resolution×throughput×destructiveness axes; do not conflate.)*

## 7. Conclusion / Outlook — the ideal compute-data spec (~150 words)

- **Deliverable:** a one-paragraph "ideal compute-data standard" spec:
  `modality (RNA + protein + PTM + metabolism + …, chosen for orthogonality)` × `spatial (coords + niche + CCI + morphology + subcellular)` × `temporal (real time + lineage + trajectory + events)` × `integrable & comparable (shared QC, cross-platform pairing, unified reference frame)`.
- **Open gaps:** cross-platform coordinate alignment; fusing destructive snapshots with non-destructive live imaging; spatiotemporal + multimodal standardization.
- **We can supply it:** Guo lab's high-throughput spatial proteomics maps directly onto the "protein + space + time" gap, and is positioned to help define the standard (echo the Aug AIVC Week agenda — voice, not citation).
- **Citations:** loop back to **Bunne et al., *Cell* 2024** (`bunne2024virtualcell`) community agenda + **Cell Research 2025 three data pillars** (candidate #2); re-land thesis.

---

## Novelty guard (answer when asked "what's new?")

No single paper puts all four together: (1) space + time as orthogonal cell-level **input** axes; (2) modalities as mutually **irreplaceable** (RNA can't stand in for protein/metabolism); (3) integrability/comparability as a first-class requirement, not an afterthought; (4) anchored on **data requirements / a standard**, not model capability, and tied to the measurement **trilemma** that decides whether the input is even obtainable. Existing AIVC reviews (`multiscaleaivc2026`, `aivcpreclinical2025`) list modalities; none theorize the standard.

---

## Citation-eligibility ledger (what is / isn't citable, and the swaps)

**Citable (peer-reviewed / formally published) — safe to `\cite`:**
- `bunne2024virtualcell` (Cell 2024), `tejadalapuerta2025nicheformer` (Nat Methods 2025), `schiebinger2019waddingtonot` (Cell 2019), `peng2026stvcr` (**Nat Methods 2026 — published**, despite bioRxiv note), `lim2025stselectionguide` (BMC Genomics 2025), `qiu2024spateo` (Cell 2024), `subcellularst2025` (Nat Commun 2025), `wen2024cellplm` (**ICLR 2024 — conference proceeding, citable**), `theodoris2023geneformer` (Nature 2023), `cui2024scgpt` (Nat Methods 2024), `trapnell2014monocle` (Nat Biotechnol 2014), `lamanno2018rnavelocity` (Nature 2018).
- `multiscaleaivc2026` (Briefings in Bioinformatics 2026) and `aivcpreclinical2025` (npj Digital Medicine 2025) — peer-reviewed reviews; **but their `.bib` author/title/DOI are still `TODO` — fill & verify before submission.**
- All candidate-40 entries in groups A–H are pre-vetted as published research / peer-reviewed reviews / formal Perspectives (#2,#3,#4,#5,#6,#8a,#8b,#11,#12,#13,#14,#15,#16,#17,#18,#19,#20,#22,#23,#26,#28,#29,#30,#31,#32,#33,#34,#35,#36,#37,#38,#39,#40) — **need to be added to `references.bib` with full metadata.**

**NOT citable — flagged in-text as `[idea, not cited]`, with published replacements:**
- `marx2021methodoftheyear` (Nat Methods "Method of the Year" — **editorial**) → use **Ståhl et al. Science 2016** (#8a) + **Chen et al. Science 2015** (#8b).
- Spatial-proteomics "Method of the Year" / "update" editorials → use **CODEX Goltsev et al. Cell 2018** (#14) + **Cancer & Metastasis Reviews 2025** (#15).
- `schwartz2023caliban` (Caliban — **bioRxiv preprint**) and LivecellX (preprint) → live-imaging/binary idea kept as `[idea, not cited]`; cite **Cellpose** (#29) / **Mesmer** (#28) / **TrackMate 7** / **Ultrack** instead.
- `cellprophet2025` (CellProphet — **bioRxiv preprint**) → use **scNODE, Bioinformatics 2024** (reading-list 011) for the temporal-window-prediction idea.
- `czi2023cellxgene` (**bioRxiv** version in bib) → upgrade to **CZ CELLxGENE Discover, *NAR* 2025** (#40) before citing.
- CZI "Benchmarking AI models in biology" (**arXiv preprint**) → use **Nat. Methods 2025** (#5).

**Never cited — motivation/voice only (AIVC Webinar):** all 郭天南 / 高张扬 / 袁新玉 remarks, the bulk-vs-single-cell & in-vitro-vs-in-vivo trade-off discussion, and the Aug 2026 Westlake AIVC Week agenda. Use as "the field's own live observations," attributed to the webinar, **not** in the reference list.
