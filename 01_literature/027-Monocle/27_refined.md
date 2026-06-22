# The dynamics and regulators of cell fate decisions are revealed by pseudotemporal ordering of single cells — Source Index

**Authors:** Cole Trapnell, Davide Cacchiarelli, Jonna Grimsby, Prapti Pokharel, Shuqiang Li, Michael Morse, Niall J Lennon, Kenneth J Livak, Tarjei S Mikkelsen & John L Rinn
**Journal / Venue:** unverified; see Flags
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/27_cleaned.md

---

## In One Sentence
The paper introduces Monocle, an unsupervised algorithm that takes single-cell RNA-Seq snapshots of an asynchronous, dissociated cell population (here, differentiating primary human myoblasts captured at four real time points) and computationally orders the cells along an inferred "pseudotime" trajectory — increasing temporal resolution of transcriptional dynamics, resolving branched lineages, and recovering early/late regulatory events (e.g., the ID1/MYOG switch) and eight previously unappreciated transcription-factor regulators that bulk and time-collected analyses miss.

## Orientation (non-binding)
This is the canonical trajectory-inference / pseudotime method and feeds the context's **temporal axis (Axis B)** and **claim 3 (destructive/snapshot sequencing cannot observe the same cell pairwise over real time)** most directly. Its premise is exactly the constraint our thesis names: because you capture a snapshot of an unsynchronized population and cannot follow one cell over time, you *reconstruct an inferred ordering* ("pseudotime — progress... rather than time") instead of a real trajectory. It can therefore serve BOTH as evidence that the field resorts to computational time-inference because the data lacks real time, AND as a named "workaround" our perspective contrasts against true temporal/paired measurement. Secondary touchpoints: it is a transcriptome-only assay (Axis A / claim 4 — modality narrowness, with an explicit aspiration toward same-cell multi-modal measurement) and it concedes that spatial positioning/cell contact shapes fate yet is discarded by dissociation (Axis C / claims 2, 7). The downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "Defining the transcriptional dynamics of a temporal process such as cell differentiation is challenging owing to the high variability in gene expression between individual cells."
> — Abstract · bears on: claim 3, Axis B (temporal) · states that resolving temporal dynamics is hard because of cell-to-cell variability.

> "Time-series gene expression analyses of bulk cells have difficulty distinguishing early and late phases of a transcriptional cascade or identifying rare subpopulations of cells, and single-cell proteomic methods rely on a priori knowledge of key distinguishing markers"
> — Abstract · bears on: claim 3, claim 10 (trilemma / bulk-vs-single-cell), claim 4 / Axis A (modality) · contrasts limitations of bulk time-series and of marker-dependent single-cell proteomics.

> "Here we describe Monocle, an unsupervised algorithm that increases the temporal resolution of transcriptome dynamics using single-cell RNA-Seq data collected at multiple time points."
> — Abstract · bears on: claim 3, Axis B, Axis A · introduces the method as a transcriptome-only temporal-resolution tool.

> "Thus individual cells can execute the same sequence of transcriptional changes over highly varying time scales."
> — Main text (introduction) · bears on: claim 3, Axis B · real elapsed time and biological progress are decoupled across cells.

> "As a population of cells captured at the same time may include many distinct intermediate differentiation states, considering only its average properties would mask trends occurring across individual cells."
> — Main text (introduction) · bears on: claim 3, claim 10 · a single real-time snapshot mixes many states, so averages distort dynamics.

> "Solving this problem by experimental synchronization of cells or by stringent isolation of precursors at distinct stages is challenging and can sharply alter differentiation kinetics."
> — Main text (introduction) · bears on: claim 3, claim 10, Axis B · the experimental route to clean time-resolved data perturbs the very kinetics being measured.

> "However, because these algorithms operate on bulk expression measurements, they are sensitive to mixture effects arising from Simpson's paradox and other averaging artifacts."
> — Main text (introduction) · bears on: claim 10 (bulk vs single-cell resolution), claim 3 · bulk-based ordering methods are corrupted by population averaging.

> "Coupled with SPADE, cytometry can track changes in up to 32 proteins to reconstruct complex cellular hierarchies of differentiation and reveal rare cell states."
> — Main text (introduction) · bears on: claim 4 / Axis A (protein modality), claim 10 · notes a contemporary protein-level single-cell approach limited to ~32 proteins.

