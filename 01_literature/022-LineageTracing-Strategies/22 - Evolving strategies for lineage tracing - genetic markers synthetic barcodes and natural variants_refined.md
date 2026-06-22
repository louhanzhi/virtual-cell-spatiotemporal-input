# Evolving strategies for lineage tracing: Genetic markers, synthetic barcodes, and natural variants — Source Index

**Authors:** Zhixin Kang, Hui Chen, Siyang Li, Shou-Wen Wang, Bin Zhou
**Journal / Venue:** Cell Stem Cell, 2026 (inferred from DOI prefix 10.1016/j.stem; corresponding author S.-W. Wang at Westlake University; B.Z. listed on the Cell Stem Cell Advisory Board) — volume/issue/pages/exact publication date not printed in the cleaned text; see Flags
**DOI:** doi:10.1016/j.stem.2026.05.001
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/22 - Evolving strategies for lineage tracing - genetic markers synthetic barcodes and natural variants_cleaned.md

---

## In One Sentence
A review that synthesizes lineage tracing into three methodological pillars — prospective genetic markers, high-throughput synthetic barcodes, and retrospective natural variants (somatic SNVs, mtDNA, DNA-methylation epimutations) — and surveys their integration with single-cell multi-omics, spatial profiling, and the computational tools that link cell lineage history to cell state.

## Orientation (non-binding)
This is the field-defining methods review for the literature class our context file names under Claim 3 ("destructive sequencing cannot pair-observe time → trajectory inference / lineage tracing / Waddington-OT"). It is a primary feed for Axis B (temporal) and supplies repeated author-conceded facts that double as support for our thesis: single-cell sequencing is destructive, transcriptomic similarity does not equate to lineage/fate, and RNA/ATAC states do not retain clonal memory (whereas DNA/methylation do). It also feeds Claims 2/7/8/10 and Axes C/Standard through its sections on spatial integration, multi-omics co-capture, and resolution-vs-context-vs-scale trade-offs. It can serve as BOTH support (concessions about what dissociated transcriptomics loses) and as a named workaround field (engineering tricks to recover time/space/lineage that the dominant paradigm discards). The downstream agent decides the role.

---

## Load-Bearing Excerpts

> "Elucidating cell fate decision-making requires linking lineage history to dynamic phenotypic states."
> — SUMMARY · bears on: C3, Axis B · frames the core problem as joining temporal ancestry to molecular state.

> "Driven by single-cell sequencing and genome engineering, lineage tracing has evolved from observational studies into a multidimensional, high-throughput discipline."
> — SUMMARY · bears on: C3, Axis B · positions lineage tracing as the high-throughput discipline for recovering fate paths.

> "Cell fate choice is often conceptualized using Waddington's landscape, where a cell rolls down a branched, contoured hill, progressively restricting its developmental potential until it settles in a terminal valley."
> — INTRODUCTION · bears on: C3, Axis B · the Waddington framing our context names (Waddington-OT class).

> "Crucially, these barcodes can be directly integrated with single-cell sequencing to enable high-resolution state-to-fate mapping."
> — INTRODUCTION · bears on: C3, C8, Axis B · synthetic barcodes link clonal/temporal history to single-cell state.

> "LARRY revealed that hematopoietic progenitors commit to specific lineages days before these fate biases manifest transcriptomically."
> — Static barcoding · bears on: C4, C3, Axis B · transcriptome lags fate commitment; RNA state alone does not reveal already-determined fate.

> "Meanwhile, tools such as CaTCH and ClonMapper overcome the destructive nature of single-cell sequencing by using targeted CRISPR activation to induce fluorescent reporters only in specifically barcoded cells, enabling physical isolation of live clones of interest."
> — Static barcoding · bears on: C3, Axis B · explicit statement that single-cell sequencing is destructive, motivating live-cell recovery.

> "Historically, viral barcoding was restricted to in vitro or transplantation assays that often fail to reflect true native physiology."
> — Static barcoding · bears on: C7, C10 · in vitro / transplantation assays do not reflect native physiology.

