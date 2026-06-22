# RNA velocity of single cells — Source Index

**Authors:** Gioele La Manno, Ruslan Soldatov, Amit Zeisel, Emelie Braun, Hannah Hochgerner, Viktor Petukhov, Katja Lidschreiber, Maria E. Kastriti, Peter Lönnerberg, Alessandro Furlan, Jean Fan, Lars E. Borm, Zehua Liu, David van Bruggen, Jimin Guo, Xiaoling He, Roger Barker, Erik Sundström, Gonçalo Castelo-Branco, Patrick Cramer, Igor Adameyko, Sten Linnarsson*, Peter V. Kharchenko* (*corresponding)
**Journal / Venue:** Nature, 2018 (volume/issue/pages unverified; see Flags)
**DOI:** doi:10.1038/s41586-018-0414-6
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/24_cleaned.md

---

## In One Sentence
The paper introduces RNA velocity — the time derivative of gene expression, estimated from the ratio of unspliced (nascent) to spliced (mature) mRNA in standard single-cell RNA-seq — and shows it predicts each cell's near-future transcriptional state, recovering directionality of differentiation/lineage trees from a single static snapshot across mouse and human datasets.

## Orientation (non-binding)
This is a methods landmark for the **temporal axis (Axis B)** and roadmap **Claim 3** (destructive sequencing cannot pair-observe a cell over time → trajectory inference). It is dual-use for our thesis: it openly **concedes** that scRNA-seq "captures only a static snapshot," supporting our "data lost time" claim; yet it is also the field's flagship **computational workaround**, and its own admissions (a few-hours, linear extrapolation horizon; predictions delivered as probability distributions over future states; reliance on lineage tracing as orthogonal ground truth) document the limits of inferring time from a snapshot rather than truly observing a trajectory. It operates entirely within the RNA modality (a possible nuance for Claim 4). The downstream agent decides whether to deploy it as a concession (support) or as a named foil.

---

## Load-Bearing Excerpts

> "Single-cell RNA sequencing can reveal RNA abundance with high quantitative accuracy, sensitivity and throughput. However, this approach captures only a static snapshot at a point in time, posing a challenge for the analysis of time-resolved phenomena such as embryogenesis or tissue regeneration."
> — Abstract · bears on: Claim 3, Axis B, Claim 10 · The paper concedes scRNA-seq yields only a static snapshot, limiting time-resolved analysis.

> "Here we show that RNA velocity—the time derivative of the gene expression state—can be directly estimated by distinguishing between unspliced and spliced mRNAs in common single-cell RNA sequencing protocols. RNA velocity is a high-dimensional vector that predicts the future state of individual cells on a timescale of hours."
> — Abstract · bears on: Claim 3, Axis B · A computational estimate infers a short-horizon future state per cell from one static measurement.

> "We reasoned that similar signals may be detectable in single-cell RNA sequencing (RNA-seq) data, and could reveal the rate and direction of change of the entire transcriptome during dynamic processes."
> — Main text (introduction) · bears on: Claim 3, Axis B · States the aim of recovering rate/direction of change from static data.

> "we found that 15–25% of reads contained unspliced intronic sequences (Fig. 1a), in agreement with previous observations in bulk (14.6%) and single-cell (~20%) RNA-seq."
> — Main text · bears on: Axis B · Quantitative basis for detecting nascent mRNA in standard protocols.

> "83% of all genes displayed expression time courses consistent with simple first-order kinetics, as expected if unspliced reads represent nascent mRNA."
> — Main text · bears on: Axis B · Quantitative validation of the nascent-mRNA assumption via metabolic labelling.

> "The balance of unspliced and spliced mRNA abundance is, therefore, an indicator of the future state of mature mRNA abundance, and thus the future state of the cell."
> — Main text · bears on: Claim 3, Axis B · Core claim: spliced/unspliced balance predicts the cell's future.

> "Unspliced mRNA levels at each time point were consistently more similar to the spliced mRNA of the subsequent time"
> — Main text (mouse liver circadian time course) · bears on: Axis B · Uses a real bulk time course to validate the predictive direction.

> "during development, a substantial proportion of chromaffin cells ... arise from Schwann cell precursors, providing a convenient test case in which the direction of differentiation can be validated by lineage tracing."
> — Main text · bears on: Claim 3 · Lineage tracing is the orthogonal ground truth used to validate the inferred temporal direction.

