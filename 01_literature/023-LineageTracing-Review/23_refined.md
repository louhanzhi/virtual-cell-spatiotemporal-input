# Connecting past and present: single-cell lineage tracing — Source Index

**Authors:** Cheng Chen, Yuanxin Liao, Guangdun Peng (corresponding: peng_guangdun@gibh.ac.cn)
**Journal / Venue:** unverified; see Flags (technical review; Received December 3, 2021, Accepted March 6, 2022)
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/23_cleaned.md

---

## In One Sentence
A technical review of single-cell lineage tracing (SCLT) — the combination of single-cell omics (mainly scRNA-seq) with heritable barcodes (integration, polylox, CRISPR, and base-editing) that record a cell's clonal history so that progenitor-progeny relationships and molecular states can be read out in parallel, with surveys of the barcoding strategies, applications, computational reconstruction methods, and technical limitations.

## Orientation (non-binding)
This paper sits most directly on the **temporal axis (Axis B / roadmap Claim 3)**: it documents the limitations of inferring cell trajectories from dissociated snapshots (pseudotime / RNA velocity) and presents lineage-recording barcodes as the route to recover *true* cell history rather than distribution-inferred trajectories. It can therefore serve BOTH as support for our temporal critique (snapshot-based trajectory inference is unreliable; "state alone" can fail) AND as a named approach whose own concessions a writer can deploy (SCLT is still endpoint/destructive readout, RNA-centric, low-throughput, invasive, and cannot yet build organism-scale or spatially-anchored trees). Secondary touchpoints: spatial (Axis C — its closing call to integrate lineage tracing + spatial transcriptomics + imaging "in both space and time"), integration/standards (Claims 8–9 — assembling separate lineage trees, standardizing analysis), and measurement trade-offs (Claim 10 — throughput/cost/invasiveness). The downstream agent decides which role to assign.

---

## Load-Bearing Excerpts

> "current research based on single-cell transcriptomics heavily relies on pseudotemporal ordering to infer cell trajectories and connective lineage relationships. However, route descriptions of state transitions may or may not be equivalent to the true lineage paths of a progenitor population, and severe limitations remain to be resolved before accurate inferences can be achieved."
> — INTRODUCTION / p.1 · bears on: Claim 3, Axis B · States that trajectory/lineage relationships inferred from transcriptomic snapshots are not equivalent to the true lineage paths.

> "First, a confident inference of cell trajectory requires substantial sampling of cells, which may be impeded by the incomplete or insufficient coverage of scRNA-seq in some cases (Tanay and Regev, 2017)."
> — INTRODUCTION / p.1 · bears on: Claim 3, Claim 10, Axis B · Sampling limitation of scRNA-seq undermines trajectory inference.

> "Second, cell fates may converge in specific situations. A well-known example of lineage convergence is that the definitive endoderm has both extra-embryonic and embryonic origins"
> — INTRODUCTION / p.1 · bears on: Claim 3, Axis B · Fate convergence breaks state-based inference of origin.

> "Third, the cell state transition may undergo rapid divergence with the change of a few molecular drivers, which is challenging to distinguish with transcriptome analysis alone (Wagner et al., 2018; Packer et al., 2019; Tritschler et al., 2019; Wagner and Klein, 2020)."
> — INTRODUCTION / p.1 · bears on: Claim 3, Claim 4, Axis A, Axis B · Transcriptome alone cannot resolve rapid fate divergence driven by a few molecular changes.

> "the ability to infer cell fate transitions for RNA velocity relies on assumptions such as constant gene-specific splicing rates, which may be violated in some situations (La Manno et al., 2018; Svensson and Pachter, 2018; Tritschler et al., 2019; Bergen et al., 2020; Lederer and La Manno, 2020)."
> — INTRODUCTION / p.1 · bears on: Claim 3, Axis B · RNA velocity rests on assumptions that may be violated.

> "although current computation tools may reveal the cell state trajectories by various pseudo-time analysis algorithms, more defined information with the ability to record the cell history is crucial to fully clarify the true path of lineage specification."
> — INTRODUCTION / p.1 · bears on: Claim 3, Axis B · Computational pseudo-time is insufficient; recorded cell history is needed for the true path.

> "recent developments of single-cell lineage tracing, which combines single-cell omics and lineage tracing, enable detecting cell state and clonal relationship in parallel, thereby illustrating a credible route of lineage segregation by integrating the information of the clonal history and state transition."
> — INTRODUCTION / p.1 · bears on: Claim 3, Claim 8, Axis B · Defines SCLT as parallel readout of state + recorded clonal history.