> "By tracking clones in their native environment, the Sleeping Beauty system challenged previous transplantation models, demonstrating that steady-state hematopoiesis is highly polyclonal—driven by thousands of successive progenitor waves rather than a few dominant stem cells."
> — Static barcoding · bears on: C7, C10 · native-context measurement overturns transplantation-derived conclusions.

> "this creates a severe structural bottleneck known as 'inter-site dropout,' where a single large deletion can erase previously encoded mutations, irreversibly destroy ancestral information, and fragment the downstream phylogenetic tree."
> — Evolvable barcoding · bears on: C3, C9 · the temporal recorder itself can lose ancestral (time) information.

> "the SMALT system leverages base editing to generate high-depth trees with a median statistical support value of approximately 90%."
> — Practical challenges in synthetic lineage tracing · bears on: C9, Standard · quantitative reliability metric for a recorder.

> "achieving an error rate below 1% requires a barcode diversity at least 100 times larger than the target population."
> — Practical challenges in synthetic lineage tracing · bears on: C9, Standard · quantitative QC requirement to avoid homoplasy artifacts.

> "The second challenge is data sparsity, which occurs when only a small fraction of cells within a clone are ultimately sampled... This incomplete capture can create the illusion of smaller, highly coherent clones, leading to erroneous conclusions of early fate priming."
> — Practical challenges in synthetic lineage tracing · bears on: C9, C10 · undersampling/dropout produces false biological conclusions.

> "the CARLIN mouse model, for instance, recovers only about 10% of barcodes."
> — Practical challenges in synthetic lineage tracing · bears on: C9, C10 · quantitative low barcode-recovery rate.

> "Computationally, only biological conclusions robust to additional data subsampling should be trusted."
> — Practical challenges in synthetic lineage tracing · bears on: C9, Standard · robustness/validation principle.

> "However, these multimodal integrations must be applied cautiously, as transcriptomic similarity does not inherently dictate lineage similarity."
> — Practical challenges in synthetic lineage tracing · bears on: C4 · transcriptome similarity ≠ lineage; modalities carry orthogonal information.

> "Generally, stability follows a clear hierarchy: DNA sequence > DNA methylation > histone modifications > chromatin accessibility (assay for transposase-accessible chromatin [ATAC]) and RNA expression."
> — Natural lineage tracing with endogenous variants · bears on: C4, Axis A · different molecular modalities differ systematically in heritable stability.

> "Whereas DNA sequences are stably inherited across successive divisions, ATAC and transcriptomic profiles fluctuate dynamically in response to state changes, despite the existence of a few memory genes that persist over several divisions."
> — Natural lineage tracing with endogenous variants · bears on: C4, Axis A, Axis B · RNA/ATAC states are dynamic and not stably inherited.

> "Highlighting this hierarchy, multi-omics tracing recently demonstrated that DNA methylation patterns of HSCs retain robust clonal memory from embryonic development through adulthood, whereas ATAC and RNA states do not."
> — Natural lineage tracing with endogenous variants · bears on: C4, C8, Axis A, Axis B · RNA modality fails to carry the heritable/temporal memory that methylation retains — direct non-substitutability evidence.

> "Both genetic markers and synthetic barcodes rely on transgenic engineering, precluding their use in human subjects."
> — Natural lineage tracing with endogenous variants · bears on: C10 · transgenesis constraint restricts applicability.

> "By cleanly capturing rare somatic variants associated with distinct lineages, high-resolution phylogenetic trees can be reconstructed, where branch lengths directly correlate with elapsed time."
> — Resolving histories via somatic DNA mutations · bears on: C3, Axis B · endogenous variants recover real elapsed time, not just inferred order.

> "Although this single-cell approach remains cost-prohibitive for routine application, the ability to jointly profile somatic mutations and transcriptomic states represents a major leap forward for natural variant tracing in human tissues."
> — Resolving histories via somatic DNA mutations · bears on: C8, C10 · joint genotype+transcriptome profiling, at high cost.

