# A comparison of single-cell trajectory inference methods — Source Index

**Authors:** Wouter Saelens, Robrecht Cannoodt, Helena Todorov, Yvan Saeys (Saelens and Cannoodt share superscript 6 — see Flags; Saeys is corresponding author, superscript *)
**Journal / Venue:** Nature Biotechnology, 2019 — venue inferred from DOI prefix and Nature Research reporting summary; exact volume/issue/pages not printed in the cleaned text (see Flags)
**DOI:** doi:10.1038/s41587-019-0071-9 (article); data deposited at doi:10.5281/zenodo.1443566
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/26_cleaned.md

---

## In One Sentence
The paper benchmarks 45 single-cell trajectory inference (TI / pseudotime) methods on 110 real and 229 synthetic datasets across four axes — accuracy, scalability, stability and usability — and finds no single best method, strong dependence of performance on trajectory topology, generally poor scalability, and a pervasive lack of standardized input/output interfaces.

## Orientation (non-binding)
This is the canonical benchmark of computational trajectory inference — the exact class of "reconstruct order/time from a static expression snapshot" methods our thesis invokes when arguing that destructive sequencing cannot pair-observe a single cell over time. It most likely feeds **Claim 3 / Axis B (temporal)** (time is computationally inferred, not observed) and **Claim 9 / standard axis** (no common format, cross-method incomparability), and secondarily **Claim 1** (benchmark-driven critique of generalization). It can serve BOTH as support (it demonstrates the field's reliance on inference and openly concedes that inference is variable, prior-dependent and topology-dependent) AND as a foil (it is itself a constructive standardization effort, not a critique of the snapshot paradigm). The downstream agent decides.

---

## Load-Bearing Excerpts

> "Trajectory inference approaches analyze genome-wide omics data from thousands of single cells and computationally infer the order of these cells along developmental trajectories."
> — Abstract · bears on: Claim 3, Axis B · states that cell order along a trajectory is computationally inferred, not directly measured.

> "Although more than 70 trajectory inference tools have already been developed, it is challenging to compare their performance because the input they require and output models they produce vary substantially."
> — Abstract · bears on: Claim 9, standard axis · the proliferation of tools with heterogeneous inputs/outputs makes cross-method comparison hard.

> "Our results highlight the complementarity of existing tools, and that the choice of method should depend mostly on the dataset dimensions and trajectory topology."
> — Abstract · bears on: Claim 1, Claim 3 · method outcome is not unique; it depends on dataset and assumed topology.

> "Such dynamic processes can be modeled computationally using trajectory inference (TI) methods, also called pseudotime analysis, which order cells along a trajectory based on similarities in their expression patterns."
> — Introduction · bears on: Claim 3, Axis B · defines TI/pseudotime as ordering cells by expression similarity (a snapshot), i.e. inferred rather than observed time.

> "TI methods offer an unbiased and transcriptome-wide understanding of a dynamic process, thereby allowing the objective identification of new (primed) subsets of cells, delineation of a differentiation tree and inference of regulatory interactions responsible for one or more bifurcations."
> — Introduction · bears on: Claim 4, Axis A (modality) · the dynamic understanding claimed is "transcriptome-wide," i.e. centered on RNA expression.

> "Single-cell omics data, including transcriptomics, proteomics and epigenomics data, provide new opportunities for studying cellular dynamic processes, such as the cell cycle, cell differentiation and cell activation."
> — Introduction (opening) · bears on: Claim 4, Axis A · lists the modalities in principle available; in practice the benchmark is transcriptomic.

> "We found that method performance was very variable across datasets, indicating that there is no 'one-size-fits-all' method that works well on every dataset"
> — Results, Accuracy · bears on: Claim 1, Claim 3 · no method generalizes across all datasets.

> "The performance of a method was strongly dependent on the type of trajectory present in the data"
> — Results, Accuracy · bears on: Claim 1, Claim 3 · accuracy is contingent on the (often unknown) underlying topology.

> "This analysis therefore indicates that detecting the right topology is still a difficult task for most of these methods, because methods tend to be either too optimistic or too pessimistic regarding the complexity of the topology in the data."
> — Results, Accuracy · bears on: Claim 3, Axis B · inferring the correct trajectory structure remains unreliable.

> "On all datasets, using one method resulted in getting a top model about 27% of the time. This increased up to 74% with the addition of six other methods"
> — Results, Accuracy (complementarity) · bears on: Claim 1, Claim 3 · a single method reaches a near-best result only ~27% of the time; seven methods are needed for ~74%.

> "Altogether, this shows that there is considerable complementarity between the different methods and that users should try out a diverse set of methods on their data, especially when the topology is unclear a priori."
> — Results, Accuracy · bears on: Claim 1, Claim 3 · a single inferred trajectory is not trustworthy on its own.

> "Real datasets were classified as 'gold standard' if the reference trajectory was not extracted from the expression data itself, such as via cellular sorting or cell mixing. All other real datasets were classified as 'silver standard.'"
> — Results, Accuracy · bears on: Claim 3, Claim 9 · a true (non-expression-derived) reference trajectory is rare; most "ground truth" is itself derived from the expression data being tested.

> "While early TI methods were developed at a time where profiling more than a thousand cells was exceptional, methods now have to cope with hundreds of thousands of cells, and perhaps soon with more than ten million."
> — Results, Scalability · bears on: Claim 10 · cell numbers are growing by orders of magnitude (computational scaling pressure).

> "Moreover, the recent application of TI methods on multi-omics single-cell data also showcases the increasing demands on the number of features."
> — Results, Scalability · bears on: Claim 4, Claim 8 · multi-omics single-cell data raises the feature dimension TI must handle.

> "We found that the scalability of most methods was overall very poor, with most graph and tree methods not finishing within an hour on a dataset with ten thousand cells and ten thousand features"
> — Results, Scalability · bears on: Claim 10 · most methods do not scale to a typical droplet-scale dataset within an hour.

> "We found that more than half of all methods had a quadratic or superquadratic complexity with respect to the number of cells, which would make it difficult to apply any of these methods in a reasonable time frame on datasets with more than a thousand cells"
> — Results, Scalability · bears on: Claim 10 · over half of methods scale quadratically-or-worse in cell count.

> "it is critical that a trajectory, and the downstream results and/or hypotheses originating from it, are confirmed by multiple TI methods. This is to make sure that the prediction is not biased due to the given parameter setting or the particular algorithm underlying a TI method."
> — Discussion · bears on: Claim 3, Claim 1 · an inferred trajectory is parameter- and algorithm-dependent and must be cross-confirmed.

> "Critical to the broad applicability of TI methods is the standardization of the input and output interfaces of TI methods, so that users can effortlessly execute TI methods on their dataset of interest, compare different predicted trajectories and apply downstream analyses"
> — Discussion · bears on: Claim 9, standard axis · names standardization of input/output interfaces as the bottleneck to applicability and comparison.

> "In the future, this framework could be extended to allow additional input data, such as spatial and RNA velocity information, and easier downstream analyses."
> — Discussion · bears on: Claim 2, Axis C (spatial), Claim 3 · concedes that current TI does not use spatial information; flags spatial and RNA-velocity data as future inputs.

> "further discussion within the field is required to arrive at a consensus concerning a common interface for trajectory models, which can include additional features such as uncertainty and gene importance."
> — Discussion · bears on: Claim 9, standard axis · no consensus common interface yet exists; one is needed.

> "Foremost, new methods should focus on improving the unbiased inference of tree, cyclic graph and disconnected topologies, as we found that methods repeatedly overestimate or underestimate the complexity of the underlying topology, even if the trajectory could easily be identified using a dimensionality reduction method"
> — Discussion · bears on: Claim 3, Axis B · methods systematically misjudge trajectory complexity, even when structure is visually evident.

> "Providing prior information to a TI method can be both a blessing and a curse. In one way, prior information can help the method to find the correct trajectory among many, equally likely, alternatives. On the other hand, incorrect or noisy prior information can bias the trajectory towards current knowledge. Moreover, prior information is not always easily available, and its subjectivity can therefore lead to multiple equally plausible solutions, restricting the applicability of such TI methods to well-studied systems."
> — Methods, Method input · bears on: Claim 3, Claim 9 · TI often needs user-supplied priors (e.g. a start cell); these bias the result toward prior knowledge and yield multiple plausible solutions.

> "Due to the absence of a common format for trajectory models, most methods return a unique set of output formats with few overlaps."
> — Methods, Common trajectory model · bears on: Claim 9, standard axis · explicit statement that no common trajectory-model format exists across methods.

> "Discrete time course: for each cell a time point from which it was sampled. If available, this was directly extracted from the reference trajectory; otherwise the geodesic distance from the root milestone was used."
> — Methods, Method input · bears on: Claim 3, Axis B · when a real sampling time per cell is unavailable, an inferred geodesic distance substitutes for time — i.e. pseudotime stands in for observed time.

> "Installation issues seem to be quite general in bioinformatics and the trajectory inference field is no exception."
> — Results, Usability · bears on: Claim 9 · reproducibility/usability frictions are pervasive, reinforcing the standards gap.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data/benchmark bottleneck, weak generalization | "method performance was very variable… no 'one-size-fits-all'" / Accuracy; "27% … 74% with … six other methods" / Accuracy | supports |
| Claim 2 / Axis C — scRNA-seq loses spatial information | "could be extended to allow additional input data, such as spatial … information" / Discussion | supports |
| Claim 3 / Axis B — destructive sequencing can't pair-observe time → trajectory inference | "computationally infer the order" / Abstract; "pseudotime analysis, which order cells … by … similarities in their expression patterns" / Intro; "otherwise the geodesic distance … was used" / Methods | supports |
| Claim 4 / Axis A — modalities are orthogonal; RNA-only is narrow | "transcriptome-wide understanding" / Intro; "transcriptomics, proteomics and epigenomics" / Intro | nuances |
| Claim 8 — multi-modal data needs integration | "application of TI methods on multi-omics single-cell data … increasing demands on the number of features" / Scalability | nuances |
| Claim 9 / standard axis — data islands, cross-study incomparability, no standard | "absence of a common format for trajectory models" / Methods; "standardization of the input and output interfaces" / Discussion; "challenging to compare … input … and output … vary substantially" / Abstract | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "hundreds of thousands of cells, and perhaps soon … ten million" / Scalability; "scalability of most methods was overall very poor" / Scalability | nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Scope | 45 TI methods evaluated, selected from a gathered list of 71 tools (Supplementary Table 1). |
| Data compendium | 110 real datasets + 229 synthetic datasets; real split into "gold" vs "silver" standard references. |
| Evaluation axes | Four: accuracy, scalability, stability, usability (Fig. 2b, Fig. 3). |
| Topology taxonomy | Seven trajectory types, from linear/cyclic (simplest) to connected/disconnected graphs (Fig. 1c, Fig. 2a). |
| Accuracy metrics | Four: HIM (topology), F1_branches (branch assignment), cor_dist (cell positions), wcor_features (important features). |
| Complementarity | One method = a "top model" (≥95% of best score) ~27% of datasets; rising to ~74% with six additional methods (Fig. 4a). |
| Scalability | Most graph/tree methods do not finish within 1 h on 10,000 cells × 10,000 features; only PAGA, PAGA Tree, Monocle DDRTree, Stemnet, GrandPrix complete within a day on 1,000,000 cells; >half of methods are quadratic/superquadratic in cell count. |
| Compute limits | Per-run cap: >1 h time limit and 16 GB (Methods: Method execution) / 10 GB (Scalability) memory; exceeding either returns a zero score. |

---

## Primary Sources Behind Key Quotes
- Spatial / RNA velocity as future TI input (the "RNA velocity" half) → Manno, G. L. et al. RNA velocity of single cells. Nature 560, 494–498 (2018) — ref 45.
- Multi-omics single-cell data raising feature demands → Cao, J. et al. Joint profiling of chromatin accessibility and gene expression in thousands of single cells. Science 361, 1380–1385 (2018) — ref 38.
- Cell numbers scaling toward millions → Svensson, V., Vento-Tormo, R. & Teichmann, S. A. Exponential scaling of single-cell RNA-seq in the past decade. Nat. Protoc. 13, 599–604 (2018) — ref 37.
- "Gold standard" reference via cell mixing → Tian, L. et al. scRNA-seq mixology: Towards better benchmarking of single cell RNA-seq protocols and analysis methods. Preprint at bioRxiv https://doi.org/10.1101/433102 (2018) — ref 34.

---

## Flags
- [ ] Metadata unverified — venue/volume/pages: The journal name "Nature Biotechnology" is inferred from the DOI prefix (s41587 = Nat. Biotechnol.) and the "Nature Research Reporting Summary" in the body; it is NOT printed verbatim in the cleaned text, and no volume/issue/page range appears. Do not cite a volume/page from this note without checking the published article.
- [ ] Reconstructed (NOT in source text): Co-first authorship of Saelens and Cannoodt is inferred from their shared superscript "6"; the text does not state "equal contribution" verbatim. Corresponding author Y. Saeys is marked by superscript "*" and the line "Correspondence and requests for materials should be addressed to Y.S."
- [ ] Page numbers: The cleaned MD carries no print page numbers; provenance anchors above use the paper's own section names (Abstract / Introduction / Results: Accuracy, Scalability, Stability, Usability / Discussion / Methods).
- [ ] Read at source: For the spatial and temporal axes, the primary methods this paper only gestures at are worth first-hand reading — RNA velocity (Manno et al., Nature 2018, ref 45) and the multi-omics single-cell work (Cao et al., Science 2018, ref 38). This benchmark does not itself implement spatial or velocity-based inference.
- [ ] Source inconsistency / OCR noise: The cleaned text contains OCR artifacts (e.g. "Te" for "The", "diferentiation", "sofware", "fndings", garbled cells in the Reporting Summary tables). Quotes above were transcribed as they appear; verify exact wording against the published PDF before quoting in print.
- [ ] Scope note: Detailed per-method rankings, metric mathematics (HIM/F1/cor/wcor), the seven output-conversion types, usability scoring scheme, and method-development guidelines were judged off-roadmap (our perspective argues "what data a virtual cell needs," not how to build/rank TI methods) and were intentionally not captured beyond the factual numbers table.
