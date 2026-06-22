# Optimal-Transport Analysis of Single-Cell Gene Expression Identifies Developmental Trajectories in Reprogramming — Source Index

**Authors:** Geoffrey Schiebinger, Jian Shu, Marcin Tabaka, Brian Cleary, Vidya Subramanian, Aryeh Solomon, Joshua Gould, Siyan Liu, Stacie Lin, Peter Berube, Lia Lee, Jenny Chen, Justin Brumbaugh, Philippe Rigollet, Konrad Hochedlinger, Rudolf Jaenisch, Aviv Regev, and Eric S. Lander
**Journal / Venue:** Cell, 2019 (volume/issue/pages not printed in source; see Flags)
**DOI:** doi:10.1016/j.cell.2019.01.006
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/21 - Waddington-OT - Optimal-Transport Analysis Developmental Trajectories in Reprogramming_cleaned.md

---

## In One Sentence
The paper introduces Waddington-OT, an optimal-transport method that infers ancestor–descendant couplings from a dense scRNA-seq time course (≈315,000 cells over 18 days of iPSC reprogramming), reconstructs branching developmental trajectories and the TFs/paracrine signals driving them, and experimentally validates that TF Obox6 and cytokine GDF9 enhance reprogramming efficiency.

## Orientation (non-binding)
Most directly feeds Claim 3 (destructive sequencing cannot pair the same cell across time) and Axis B (temporal): it is itself the canonical "Waddington-OT class" reference the context file names, and it states the destructive-measurement constraint and the "distribution-to-distribution" workaround in explicit prose. It can serve BOTH as support (a leading example of why time must be inferred, not observed) AND as a foil (a high-profile, RNA-only, dissociated dataset where space is absent and cell-cell interaction must be inferred from co-expression rather than measured in situ). Secondary touchpoints: Claim 10 (resolution × throughput × destructiveness trade-off), Claims 1/9 (method incomparability / many trajectory tools fail), Claim 7 + Axis C (paracrine/microenvironment effects, here inferred without spatial data).

---

## Load-Bearing Excerpts

> "Because scRNA-seq destroys cells in the course of recording their profiles, one cannot follow expression of the same cell and its direct descendants across time. While various approaches can record information about cell lineage, they currently provide only very limited information about a cell’s state at earlier time points (Kester and van Oudenaarden, 2018)."
> — Introduction · bears on: Claim 3, Axis B, Claim 10 · states that destructive measurement prevents tracking the same cell over time, and that lineage-tracing methods do not recover ancestral expression state.

> "The first challenge has been largely solved by the advent of single-cell RNA sequencing (scRNA-seq) (Tanay and Regev, 2017). The second remains a work-in-progress."
> — Introduction · bears on: Claim 3, Axis B · distinguishes discovering cell classes (solved) from tracing each class's development over time (unsolved).

> "Comprehensive studies of cell trajectories thus rely heavily on computational approaches to connect discrete ‘‘snapshots’’ into continuous ‘‘movies.’’"
> — Introduction · bears on: Claim 3, Axis B, Claim 10 · time-course biology must reconstruct continuous dynamics computationally from disjoint static samples.

> "First, with few exceptions, most methods do not explicitly leverage temporal information (Table S6). Historically, most were designed to extract information about stationary processes, such as adult stem cell differentiation, in which all stages exist simultaneously. However, time courses are becoming commonplace. Second, many methods model trajectories in terms of graph theory, which imposes strong constraints on the model, such as one-dimensional trajectories (‘‘edges’’) and zero-dimensional branch points (‘‘nodes’’). Thus, gradual divergence of fates is not captured well by these models. Third, few methods account for cellular growth and death during development (Table S6)."
> — Introduction · bears on: Claim 1, Claim 9, Claim 10, Axis B · enumerates structural limitations of existing trajectory-inference methods (no time, rigid graph structure, no growth/death).

> "cells at any time are drawn from a probability distribution in gene-expression space, and each cell has a distribution of both probable origins and probable fates (Figure 1). It uses scRNA-seq data collected across a time course to infer how these probability distributions evolve over time, by using the mathematical approach of optimal transport (OT)."
> — Introduction · bears on: Claim 3, Axis B · frames trajectory inference as evolution of distributions, with origins/fates as distributions rather than observed pairs.

> "because different cells are sampled independently at different time points, we lose the joint distribution of expression between pairs of time points, called temporal coupling. Absent any constraint on cellular transitions, we cannot infer the temporal coupling, but if we assume that cells move short distances over short time periods, then we can infer the temporal coupling by using the mathematical technique of optimal transport (Figure 1A; Methods S1)."
> — Results / Reconstruction of Probabilistic Trajectories by Optimal Transport · bears on: Claim 3, Axis B, Claim 10 · destructive, independent sampling destroys the joint (paired) distribution across time; the temporal coupling is recoverable only under modeling assumptions, not observation.