> "SCLT can identify the progenitor-progeny relationship by barcode evolution and define the states of each cell by scRNA-seq, thus enabling the revelation of integrated lineage kinship and molecular trajectory."
> — FROM TRADITIONAL LINEAGE TRACING TO SINGLE-CELL LINEAGE TRACING / p.2 · bears on: Claim 3, Claim 8, Axis B · SCLT couples barcode-recorded lineage with scRNA-seq state.

> "trajectory analysis may fail to recapitulate the true differentiation paths with states alone under certain circumstances. The SCLT method can address this issue by accessing the shared barcodes, which connect cells with states in the early and late developmental stages"
> — Analyzing trajectory directions in state-fate maps / p.5 · bears on: Claim 3, Axis B · "States alone" can fail; recorded barcodes link early and late cells to recover true trajectories.

> "the readout of somatic mutations usually requires costly deep sequencing of the whole genome or exome of single cells, given the low frequency of these somatic mutations and their sparse genomic distribution"
> — BARCODE CLASSIFICATION / p.3 · bears on: Claim 10 · Cost trade-off of endogenous (mutation-based) lineage readout.

> "The current throughput of commercial scRNA-seq platforms (e.g., 10x Genomics) is around 10,000 cells per experiment, but high cost makes it impractical to sequence millions of cells, which may be necessary for organism-level tracing analysis. Insufficient sampling results in the doubt of whether selected cells can represent the whole population, thus affecting the accuracy and completeness of lineage couplings."
> — Recovery rates of cells and barcodes / p.7 · bears on: Claim 10, Claim 1 · Throughput/cost ceiling of scRNA-seq limits sampling completeness.

> "two high throughput scRNA-seq techniques called SPLiT-seq and sci-RNA-seq have enabled the sequencing of millions of cells by labeling them using combinatorial indexing. However, further refinements of their gene detection rates are necessary for accurate downstream analysis (Rosenberg et al., 2018; Cao et al., 2019)."
> — Recovery rates of cells and barcodes / p.7 · bears on: Claim 10 · Throughput-vs-gene-detection trade-off in high-throughput scRNA-seq.

> "invasive barcoding strategies may have latent effects to the behaviors of barcoded cells, which is often difficult to evaluate. For example, CRISPR/Cas9-mediated gene editing could cause DNA double-strand breaks, leading to subsequent p53 activation and even cell death (Haapaniemi et al., 2018; Ihry et al., 2018; Chan et al., 2019), which might alter the lineage routes as well as lose the barcoded cells."
> — Recovery rates of cells and barcodes / p.7 · bears on: Claim 10, Axis B · The measurement/labeling itself perturbs and kills cells, altering what it measures.

> "a proportion of cells may be free of gene editing at the time of sequencing, leading to the loss of lineage information from these cells (Chan et al., 2019)."
> — Recovery rates of cells and barcodes / p.7 · bears on: Claim 10, Axis B · Incomplete recording loses lineage information for some cells.

> "in-house scripts are unfriendly for comparing results between different scenarios."
> — Current computational methods / p.8 · bears on: Claim 9, standard · Non-standardized custom pipelines hinder cross-experiment comparison.

> "Recently, using both ground-truth datasets from a synthetic image-readable lineage recording technology and in silico datasets from simulated recording C. elegans or mouse development, Gong et al. reported systematic evaluations of dozens of methods which were roughly classified into three different groups ... setting a standard for the evaluation of future methods."
> — Current computational methods / p.8 · bears on: Claim 9, standard · Benchmarking against ground-truth to standardize method evaluation.

> "A more practical way is to integrate information from multiple lineage tracing experiments, as the current knowledge of developmental lineages is also assembled from multiple lineage experiments with various techniques."
> — Integration of multiple lineage trees / p.8 · bears on: Claim 8, Claim 9, standard · Knowledge is assembled by integrating many separate experiments.

> "the cell lineage of human development isn't invariant per se due to the stochasticity/plasticity of each cell fate decision (Zechner et al., 2020), making it unrealistic to assemble multiple small lineage trees collectively to create a complete lineage tree in the organismal level."
> — Integration of multiple lineage trees / p.8 · bears on: Claim 9, Axis B · Stochastic/plastic fate decisions make a single complete organismal lineage tree unrealistic to assemble.