> "Because mitochondria segregate randomly during cell division, heteroplasmic mutations are subjected to intracellular selection and neutral drift, driving variants toward either complete fixation or total loss in descendant cells. Consequently, accurate phylogenetic tree reconstruction is inherently challenging, leaving analyses susceptible to misinterpretation."
> — Resolving histories via mitochondrial DNA mutations · bears on: C3, C9 · a natural temporal recorder whose noise/drift limits reliable reconstruction.

> "Early studies estimated that DNA methylation yields an error rate of approximately 0.001 per CpG site per division, suggesting that roughly 10,000 epimutations could arise across the human genome per cell cycle."
> — High-resolution lineage tracing via DNA methylation · bears on: C4, Axis A · quantitative epimutation rate; methylation as a large information reservoir.

> "Benchmarked against ground-truth synthetic barcodes, MethylTree achieves nearly 100% accuracy. Notably, epimutation-resolved clones precisely match DARLIN barcodes induced at E10."
> — High-resolution lineage tracing via DNA methylation · bears on: C9, Standard · benchmarking a natural-variant method against an engineered ground truth.

> "Genetic markers, synthetic barcodes, and natural variants have revolutionized ancestry reconstruction, but lineage history alone provides an incomplete picture of cell fate."
> — Integrating lineage history with molecular and spatial states · bears on: C8 · lineage data must be combined with other modalities.

> "To decode the underlying regulatory networks, lineage readouts are now co-captured with molecular and spatial data at the single-cell level."
> — Integrating lineage history with molecular and spatial states · bears on: C8, Axis C · co-capture of lineage + molecular + spatial.

> "Moving beyond isolated phylogenetic trees, these integrated approaches establish the link between a cell's ancestry, phenotype, and physical microenvironment."
> — Integrating lineage history with molecular and spatial states · bears on: C7, C8, Axis C · explicit triad of ancestry × phenotype × microenvironment.

> "Camellia-seq captures lineage barcodes alongside transcriptomic, chromatin accessibility, and DNA methylation profiles."
> — Integrating lineage history with molecular and spatial states · bears on: C8, Axis A · multimodal single-cell co-profiling example.

> "In human contexts, MethylTree enables non-invasive, multi-omics lineage tracing by jointly profiling RNA expression and DNA methylation, allowing analysis of lineage, transcriptome, and epigenome in single cells."
> — Integrating lineage history with molecular and spatial states · bears on: C8 · joint lineage + transcriptome + epigenome in human cells.

> "Integrating barcode information with spatial location represents another critical frontier for dissecting how cell-cell interactions and native microenvironments shape cell fate."
> — Integrating lineage history with molecular and spatial states · bears on: C7, Axis C · spatial context shapes fate.

> "Classic marker-based lineage tracing inherently captures spatial information at low cost and high throughput. Although labeled cells can be sorted for single-cell profiling, the lack of lineage barcode diversity fundamentally limits resolution at the single-cell level."
> — Integrating lineage history with molecular and spatial states · bears on: C2, C7, C10, Axis C · trade-off between preserving spatial info and single-cell clonal resolution.

> "Recent advancements in spatial profiling—progressing from the 55-μm spots of Visium to the 500-nm resolution of Stereoseq—have enabled spatial lineage tracing with synthetic barcodes at high resolution, albeit at high cost."
> — Integrating lineage history with molecular and spatial states · bears on: C2, C10, Axis C · quantitative spatial-resolution gains traded against cost.

> "Ultimately, the choice of platform is dictated by the competing needs for phylogenetic depth versus the preservation of the native physical microenvironment."
> — Integrating lineage history with molecular and spatial states · bears on: C10, Axis C · explicit resolution-vs-spatial-context trade-off.

> "Although scRNA-seq data alone can be utilized to infer differentiation dynamics via pseudotime analysis or RNA velocity, these approaches are inherently limited by the absence of true temporal constraints and are shown to perform poorly in distinguishing early fate bias among progenitors."
> — Computational integration of lineage and state dynamics · bears on: C1, C3, Axis B · transcriptome-only trajectory inference lacks true temporal constraints and fails at early fate bias.