> "However, the application to cells differs in one key respect: unlike earth, cells can proliferate. We therefore modify the classical conservation of mass constraints to accommodate cell growth and death (Methods S1)."
> — Results / Reconstruction of Probabilistic Trajectories by Optimal Transport · bears on: Claim 10, Axis B · models cellular growth and death, a feature the paper argues other methods omit.

> "The optimal-transport calculation (1) implicitly assumes that a cell’s fate depends on its current position but not on its previous history (i.e., the stochastic process is Markov), and (2) captures only the timevarying components of the distribution (see Discussion)."
> — Results / Reconstruction of Probabilistic Trajectories by Optimal Transport · bears on: Claim 3, Axis B · states the Markov and time-varying-only modeling assumptions underlying the inferred couplings.

> "Because current experimental approaches for tracing cell lineage do not describe the transcriptional profile of a cell set’s ancestors, we developed a computational approach to validate the model."
> — Results / The Model Is Predictive and Robust · bears on: Claim 3, Axis B · concedes that experimental lineage tracing cannot supply ancestral expression profiles, forcing computational (not ground-truth) validation.

> "We performed two time course experiments. In the first, we collected 65,781 scRNA-seq profiles at 10 time points across 16 days, with samples taken every 48 h. In the second, we profiled 259,155 cells collected at 39 time points across 18 days, with samples taken every 12 h (every 6 h between days 8 and 9)."
> — Results / A Dense scRNA-Seq Time Course of iPS Reprogramming · bears on: Axis B, Claim 10 · documents the dense temporal sampling design (half-day / 6-hour resolution).

> "A powerful predictor of a cell’s fate is its expression level of the OKSM transgene, whose expression level explains 50% of the variance in the log fate ratio between MET versus stromal fate by day 2 and 75% by day 5 (Figure S2E). The divergence is gradual rather than a sharp branch point."
> — Results / In Initial Stages of Reprogramming, Cells Progress toward Stromal or MET Fates · bears on: Axis B, Claim 1 · quantifies gradual (non-branch-point) fate divergence, arguing against discrete graph-node trajectory models.

> "We next asked how these cell types might interact as they reprogram concurrently. For example, secretion of inflammatory cytokines is known to enhance reprogramming (Mosteiro et al., 2016). ... We defined an interaction score based on concurrent expression of ligand-receptor pairs across cell sets (Figures 6A, 6B, S5A, and S5B; STAR Methods)."
> — Results / The Developmental Landscape Highlights Potential Paracrine Signals · bears on: Claim 7, Axis C · cell–cell (paracrine) interactions shape fate, but here are inferred from concurrent ligand-receptor co-expression rather than measured with spatial information.

> "We identify a rich potential for paracrine interactions with stromal cells that may play key roles in the initial differentiation and maintenance of iPS-, neural-, and trophoblast-like cells."
> — Discussion / Tracking Cell Differentiation Trajectories and Fates · bears on: Claim 7, Axis C · microenvironmental secreted signals are proposed as drivers of fate, established without spatial proximity data.

> "To set Waddington-OT in context, we comprehensively reviewed 62 other approaches (Table S6), which fall into three classes: category 1 (33 tools) is not applicable to developmental time courses with scRNA-seq, category 2 (25 tools) is applicable but does not incorporate time information, and category 3 (4 tools) leverages time information, but does not model cell growth rates over time."
> — Discussion / An Optimal Transport Framework · bears on: Claim 1, Claim 9, Claim 10, Axis B · most trajectory-inference tools ignore time and/or growth, a systematic gap across 62 methods.

> "Category 2 methods produced trajectories that are completely inconsistent with the time course—making huge leaps across time points and, in some cases, going backward in time. For example, Monocle2 produced trajectories in which day 0 cells give rise to day 18 cells, which then give rise to day 8 cells."
> — Discussion / An Optimal Transport Framework · bears on: Claim 1, Claim 9 · widely used methods produce biologically nonsensical, time-violating trajectories on the same data — evidence of method unreliability / non-comparability.

> "Waddington-OT is the only approach that incorporates temporal information and models cell growth over time (that we can consider a new category 4). It is the only approach that produced reasonable trajectories on our data, suggesting that these features are critical for robust analysis of developmental processes. Moreover, it brings the powerful framework of optimal transport to biology and is the first application of OT to estimate the temporal coupling of a stochastic processes in any field."
> — Discussion / An Optimal Transport Framework · bears on: Claim 1, Claim 3, Axis B · claims temporal information + growth modeling are necessary for robust trajectories; positions OT-coupling as novel.