> "a statistical framework, LinTiMaT, attempted to resolve lineage ambiguities when integrating different individual lineage trees into a single invariant tree by incorporating gene expression information across different experiments (Zafar et al., 2020; Forrow and Schiebinger, 2021)."
> — Integration of multiple lineage trees / p.8 · bears on: Claim 8, Claim 9, standard · A method to integrate separate lineage trees using cross-experiment expression data.

> "obtaining an accurate and systematic lineage tree of a species remains a challenging task for current practices of SCLT, and new designs are necessary for further improvements."
> — SUMMARY AND PERSPECTIVES / p.8 · bears on: Claim 3, Claim 9, Axis B · Conceded limitation: no accurate systematic species-level lineage tree yet.

> "Recently, the fast development of spatial transcriptomics has shed light on the understanding of the spatial organization of cell types and their lineage relationships"
> — SUMMARY AND PERSPECTIVES / p.8 · bears on: Claim 2, Claim 7, Axis C · Spatial transcriptomics adds spatial organization to lineage understanding.

> "A recent study integrating lineage tracing and spatial transcriptomics has demonstrated that the closely located cells tend to share lineage origins in cerebral organoids (He et al., 2022). This phenomenon may not be shared by the development of neural crest cells and some other long-traveling cells, as their derivatives are spread around the whole organism instead of compact clusters."
> — SUMMARY AND PERSPECTIVES / p.8 · bears on: Claim 7, Axis C · Spatial proximity often tracks lineage origin, but not for migratory cell types — spatial context carries lineage information not recoverable from dissociated cells.

> "the complicated developmental processes may be illustrated by the microscope-based real-time lineage tracing, as this technology can offer valuable information about the cell division number, cell division rate, cell location, cell history, and so on (Denoth-Lippuner et al., 2021; Huang et al., 2021)."
> — SUMMARY AND PERSPECTIVES / p.8 · bears on: Claim 3, Claim 7, Axis B, Axis C · Imaging gives real-time, non-destructive readout of division and location over time (contrast with endpoint sequencing).

> "Anchored by cell's location, combining lineage-information-based spatial transcriptomics and in toto imaging will build a connection between ground-truth cellular history and final molecular interrogation. Future advances to integrate SCLT, spatial multi-omics, and imaging techniques should boost the synthesized studies of animal development and disease modeling in both space and time"
> — SUMMARY AND PERSPECTIVES / p.8 · bears on: Claim 7, Claim 8, Axis B, Axis C, standard · Explicit call to integrate lineage, spatial multi-omics, and imaging across both space and time.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 3 — destructive sequencing can't pairwise-observe time; trajectory inference (Axis B) | "route descriptions of state transitions may or may not be equivalent to the true lineage paths…" / Introduction | supports |
| Claim 3 — RNA velocity / pseudotime assumptions | "RNA velocity relies on assumptions such as constant gene-specific splicing rates, which may be violated…" / Introduction | supports |
| Claim 3 — recorded history vs inferred trajectory | "more defined information with the ability to record the cell history is crucial…" / Introduction; "states alone…fail" / Trajectory directions | supports |
| Axis B — temporal recording method (lineage barcodes) | "SCLT can identify the progenitor-progeny relationship by barcode evolution…" / From traditional to SCLT | supports (with caveat: still endpoint/destructive readout) |
| Claim 4 — transcriptome alone insufficient (Axis A) | "challenging to distinguish with transcriptome analysis alone" / Introduction | supports |
| Claim 10 — resolution × throughput × destructiveness trade-off | "around 10,000 cells per experiment, but high cost makes it impractical…"; "invasive barcoding strategies may have latent effects…p53 activation and even cell death" / Recovery rates | supports |
| Claim 2 / Claim 7 — spatial information lost on dissociation; microenvironment (Axis C) | "closely located cells tend to share lineage origins…"; "spatial organization of cell types and their lineage relationships" / Summary | supports |
| Claim 8 — multimodal/multi-source integration | "combining lineage-information-based spatial transcriptomics and in toto imaging…"; "LinTiMaT…incorporating gene expression information across different experiments" / Summary, Integration of multiple trees | supports |
| Claim 9 — data islands, cross-experiment comparability, lack of standards | "in-house scripts are unfriendly for comparing results between different scenarios"; "setting a standard for the evaluation of future methods" / Computational methods | supports / nuances |
| Axis B — organism-scale completeness | "unrealistic to assemble multiple small lineage trees…to create a complete lineage tree at the organismal level" / Integration of multiple trees | nuances (limit conceded) |
| Axis A — modality breadth | (paper is itself almost exclusively scRNA-seq + DNA barcodes; no protein/metabolite/PTM modality discussed) | — (paper exemplifies RNA-centric scope; makes no modality-breadth claim) |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Barcode-based SCLT schemes: (A) Cre-LoxP vs DNA-barcode labeling; (B) integration barcodes; (C) polylox barcodes; (D) CRISPR barcodes incl. inter-site deletion; (E) base-editing barcodes. |
| Fig. 2 | SCLT applications: static vs cumulative barcodes; lineage-coupling metrics; trajectory direction from state+clonal info; subgrouping similar cells by clone; inferring division-tree parameters; population-level mathematical models. |
| Fig. 3 | Technical considerations: timing/modes of barcoding (early/intermediate/late/continuous); experimental capture workflow; clonal-analysis algorithms; multiple-tree integration by cell type. |
| Fig. 4 | Integrating technologies: (A) imaging vs sequencing methods across space/time; (B) organoid vs in vivo models. |
| Number | Commercial scRNA-seq (10x Genomics) throughput "around 10,000 cells per experiment"; millions of cells "may be necessary for organism-level tracing." |