> "By explicitly integrating lineage history with transcriptomic state information, the underlying differentiation processes can be captured with significantly higher fidelity."
> — Computational integration of lineage and state dynamics · bears on: C3, C8, Axis B · adding true lineage/temporal data raises fidelity over transcriptome alone.

> "For evolving barcodes, optimal transport (OT) algorithms, such as LineageOT and moslin, reconcile known lineage relationships with transcriptomic distances to compute the most probable flow of cells between successive time points. However, their foundational assumption that lineage similarity dictates fate similarity must be applied cautiously, as it may fail in contexts of divergent or convergent differentiation."
> — Computational integration of lineage and state dynamics · bears on: C3, C4, Axis B · the Waddington-OT class our context names, plus a caveat on its core assumption.

> "Despite these recent advances, the computational integration of lineage and state information remains a formidable challenge. Resolving these analytical bottlenecks may require additional analytical paradigms that can account for challenges such as complex kinetics, heterogeneous sampling, barcode dropout, and the absence of ancestral states."
> — Computational integration of lineage and state dynamics · bears on: C1, C9 · open computational bottlenecks for fusing lineage + state.

> "Selecting a readout strategy requires balancing phylogenetic resolution, spatial context, and experimental scale."
> — Practical design guidance · bears on: C10 · three-way readout trade-off.

> "Although bulk sequencing coupled with fluorescence-activated cell sorting (FACS) lacks single-cell granularity, it enables cost-effective clonal quantification across millions of cells, mitigating the sampling bias of lower-throughput methods... single-cell sequencing provides superior resolution for reconstructing trajectories and multi-omics states but remains constrained by higher per-cell costs."
> — Practical design guidance · bears on: C10 · resolution vs throughput vs cost trade-off (bulk vs single-cell).

> "Translating these approaches into the clinic requires overcoming inherent trade-offs between sequencing cost, phylogenetic precision, and cellular scalability."
> — Opportunities and future directions · bears on: C10 · cost × precision × scale trilemma.

> "This requires moving beyond standard transcriptomics to incorporate co-profiling of the epigenome, direct mapping of physical cell-cell contacts, and logging of historical molecular signaling events."
> — Opportunities and future directions · bears on: C4, C7, C8, Axis A, Axis C · explicit call to go beyond transcriptomics to more modalities.

> "Seamlessly integrating continuous lineage trees with next-generation spatial profiling technologies will eventually illuminate how the physical microenvironment and localized niche interactions cooperatively prime cell fate decisions over time."
> — Opportunities and future directions · bears on: C7, C8, Axis B, Axis C · uniting temporal lineage with spatial microenvironment.