> "In principle, single-cell RNA-Seq could also be used to resolve cellular transitions during differentiation through temporal profiling of the entire transcriptome."
> — Main text (introduction) · bears on: claim 3, Axis B, Axis A · positions whole-transcriptome scRNA-Seq as a basis for inferring temporal transitions.

> "We hypothesized that ordering whole-transcriptome profiles of single cells with an unsupervised algorithm would improve temporal resolution during differentiation without a priori knowledge of marker genes. In essence, one RNA-Seq experiment would constitute a time series, with each cell representing a distinct time point along a continuum."
> — Main text · bears on: claim 3, Axis B · core idea: a single static snapshot is reinterpreted as a time series via inferred ordering.

> "Monocle orders single-cell expression profiles in 'pseudotime'—a quantitative measure of progress through a biological process."
> — Main text · bears on: claim 3, Axis B · defines pseudotime as inferred progress, not measured elapsed time.

> "We speculated that the high variability in cell-to-cell gene expression levels was due to unsynchronized differentiation, with myoblasts, intermediate myocytes and mature myotubes residing in the same well."
> — Main text (results) · bears on: claim 3, claim 10 · cells at one real time point span multiple differentiation states.

> "We captured between 49 and 77 cells at each of four time points after the switch to DM using the Fluidigm C1 microfluidic system."
> — Main text (results) · bears on: claim 3, claim 10 · experimental scale: snapshot capture at four real time points.

> "A total of 1,061 genes were dynamically regulated during differentiation (false discovery rate (FDR) < 5%; Fig. 2c)."
> — Main text (results) · bears on: claim 3, Axis B · quantitative output of pseudotime-based dynamic-gene detection.

> "In contrast to the high resolution of pseudotime ordering, simply comparing gene expression levels between groups of cells collected on different days masked changes in key transcriptional regulators of myogenesis."
> — Main text (results) · bears on: claim 3, claim 10 · ordering by real collection time loses signal that pseudotime recovers.

> "Monocle placed subsets as small as 50 cells in pseudotemporal order highly similar (Spearman ≥ 0.8) to their relative order in the full data set. The algorithm retained the ability to detect dynamically regulated genes with high precision (≥95%) over all designs and with increasing recall as more of the cells were included"
> — Main text (results) · bears on: claim 3, Axis B · robustness/quantitative benchmark of the inferred ordering.

> "A time-series analysis of myoblast differentiation with bulk RNA-Seq identified up- and downregulated genes but did not identify the transient clusters or distinguish the early from late regulation visible with pseudotemporally ordered single cells"
> — Main text (results) · bears on: claim 10 (bulk vs single-cell), claim 3 · bulk time-series loses temporal structure recoverable from single cells.

> "Furthermore, dynamic range of expression was compressed for most genes, confirming that failure to account for variability in progress through differentiation leads directly to the effects associated with Simpson's paradox. Pseudotemporal cell ordering thus decomposes the coarse kinetic trends produced by bulk RNA-Seq into distinct, sequential waves of transcriptional reconfiguration."
> — Main text (results) · bears on: claim 10, claim 3 · names the averaging artifact bulk measurement introduces and what single-cell ordering recovers.

> "This pseudotime ordering pinpoints key events in differentiation, such as the ID1/MYOG switch, that are masked both by conventional bulk cell expression profiling and by single-cell expression profiles ordered by time collected."
> — Discussion · bears on: claim 3, claim 10, Axis B · real collection-time ordering is insufficient; inferred ordering exposes hidden events.

> "Sequencing-based measurements of small RNAs and mRNAs from the same cell will provide answers to such systems-level questions."
> — Discussion · bears on: claim 4 / Axis A (modality), claim 8 (multi-modal integration) · aspiration toward joint multi-modal measurement from the same cell.

> "Moreover, single-cell analysis distinguishes cells of interest from contaminating cell types such as interstitial mesenchymal cells without experimental isolation that might disrupt cell-cell interactions important in the in vivo niche."
> — Discussion · bears on: claim 7 (microenvironment / niche), claim 2 / Axis C (spatial) · concedes cell-cell interactions in the in vivo niche matter and can be disrupted by isolation.