> "care must be taken when interpreting low-dimensional representations, as cells that lack apparent velocity in one particular embedding can nevertheless have substantial velocity in some subspace that is not visualized."
> — Main text · bears on: Claim 3 · Conceded interpretation caveat for the velocity field.

> "Metabolic labelling showed that for most genes, changes in the spliced/unspliced ratio would be detectable after 10–100 min."
> — Main text · bears on: Axis B · Quantitative detection timescale of the signal.

> "we estimate that we were able to extrapolate 2.5–3.8 h into the future (Fig. 2f, g) ... Given the linear nature of the extrapolation, however, this predictive timescale will depend on the shape of the gene expression trajectory (that is, the curvature of the expression manifold)."
> — Main text · bears on: Claim 3, Axis B · CONCEDED limitation: predictive window is only a few hours and the extrapolation is linear.

> "Cell fates can be predicted over longer time scales by tracing a sequence of small extrapolation steps on the observed expression manifold (Supplementary Note 2 Section 7)."
> — Main text · bears on: Claim 3, Axis B · Longer horizons require chaining short steps along the observed manifold.

> "Estimates of RNA velocity were robust to variations in the model parameters, and gene and cell subsampling, with the most sensitive parameter being the size of the neighbourhood used in the visualization of velocity in pre-defined embeddings."
> — Main text · bears on: Claim 3 · Robustness claim plus the most sensitive parameter.

> "Failures in specific cases had several apparent causes, including genes observed exclusively far from equilibrium, uneven contribution of non-coding transcripts, and alternative splicing leading to multiple rates of γ across the measured populations."
> — Main text · bears on: Claim 3 · Conceded failure modes of the method.

> "Using a Markov random-walk model on the velocity field, the terminal and root states could be automatically identified (Fig. 3c), demonstrating the power of RNA velocity to orient the lineage tree without prior knowledge about the developmental process."
> — Main text (hippocampus) · bears on: Claim 3, Axis B · Lineage tree is oriented computationally from the velocity field.

> "Comparing the probability distribution of future states for a cell starting among the pre-OPCs, with one starting in the narrow passage leading to OPCs revealed a clear difference—the latter cell was overwhelmingly likely to end up as a fully formed OPC whereas the former was as likely to remain in the pre-OPC state."
> — Main text · bears on: Claim 3 · Future fate is delivered as a probability distribution over states, not a paired observation.

> "Examining two adjacent neuroblasts just at the entrance to the branching point between CA and granule fates ... we found that although their current states were neighbours (in gene-expression space), their futures were already tilted towards different fates"
> — Main text · bears on: Claim 3, Axis B · Inferred per-cell future fate from a single snapshot.

> "We used principal curve analysis to order the cells according to a differentiation pseudotime, and examined the temporal progression of transcription in human primary cells."
> — Main text (human forebrain) · bears on: Claim 3, Axis B · Time reconstructed by pseudotime ordering, with direction set by the velocity field.

> "The layered expression of these genes in the tissue (Fig. 4c) corresponded closely to the pseudotemporal distribution of their expression in the single-cell RNA-seq data (Fig. 4b)."
> — Main text (human forebrain) · bears on: Axis C, Axis B · Spatial tissue layering, recovered via a separate in situ hybridization assay, matches the pseudotime ordering derived from dissociated scRNA-seq.

> "The majority (75%) of the genes that were differentially regulated along the pseudotime trajectory showed a positive correlation with the empirical expression derivative."
> — Extended Data Fig. 8 legend · bears on: Claim 3 · Quantitative agreement between velocity estimates and observed expression derivatives.