> "Optimal-transport analysis is only intended to capture the time-varying components of a distribution Pt. For systems in dynamic equilibrium, Pt does not change over time and optimal transport would infer that each cell is stationary. ... Our focus is on out-of-equilibrium systems, where the distribution Pt undergoes major changes over time."
> — Discussion / An Optimal Transport Framework · bears on: Axis B, Claim 3 · stated scope limit: the method recovers only out-of-equilibrium change, not dynamics within a stationary distribution.

> "First, the framework currently assumes that a cell’s trajectory depends only on its current gene-expression levels. One could incorporate other types of information like epigenomic state."
> — Discussion / Future Prospects · bears on: Claim 4, Claim 8, Axis A · concedes the model uses gene expression alone and that other modalities (e.g., epigenomic state) would add orthogonal information.

> "Second, our framework for learning regulatory models assumes that trajectories are cell autonomous, but might be extended to incorporate intercellular interactions, such paracrine signaling, by using optimal transport for interacting particles (Ambrosio et al., 2008; Santambrogio, 2015) (Methods S1)."
> — Discussion / Future Prospects · bears on: Claim 7, Axis C · concedes the cell-autonomous assumption omits intercellular/microenvironmental interactions.

> "Third, various methods exist for obtaining lineage information about cells, based on the introduction of barcodes at discrete time points or continuously (Kester and van Oudenaarden, 2018). Barcodes can be used to recognize cells that descend from a recent common ancestor cell but do not currently directly reveal the full gene-expression state of the ancestral cell."
> — Discussion / Future Prospects · bears on: Claim 3, Axis B · lineage barcoding gives clonal relations but not the ancestral expression state — restating the core gap that trajectories must be inferred.

> "Finally, our method can be refined to analyze all time points simultaneously rather than just consecutive pairs; this can be particularly useful for situations where the number of cells at different time points varies significantly."
> — Discussion / Future Prospects · bears on: Axis B · notes a current limitation: couplings are composed from consecutive pairs rather than fitted jointly.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 3 — destructive sequencing cannot pair the same cell across time | "Because scRNA-seq destroys cells…one cannot follow expression of the same cell" / Introduction | supports |
| Claim 3 — temporal coupling lost by independent sampling | "because different cells are sampled independently…we lose the joint distribution" / Results · Reconstruction | supports |
| Claim 3 — lineage tracing lacks ancestral expression state | "current experimental approaches for tracing cell lineage do not describe the transcriptional profile of a cell set’s ancestors" / Results · Model Is Predictive; "Barcodes…do not currently directly reveal the full gene-expression state" / Discussion · Future Prospects | supports |
| Axis B — temporal (time course / trajectory inference) | "scRNA-seq data collected across a time course to infer how these probability distributions evolve" / Introduction; "39 time points across 18 days…every 12 h" / Results · Dense Time Course | supports |
| Claim 10 — resolution × throughput × destructiveness trade-off | "rely heavily on computational approaches to connect discrete ‘‘snapshots’’ into continuous ‘‘movies.’’" / Introduction; growth/death modeling / Results · Reconstruction | supports |
| Claim 1 — pure data-driven trajectory tools generalize/perform poorly | "Monocle2 produced trajectories in which day 0 cells give rise to day 18 cells, which then give rise to day 8 cells" / Discussion | supports |
| Claim 9 — methods not comparable / unreliable across the same data | "comprehensively reviewed 62 other approaches…category 2…does not incorporate time…category 3…does not model cell growth" / Discussion | supports |
| Claim 7 — microenvironment / paracrine signals shape cell state & fate | "rich potential for paracrine interactions with stromal cells that may play key roles" / Discussion; "interaction score based on concurrent expression of ligand-receptor pairs" / Results · Paracrine | supports |
| Axis C — spatial | paracrine inferred from co-expression, dissociated scRNA-seq; "trajectories are cell autonomous…might be extended to incorporate intercellular interactions" / Discussion · Future Prospects | challenges (absence: cell–cell interaction inferred, not measured in situ) |
| Claim 4 / Claim 8 — modalities are orthogonal / need integration | "assumes that a cell’s trajectory depends only on its current gene-expression levels…incorporate other types of information like epigenomic state" / Discussion · Future Prospects | nuances |
| Axis A — modality (RNA only here) | gene expression is the sole input throughout; epigenomic state listed as a future add-on / Discussion | nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Data scale | ≈315,000 total scRNA-seq profiles across two experiments; experiment 1 = 65,781 cells, 10 time points, 16 days, 48 h intervals; experiment 2 = 259,155 cells, 39 time points, 18 days, 12 h intervals (6 h between days 8–9). |
| Filtering | After downsampling to 15,000 UMIs/cell and filtering (<2000 UMIs, genes in <50 cells removed): 251,203 cells, G = 19,089 genes retained; 1,479 variable genes selected (Seurat MeanVarPlot, z-scored dispersion threshold 1.0). |
| Sequencing depth | Average 87 million paired-end reads/sample; larger experiment ≈46,523 reads/cell. |
| Figure 2I | Ancestor-distribution divergence: stromal vs MET ancestors differ by 30% at day 3 and 60% at day 6; stromal ancestors begin diverging as early as day 1.5. |
| Figure S2E | OKSM transgene level explains ≈50% of variance in log MET-vs-stromal fate ratio by day 2, 75% by day 5. |
| iPSC bottleneck | iPSC trajectory = 40% of cells at day 8.5, but only 10% at day 10 (2i) and 1% at day 11 (serum). |
| Figures 5D–5F | Whole-chromosome aneuploidy inferred in 4.0% of trophoblasts and 2.1% of stromal cells vs 1.1% of other cells; sub-chromosomal events in 6.9% of trophoblasts and 3.2% of stromal cells (vs 1.2% other, 0.4% neural); aberration-detection method ≈45% sensitivity, high specificity. |
| Figures 7B–7F | Obox6 and Zfp42 each ≈2-fold increase in reprogramming efficiency (2i; more in serum); GDF9 (dose-dependent, daily from day 8) ≈4–5-fold increase at highest dose, measured by Oct4-GFP colonies, bulk RNA-seq, and scRNA-seq. |
| Growth model params | Birth rate β∈[0.3, 1.7] (fastest doubling ≈9.6 h, slowest ≈55 h); death rate δ∈[0.3, 1.7]; OT params ε=0.05, λ1=1, λ2=50, growth_iters=3; cost = squared Euclidean distance in 30-D local PCA. |
| Table S6 | Comparative review of 62 trajectory-inference approaches in 3 categories (33 not applicable; 25 applicable but no time; 4 use time but no growth modeling). |