> "Monocle thus enabled analysis of the myoblast differentiation trajectory without subtracting these cells by immunopurification, maintaining in vitro differentiation kinetics that resemble physiological cell crosstalk occurring in the in vivo niche."
> — Main text (results) · bears on: claim 7, claim 2 / Axis C · frames cell crosstalk / niche context as biologically important, though the assay is dissociated.

> "even cells in a genetically and epigenetically clonal population might progress through differentiation at different rates in vitro, depending on positioning and physical contact with neighboring cells. Looking at average behavior in a group of cells is thus not necessarily faithful to the process through which an individual cell transits."
> — Online Methods (The single cell ordering problem) · bears on: claim 7 (spatial neighborhood effect), claim 3, claim 10 · spatial positioning / neighbor contact modulates fate progression — yet dissociated assays discard it.

> "Moreover, two cells might transit through a different sequence of intermediate stages and ultimately converge on the same end state."
> — Online Methods (The single cell ordering problem) · bears on: claim 3, Axis B · acknowledges path heterogeneity that snapshot data cannot follow per-cell.

> "Each point in the image of the function is the state of the cell at s, which can be thought of as progress through the biological process, rather than time. That is, two cells might execute exactly the same sequence of changes as they differentiate but take different amounts of time to do so."
> — Online Methods (The single cell ordering problem) · bears on: claim 3, Axis B · explicit statement that pseudotime measures progress, NOT elapsed/real time.

> "This 'pseudotemporal' scale of differentiation is numerically arbitrary and will of course vary from experiment to experiment, but nevertheless is useful for downstream analysis."
> — Online Methods (The single cell ordering problem) · bears on: claim 3, claim 9 (cross-experiment comparability), Axis B · concedes pseudotime is arbitrary and experiment-dependent — not an absolute, comparable time axis.

> "We have found that selecting genes that are differentially expressed between groups of cells collected at different real times allows robust ordering ... However, in some experiments this might not be available (for example, because all the cells came from a single tissue or time point). In these cases, we recommend selecting genes on the basis of a minimum expression level and a minimum level of variance."
> — Online Methods (Dimensionality reduction) · bears on: claim 3, Axis B · ordering can be derived even from a single time point — i.e., real time is not required to produce a pseudotemporal axis.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 3 — destructive/snapshot seq cannot observe time pairwise | "one RNA-Seq experiment would constitute a time series..." / Main text | supports |
| Claim 3 — pseudotime is inferred, not real time | "...progress through the biological process, rather than time" / Online Methods | supports (names the workaround) |
| Claim 3 — pseudotime axis is arbitrary / experiment-dependent | "...numerically arbitrary and will of course vary from experiment to experiment" / Online Methods | supports / nuances |
| Axis B — temporal | "increases the temporal resolution of transcriptome dynamics" / Abstract | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "...sensitive to mixture effects arising from Simpson's paradox" / Main text | supports |
| Claim 10 — bulk vs single-cell averaging | "bulk RNA-Seq ... did not identify the transient clusters" / Main text | supports |
| Claim 4 / Axis A — modality narrowness (RNA-only paradigm) | "...temporal profiling of the entire transcriptome" / Main text | supports (exemplar) |
| Claim 4 / Claim 8 — need same-cell multi-modal | "small RNAs and mRNAs from the same cell" / Discussion | supports |
| Claim 2 / Axis C — spatial info lost by dissociation | "...disrupt cell-cell interactions important in the in vivo niche" / Discussion | nuances |
| Claim 7 — microenvironment / neighbor effect on cell state | "...depending on positioning and physical contact with neighboring cells" / Online Methods | supports |
| Claim 9 — cross-experiment comparability / standards | "...vary from experiment to experiment" / Online Methods | nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Workflow: primary human myoblasts cultured in high-serum, switched to low-serum, dissociated and individually captured at 24-h intervals; per-cell RNA-Seq. Confirms single-cell averages correlate with bulk RNA-Seq (n=3); shows temporal heterogeneity of late markers (ENO3, MYH3); immunofluorescence (MEF2C, MYH2). |
| Fig. 2 | Monocle pipeline + results: ICA two-dimensional space with MST and main diameter path (pseudotime backbone); heatmap of differentially expressed genes (cells in pseudotime order); MEF2C vs MYH2 expressing-cell proportions by IF, RNA-Seq at collection time, and RNA-Seq at pseudotime; CDK1/ID1/MYOG ordered by collection time vs pseudotime. |
| Fig. 3 | K-medioid clustering of pseudotemporal expression into six trends; selected GO terms (enrichment as −log10(q)); counts of transcription factors with conserved binding-site motifs per cluster, segregated by regulatory-element function. |
| Fig. 4 | Loss-of-function shRNA screen: fraction of nuclei in MYH2+ cells, whole-well MYH2 area, nuclei counts (normalized to mock); co-occupancy scores of conserved TF binding motifs in enhancers/promoters; two proposed inhibitor mechanisms. |
| Key numbers | 49–77 cells per time point at 0/24/48/72 h; ~4 million reads per single-cell library (10–20 million per bulk TruSeq library); 1,061 dynamically regulated genes (FDR < 5%); robust ordering down to 50-cell subsets (Spearman ≥ 0.8), precision ≥95%; six pseudotemporal gene clusters; 175 transcription factors with enriched motifs near upregulated genes; RNAi screen of 11 candidates / 44 shRNAs; 8 previously unappreciated TF regulators (MZF1, ZIC1, XBP1, USF1, CUX1, ARID5B, POU2F1, AHR). |
| Data accession | GEO: GSE52529. Monocle source at http://monocle-bio.sourceforge.net/ |