> "As RNA velocity is grounded in real transcription kinetics, this approach promises to bring a more solid quantitative foundation to our understanding of the dynamics of cells in gene-expression space during differentiation."
> — Discussion · bears on: Claim 3, Axis B · Positions velocity as a kinetics-grounded route to cell dynamics.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 3 — destructive seq cannot pair-observe time → trajectory inference | "this approach captures only a static snapshot…" / Abstract | supports |
| Claim 3 — trajectory/lineage inference as workaround | "RNA velocity … predicts the future state of individual cells on a timescale of hours" / Abstract | nuances |
| Claim 3 — limits of inferred (vs observed) time | "extrapolate 2.5–3.8 h … linear nature of the extrapolation" / Main text | challenges |
| Claim 3 — fate as distribution, not paired observation | "probability distribution of future states for a cell…" / Main text | nuances |
| Claim 3 — lineage tracing as orthogonal ground truth | "validated by lineage tracing" / Main text | supports |
| Axis B — temporal (every modality needs a time course / trajectory) | "order the cells according to a differentiation pseudotime" / Main text | nuances |
| Axis C — spatial | "layered expression … corresponded … to the pseudotemporal distribution" (validated by in situ) / Main text | nuances |
| Claim 10 — resolution × throughput × destructiveness trilemma | "static snapshot at a point in time" / Abstract | supports |
| Claim 4 — modalities orthogonal / non-substitutable | entire method confined to RNA (unspliced vs spliced) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Transcriptional-dynamics model: transcription (α), splicing (β), degradation (γ) rates for unspliced (u) and spliced (s) mRNA; steady-state slope u = γs; phase portraits; demonstration on mouse liver 24-h circadian time course. |
| Fig. 2 | RNA velocity recapitulates chromaffin-cell differentiation (E12.5, n = 385 cells); optimal extrapolation-time distribution with mode 2.1 h; velocity visualized on PCA and t-SNE. |
| Fig. 3 | Velocity field of developing mouse hippocampus (n = 18,213 cells; P0 8,113 + P5 10,100); Markov-random-walk identification of root (radial glia) and terminal states; fate-decision analyses. |
| Fig. 4 | Human embryonic glutamatergic neurogenesis (week 10 post-conception, n = 1,720 cells); pseudotime by principal curve; in situ hybridization (RNAscope) validation of layered marker expression. |
| Quant. values | Unspliced fraction 15–25% of reads (bulk 14.6%, single-cell ~20%); 83% of genes fit first-order kinetics; spliced/unspliced change detectable after 10–100 min; extrapolation 2.5–3.8 h (mode 2.1 h); 11% (Ext. Data 10.8%) of genes show two γ slopes; 75% of pseudotime-regulated genes correlate with empirical derivative. |

---

## Primary Sources Behind Key Quotes
- Transcriptional-dynamics kinetic model (the α/β/γ framework the paper builds on) → Zeisel, A. et al., Coupled pre-mRNA and mRNA dynamics…, Mol. Syst. Biol. 7, 529 (2011) — ref 2.
- Prior bulk intronic/exonic-read analysis of transcriptional regulation → Gaidatzis, D., Burger, L., Florescu, M. & Stadler, M. B., Nat. Biotechnol. 33, 722–729 (2015) — ref 4.
- Chromaffin / Schwann-cell-precursor lineage-tracing test case (ground truth for direction) → Furlan, A. et al., Science 357, eaal3753 (2017) — ref 13.

---

## Flags
- [ ] Metadata unverified: Journal confirmed as Nature (DOI prefix 10.1038/s41586-, "Nature thanks…" peer-review note) and DOI 10.1038/s41586-018-0414-6 confirmed in text; volume/issue/page numbers are NOT present in the cleaned source — do not assert them.
- [ ] Source cleaning artifact: DOI is rendered with a stray space in the cleaned text ("10.1038/s41586- 018-0414-6"); resolved here to 10.1038/s41586-018-0414-6.
- [ ] Source inconsistency: reference 18 in the cleaned text ("18. Plass, M. et al. Prox1 postmitotically defnes dentate gyrus cells…, Science 360, eaaq1723 (2018)") carries a title identical to ref 17 (Iwano et al., Development 2012) — an apparent OCR/cleaning mismatch; the Plass et al. 2018 Science paper is a whole-organism single-cell study, not the Prox1 paper.
- [ ] Page anchors: the cleaned MD has no page boundaries, so excerpts are anchored by section name (Abstract / Main text / Discussion / Methods / figure legends) rather than page number.
- [ ] Read at source: Zeisel et al. 2011 (ref 2, the kinetic model underpinning velocity) and Furlan et al. 2017 (ref 13, the lineage-tracing validation) are worth reading first-hand if the writer cites the model or the ground-truth validation.