---

## Primary Sources Behind Key Quotes
- Trajectory-inference limitations / pseudotime comparison → Saelens W, Cannoodt R, Todorov H, Saeys Y (2019) Nat Biotechnol 37:547–554 (ref list).
- RNA velocity (original + violated assumptions) → La Manno G et al. (2018) Nature 560:494–498 (ref list); Bergen V et al. (2020) Nat Biotechnol 38:1408–1414.
- Lineage tracing links state to fate (dissociated snapshot critique) → Weinreb C, Rodriguez-Fraticelli A, Camargo FD, Klein AM (2020) Science 367:eaaw3381.
- SCLT + spatial transcriptomics, proximity ~ lineage in cerebral organoids → He Z et al. (2022) Nat Methods 19:90–99.
- Integrating lineage trees with expression (LinTiMaT) → Zafar H, Lin C, Bar-Joseph Z (2020) Nat Commun 11:3055; LineageOT → Forrow A, Schiebinger G (2021) Nat Commun 12:4940.
- High-throughput scRNA-seq (combinatorial indexing) → Rosenberg AB et al. (2018) Science 360:176–182 (SPLiT-seq); Cao J et al. (2019) Nature 566:496–502 (sci-RNA-seq).
- CRISPR editing → p53 activation / cell death → Haapaniemi E et al. (2018) Nat Med 24:927–930; Ihry RJ et al. (2018) Nat Med 24:939–946.
- Benchmark of lineage-reconstruction methods → Gong W et al. (2021) Cell Syst 12(8):810–826.

---

## Flags
- [ ] Metadata unverified — Journal/Venue: the body prints only "REVIEW", "Received December 3, 2021 / Accepted March 6, 2022", and a CC-BY OPEN ACCESS notice; no journal name, volume, issue, or page numbers appear in the cleaned text. Format (REVIEW / KEYWORDS / ABBREVIATIONS / DECLARATIONS / OPEN ACCESS), corresponding author at GIBH (Guangdun Peng), and dates are consistent with *Protein & Cell* (2022) but this is NOT confirmed from the source text — do not cite the venue without checking the DOI/publisher record.
- [ ] Metadata unverified — DOI not present in the cleaned text (`grep '10.[0-9]{4,}/'` returned nothing). Resolve before citing.
- [ ] Reconstructed (NOT in source text): none — author names are printed in full in the "Authors" block (Cheng Chen, Yuanxin Liao, Guangdun Peng); not reconstructed from initials.
- [ ] Read at source: for our temporal-axis argument, prefer first-hand reading of (a) Saelens et al. 2019 Nat Biotechnol 37:547 and La Manno et al. 2018 Nature 560:494 for the trajectory/RNA-velocity critique; (b) Weinreb et al. 2020 Science 367:eaaw3381 for state-to-fate via lineage; (c) He et al. 2022 Nat Methods 19:90 for lineage + spatial transcriptomics. This review is a secondary aggregator of those primary results.
- [ ] Page numbers are approximate (printed page numbers absent from cleaned text; "p.X" labels above are sequential-section estimates, not the article's true pagination).
- [ ] Scope note: most of the paper details barcode chemistry/design (integration vs polylox vs CRISPR vs base-editing) and library-diversity figures (e.g., polylox ~1.8 million barcodes). These are method internals, off the data-standard roadmap, and were deliberately NOT captured. Only lines bearing on temporal/spatial/integration/trade-off claims were extracted.