---

## Primary Sources Behind Key Quotes
- Pseudotime / curve-reconstruction algorithm Monocle extends → Magwene, P.M., Lizardi, P. & Kim, J. "Reconstructing the temporal ordering of biological samples using microarray data." Bioinformatics 19, 842–850 (2003). [ref 10]
- Simpson's paradox (averaging artifact) → Simpson, E.H. "The interpretation of interaction in contingency tables." J. R. Stat. Soc. Series B 13, 238–241 (1951). [ref 8]
- Single-cell mass cytometry / hematopoietic continuum (protein-level single-cell) → Bendall, S.C. et al. Science 332, 687–696 (2011). [ref 1]
- SPADE (cellular hierarchy from cytometry) → Qiu, P. et al. Nat. Biotechnol. 29, 886–891 (2011). [ref 13]
- High cell-to-cell variability in single-cell expression → Shalek, A.K. et al. Nature 498, 236–240 (2013) [ref 2]; Guo, G. et al. Dev. Cell 18, 675–685 (2010) [ref 3]; Buganim, Y. et al. Cell 150, 1209–1222 (2012) [ref 5]; Tang, F. et al. Cell Stem Cell 6, 468–478 (2010) [ref 6].

---

## Flags
- [ ] Metadata unverified: Journal/venue and year are NOT stated anywhere in the cleaned source text; the body, acknowledgments, and reference list never self-cite this paper's own venue. Externally this is widely known as Nature Biotechnology, 2014 (Monocle paper), but that is reconstructed, not confirmed from the file — do not cite as fact without checking the original.
- [ ] Metadata unverified: DOI not present in source text. The only DOI string found by grep (`10.1096/fj.03-0568fje`) belongs to reference 16 (Tomczak, FASEB J.), NOT to this paper. The commonly cited DOI for this paper (10.1038/nbt.2859) is external knowledge, not in the file.
- [ ] Reconstructed (NOT in source text): none for author names — full first names ARE printed in the "Authors" block (line 317), so no initials were guessed.
- [ ] Read at source: Magwene et al. 2003 (Bioinformatics 19:842–850, ref 10) is the foundational temporal-ordering / curve-reconstruction method Monocle builds on — worth reading first-hand for the trajectory-inference lineage. Bendall et al. 2011 (ref 1) and Qiu et al. 2011 SPADE (ref 13) are the primary single-cell cytometry trajectory antecedents.
- [ ] Source inconsistency: reference list in the cleaned file is interleaved out of order (refs 10, 12–25 appear mid-body before Online Methods; refs 26–42 appear after Online Methods) and references 11 is not separately shown; numbering is otherwise internally consistent. No content affected for the quotes captured above.
- [ ] Scope note: figure-level biological detail (specific myogenic TFs, ID1/MYOG switch mechanism, RNAi mechanism models) is largely off the perspective's roadmap; captured only where it demonstrates the temporal/bulk-vs-single-cell point. Method math (PQ-tree, ICA, GAM/Tobit equations) is out of scope and not quoted.