> "these state manifolds may not inherently represent lineage relationships, as transcriptomic similarity does not necessarily equate to lineage proximity."
> — Figure 1A legend · bears on: C4, Axis B · transcriptomic manifold ≠ lineage structure.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| C1 · data is bottleneck / data-driven generalizes poorly | "scRNA-seq data alone... inherently limited by the absence of true temporal constraints" / Computational integration | supports |
| C2 · scRNA-seq loses spatial info | "dissociation-based readout undersamples" / Table 2; "Classic marker-based lineage tracing inherently captures spatial information" / Integrating | supports |
| C3 · destructive sequencing can't pair-observe time → trajectory / lineage / Waddington-OT | "overcome the destructive nature of single-cell sequencing" / Static barcoding; "optimal transport... LineageOT and moslin" / Computational integration; Waddington landscape / Introduction | supports |
| C4 · modalities orthogonal, non-substitutable (RNA can't cover other layers) | "DNA methylation patterns... retain robust clonal memory... whereas ATAC and RNA states do not" / Natural variants; "transcriptomic similarity does not... dictate lineage similarity" | supports |
| C5 · protein / metabolism modalities indispensable to function & phenotype | (not directly addressed; paper covers DNA/methylation/RNA/ATAC, not proteomics/metabolomics) | — |
| C6 · high-throughput spatiotemporal proteomics feasible | (not addressed; no proteomics methods discussed) | — |
| C7 · spatial organization / microenvironment changes cell state & fate | "how cell-cell interactions and native microenvironments shape cell fate" / Integrating; "native physical microenvironment" / Opportunities | supports |
| C8 · multimodal orthogonal info, need integration | "Camellia-seq captures lineage barcodes alongside transcriptomic, chromatin accessibility, and DNA methylation" / Integrating; "co-captured with molecular and spatial data" | supports |
| C9 · data islands / cross-paper incomparable / lack of standard | "data sparsity..."; "barcode diversity at least 100 times larger"; "Benchmarked against ground-truth synthetic barcodes" / methods sections | supports (QC/benchmark practice) |
| C10 · resolution × throughput × destructiveness trilemma | "balancing phylogenetic resolution, spatial context, and experimental scale" / Practical design; "phylogenetic depth versus... native physical microenvironment" / Integrating | supports |
| Axis A · modality | stability hierarchy "DNA sequence > DNA methylation > ... > RNA expression" / Natural variants | nuances |
| Axis B · temporal | "branch lengths directly correlate with elapsed time" / SNV section; "absence of true temporal constraints" / Computational integration | supports |
| Axis C · spatial | "from the 55-μm spots of Visium to the 500-nm resolution of Stereoseq" / Integrating | supports |
| Standard · QC / comparable / integrable | "error rate below 1% requires a barcode diversity at least 100 times larger"; "median statistical support value of approximately 90%" | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 | Catalog of modern lineage tracing approaches across the three pillars (genetic markers; synthetic static + evolvable barcodes; natural SNV/mtDNA/methylation), with representative methods and suggested reviews. |
| Table 2 | Side-by-side evaluation of the three pillars on applicable system, labeling specificity, lineage diversity (genetic marker low 1–10; synthetic high; natural high), lineage recovery, temporal control (genetic marker yes/inducible; synthetic partial; natural none), readout (note: synthetic + natural readouts are destructive; genetic marker can be imaging-based), key strengths/limitations. Load-bearing for C10 trade-offs and Axes B/C. |
| Figure 1 | The three pillars + Waddington-landscape framing of cell fate; legend states transcriptomic similarity does not necessarily equate to lineage proximity (C4). |
| Figure 3D | Linking lineage history to molecular and spatial states (FACS+PCR bulk; single-cell RNA/multi-omics; spatial via sequencing or imaging) — C8, Axis C. |
| Figure 4A | Stability hierarchy of natural variants in the cell (nuclear DNA most stable; ATAC/RNA dynamic) — C4, Axis A. |
| Figure 5 | Decision guide for selecting a lineage tracing approach by biological question — C10. |
| Quantitative anchors | barcode diversity ≥100× target population for <1% homoplasy error; CARLIN recovers ~10% of barcodes; LARRY >70% and DARLIN ~70% lineage barcode recovery; SMALT trees ~90% median statistical support; MethylTree ~100% accuracy vs synthetic ground truth; methylation error ~0.001 per CpG per division (~10,000 epimutations/cell cycle); mtDNA mutation rate 10–100× nuclear; Visium 55-μm spots vs Stereo-seq 500-nm resolution; SNV rate ~1 per cell division; MethylTree estimated ~250 de novo HSC clones in early murine blood. |

---

## Primary Sources Behind Key Quotes
- LARRY: lineage commitment precedes transcriptomic manifestation; >70% barcode recovery → Weinreb, Rodriguez-Fraticelli, Camargo, Klein 2020, Science 367:eaaw3381, ref #5.
- Transcriptomic similarity ≠ lineage proximity → refs #5–8 (Weinreb 2020 Science 367; Xie et al. 2023 Nat. Methods 20:1244–1255; Chen et al. 2022 [Live-seq] Nature 608:733–740; Barile et al. 2021 Genome Biol. 22:197).
- DNA methylation retains clonal memory while ATAC/RNA do not; DARLIN/Camellia-seq joint lineage+transcriptome+epigenome → Li et al. 2023, Cell 186:5183–5199.e22, ref #44.
- MethylTree (non-invasive methylation lineage tracing; ~100% vs ground truth) → Chen, Fu, Chen, Li, Wang 2025, Nat. Methods 22:488–498, ref #57.
- EPI-Clone (targeted scTAM-seq epimutation tracing in blood ageing) → Scherer et al. 2025, Nature 643:478–487, ref #58.
- Pseudotime / RNA velocity (limited by absence of true temporal constraints) → Trapnell et al. 2014, Nat. Biotechnol. 32:381–386, ref #141; La Manno et al. 2018, Nature 560:494–498, ref #140; poor early-fate-bias performance → refs #5, #8.
- CoSpar (transition matrices from static+evolving barcodes; resolves HSC fate bias) → Wang, Herriges, Hurley, Kotton, Klein 2022, Nat. Biotechnol. 40:1066–1074, ref #142.
- LineageOT → Forrow & Schiebinger 2021, Nat. Commun. 12:4940, ref #143; moslin → Lange et al. 2024, Genome Biol. 25:277, ref #144.
- CARLIN ~10% barcode recovery → Bowling et al. 2020, Cell 181:1410–1422.e27, ref #104.
- Stereo-seq 500-nm spatial atlas → Chen et al. 2022, Cell 185:1777–1792.e21, ref #134; Visium / spatial transcriptomics → Ståhl et al. 2016, Science 353:78–82, ref #135.
- SMALT (base-editing high-depth phylogeny, ~90% support) → Liu et al. 2021, Nat. Methods 18:1506–1514, ref #52.
- Sleeping Beauty native polyclonal hematopoiesis → Sun et al. 2014, Nature 514:322–327, ref #39.
- MAESTER / mtscATAC-seq (mtDNA + state co-capture) → Miller et al. 2022, Nat. Biotechnol. 40:1030–1034, ref #60; Lareau et al. 2021, Nat. Biotechnol. 39:451–461, ref #61.
- Waddington landscape framing → Ferrell 2012, Curr. Biol. 22:R458–R466, ref #4; Dymecki, Ray, Kim 2010, Methods Enzymol. 477:183–213, ref #3.

---

## Flags
- [ ] Metadata unverified: exact volume/issue/page numbers and printed received/accepted/published dates are not present in the cleaned text. Venue (Cell Stem Cell) and year (2026) are inferred from the article DOI (10.1016/j.stem.2026.05.001), the corresponding author's affiliation, and the Cell Stem Cell Advisory Board mention — treat as high-confidence but text-unconfirmed.
- [ ] Routing note (not an error): corresponding author Shou-Wen Wang is at Westlake University (same institution as the perspective we are writing); several cited computational methods (CoSpar, MethylTree) are from this group. Relevant when deciding self-vs-external citation, not a metadata issue.
- [ ] Scope note: this paper does NOT address proteomics, PTMs, metabolomics, or interactomes (our Claims C5/C6, Axis A protein/metabolite rows). It contributes to Axis A only on the DNA/methylation/ATAC/RNA stability hierarchy. Do not over-extend it to protein-modality claims.
- [ ] Read at source: for the strongest single-modality-insufficiency quote ("DNA methylation retains clonal memory... whereas ATAC and RNA states do not"), read Li et al. 2023 Cell (ref #44) first-hand; for "lineage commitment precedes transcriptomic signature," read Weinreb et al. 2020 Science (ref #5, LARRY) first-hand.
- [ ] Source inconsistency: the cleaned text contains OCR artifacts in some reference strings (e.g., split/garbled author initials and method names in the Table 1 cell and refs #50, #121, #126); reference numbers and DOIs above were taken from the clean reference list, but double-check any reference re-typed from the embedded Table 1 HTML.