---

## Primary Sources Behind Key Quotes
- Destructive sequencing / lineage tracing limits → Kester, L., and van Oudenaarden, A. (2018). "Single-cell transcriptomics meets lineage tracing." Cell Stem Cell 23, 166–179.
- Single-cell solves cell-class discovery → Tanay, A., and Regev, A. (2017). Nature 541, 331–338.
- Trajectory-inference method comparison → Saelens, W., Cannoodt, R., Todorov, H., and Saeys, Y. (2018). bioRxiv, doi:10.1101/276907.
- Unbalanced transport (growth/death) → Chizat, L., Peyré, G., Schmitzer, B., and Vialard, F.-X. (2018). "Scaling algorithms for unbalanced transport problems." Math. Comp. 87, 2563–2609.
- Optimal transport foundations → Monge, G. (1781); Kantorovich, L. (1942). Comptes Rendus (Doklady) de l'Academie des Sciences de l'URSS 37, 199–201.
- Inflammatory cytokines / senescence enhance reprogramming → Mosteiro, L., et al. (2016). Science 354, aaf4445.
- Yamanaka reprogramming → Takahashi, K., and Yamanaka, S. (2006). Cell 126, 663–676; (2016). Nat. Rev. Mol. Cell Biol. 17, 183–193.
- Prior scRNA-seq of chemical reprogramming (single bifurcation) → Zhao, T., et al. (2018). Cell Stem Cell 23, 31–45.

---

## Flags
- [ ] Metadata unverified: Journal volume/issue/page range NOT printed in the source text. DOI (10.1016/j.cell.2019.01.006), venue (Cell), and dates (Received Jul 3, 2018; Revised Oct 15, 2018; Accepted Jan 2, 2019; Published Jan 31, 2019) are confirmed from the text; volume/pages are not — do not state them as fact without checking the published article.
- [ ] Data availability: raw scRNA-seq deposited as GEO: GSE122662 (Key Resources Table) — useful if first-hand data access is needed.
- [ ] Read at source: Table S6 (full 62-method comparison) and Figure S7 are referenced for the method-limitation claims but live in Supplemental Information (not in this cleaned file); Methods S1 holds the formal OT/temporal-coupling math. Read these directly if the writer leans on the benchmark or the mathematical framing.
- [ ] Scope note (not an error): This paper is dissociated, RNA-only scRNA-seq with no spatial measurement; its paracrine/microenvironment findings (Claim 7 / Axis C) are inferred from ligand-receptor co-expression, not from spatial proximity — relevant as a foil illustrating the spatial gap, not as evidence that spatial data were collected.
