# Generalizing RNA velocity to transient cell states through dynamical modeling — Source Index

**Authors:** Volker Bergen, Marius Lange, Stefan Peidli, F. Alexander Wolf, Fabian J. Theis
**Journal / Venue:** Nature Biotechnology, 2020 (journal inferred from DOI prefix s41587 and self-citations; exact volume/issue/pages not printed in cleaned text — see Flags)
**DOI:** doi:10.1038/s41587-020-0591-3
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/25_cleaned.md

---

## In One Sentence
The paper presents scVelo, a likelihood-based dynamical model that infers RNA velocity by solving the full splicing kinetics (transcription, splicing, degradation rates) per gene from a single static scRNA-seq snapshot, and from it derives a gene-shared "latent time" plus putative driver genes for transient developmental systems (dentate gyrus neurogenesis, pancreatic endocrinogenesis).

## Orientation (non-binding)
This is a methods paper that openly concedes the data limitations our thesis targets — it states scRNA-seq is destructive and yields "only static snapshots," is "not time resolved," and (in Discussion) lacks spatial coordinates and is RNA-only. It is therefore strong material for **Claim 3** (destructive measurement → no paired temporal observation; time only inferred, not measured) and secondarily for **Claims 1, 2, 4**. It can serve as BOTH support (it concedes the destructive-snapshot fact we build on) and foil (it is a paradigmatic computational workaround that reconstructs pseudo/latent time and directionality from a single snapshot rather than measuring real trajectories). The downstream agent decides the role.

---

## Load-Bearing Excerpts

> "A central challenge in trajectory inference is the destructive nature of single-cell RNA sequencing (scRNA-seq), which reveals only static snapshots of cellular states."
> — Introduction / p.1 · bears on: Claim 3 (destructive measurement, no paired time), Axis B (temporal) · the paper concedes that scRNA-seq is destructive and gives only static snapshots.

> "To move from descriptive toward predictive trajectory models, additional information is required to constrain the space of possible dynamics that could give rise to the same trajectory."
> — Introduction / p.1 · bears on: Claim 3, Claim 1 · a snapshot underdetermines the dynamics; extra information is needed to constrain which trajectory produced it (cites refs 9, 10).

> "As such, lineage-tracing assays can add information via genetic modification to enable the reconstruction of lineage relationships. However, these assays are not straightforward to set up and are technically limited in many systems, such as human tissues."
> — Introduction / p.1 · bears on: Claim 3 (alternative ways to recover time/lineage and their limits) · lineage tracing can add real lineage information but is technically limited, especially in human tissue (cites refs 11–17).

> "The concept of RNA velocity has enabled the recovery of directed dynamic information by leveraging the fact that newly transcribed, unspliced pre-mRNAs and mature, spliced mRNAs can be distinguished in common scRNA-seq protocols, the former detectable by the presence of introns."
> — Introduction / p.1 · bears on: Claim 3, Claim 4 · directional/temporal information is computationally recovered from a single RNA snapshot via the spliced/unspliced ratio.

> "The inferred latent time represents the cell's internal clock, which accurately describes the cell's position in the underlying biological process."
> — Introduction / p.1 · bears on: Claim 3, Axis B (temporal) · time here is an inferred latent quantity, not a measured timestamp.

> "In contrast to existing similarity-based pseudo-time methods, this latent time is grounded only on transcriptional dynamics and accounts for speed and direction of motion."
> — Introduction / p.1 · bears on: Claim 3 · both pseudo-time and latent time are reconstructed orderings inferred from snapshot data rather than observed real time.

> "These assumptions are often violated, in particular when a population comprises multiple heterogeneous subpopulations with different kinetics."
> — Introduction / p.1 · bears on: Claim 1 (model assumptions break on real heterogeneous data) · the standard steady-state model's assumptions frequently fail on real heterogeneous populations.

> "In general, the sampled population is not time resolved, and t is a latent variable. Likewise, the cell's transcriptional state k is a latent variable that is not known, and the rates α(k), β and γ are usually not experimentally measured."
> — Methods, "Modeling transcriptional dynamics" / p.6 · bears on: Claim 3, Claim 4 · explicit statement that the data carry no real time axis and that kinetic rates are not measured but inferred.

> "we considered a scRNA-seq experiment from the developing mouse dentate gyrus comprising two time points (P12 and P35) measured using droplet-based scRNA-seq"
> — Results, "Resolving the heterogeneous population kinetics in dentate gyrus development" / p.2 · bears on: Claim 3 · only two coarse experimental time points are available; not a continuous, paired time course.

> "Whether a cell type is still in transition or already terminal is indicated by two experimental time points (Supplementary Fig. 6a) and experimental analysis, both supporting the overall velocity-inferred directionality."
> — Results, dentate gyrus / p.2 · bears on: Claim 3 · the computationally inferred directionality still has to be validated against external experimental time points.

> "In real time, α-cells are produced earlier (before E12.5) than β-cells (E12.5–E15.5). This ordering is captured by latent time but not by pseudo-time."
> — Results, "Relating cell fates and disentangling dynamical regimes through latent time" / p.3 · bears on: Claim 3 · inferred orderings (latent vs pseudo-time) are benchmarked against known real developmental time; pseudo-time gets the ordering wrong (cites ref 20).

> "the observed time frame in the data covers only a small part of the timeframe of the underlying dynamical process… the snapshot captured in an scRNA-seq data set recovers little of the full dynamics. Here, the overall developmental time scale of the sampled population might be far shorter than the potential duration of the kinetics."
> — Results, "Accounting for different kinetic regimes and insufficiently observed kinetics" / p.4 · bears on: Claim 3 · a single snapshot can capture only a small fraction of the true temporal dynamics, creating an identifiability problem.

> "This manifests in a straight line rather than a curve in the unspliced to spliced phase diagram, which constitutes a fundamental issue to all existing models for velocity estimation."
> — Methods, "Accounting for insufficiently observed kinetics with prior information" / p.7 · bears on: Claim 1, Claim 3 · insufficiently observed kinetics is a fundamental limitation shared by all velocity-estimation methods.

> "we advise the user not to limit biological conclusions to the projected velocities but to examine individual gene dynamics via phase portraits to understand how inferred directions are supported by particular genes."
> — Results, insufficiently observed kinetics / p.4 · bears on: Claim 1 · explicit caution against over-trusting the inferred directional output.

> "scVelo enables velocity estimation without assuming either the presence of steady states or a common splicing rate across genes. It maintains the weaker assumptions of constant gene-specific splicing and degradation rates and two transcription rates each for induction and repression. These assumptions might be violated in practice and can be addressed by extending scVelo toward more complex regulations."
> — Discussion / p.4 · bears on: Claim 1 · even the improved model retains assumptions that may be violated in practice.

> "In particular, spatial single-cell RNA profiling at transcriptome scale might provide additional information on relative cell positions necessary to resolve spatial dependencies in gene regulation. Spatial coordinates as well as experimental time might also be leveraged as additional constraints to extend the concept of latent time—for instance, to capture the progression around a cell cycle."
> — Discussion / p.4 · bears on: Claim 2 (scRNA-seq lacks spatial), Claim 8 (integration), Axis B + Axis C · spatial coordinates and experimental time are described as missing inputs that would constrain and improve the inference (cites refs 41, 42).

> "Extending the kinetic model to protein translation has been proposed within the steady-state formulation and can be likewise included into the dynamical model."
> — Discussion / p.4 · bears on: Claim 4 (RNA-only modality; protein as a distinct downstream layer), Axis A (proteome) · protein/translation is a separate modality not captured by the RNA readout, available only by extending the model (cites ref 44).

> "Metabolic labeling, for example using single-cell SLAM-seq, enables the quantification of total RNA levels together with newly transcribed RNA. This additional readout can be easily included into the dynamical model, incorporating varying labeling lengths as additional prior."
> — Discussion / p.4 · bears on: Claim 3 (experimental readouts that add temporal information), Claim 4 · an additional experimental measurement (metabolic labeling) supplies temporal information beyond the static snapshot (cites refs 45, 46).

> "scVelo's suitability for characterizing transient populations makes it a promising candidate for studying cellular responses to perturbation, which often display drastic switching behaviors. In particular, scVelo could help to mechanistically understand recent machine learning approaches to modeling such response and point to ways to extend them to incorporate splicing dynamics."
> — Discussion / p.4 · bears on: Axis A (phenotype / perturbation response), Claim 1 · connects dynamics inference to machine-learning perturbation-response models (cites ref 48, scGen).

> "On the gene level, full-length scRNA-seq protocols, such as Smart-seq2, allow accounting for gene structure, alternative splicing and state-dependent degradation rates."
> — Discussion / p.4 · bears on: Claim 10 (protocol/measurement trade-offs) · different scRNA-seq protocols capture different information; full-length protocols enable readouts droplet protocols cannot (cites ref 40).

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 3 — destructive sequencing cannot pair-observe time | "the destructive nature of single-cell RNA sequencing… reveals only static snapshots" / Introduction | supports |
| Claim 3 — time inferred, not measured (distribution-based) | "the sampled population is not time resolved, and t is a latent variable" / Methods | supports |
| Claim 3 — pseudo/latent time are reconstructions | "latent time represents the cell's internal clock"; "captured by latent time but not by pseudo-time" / Intro, Results | nuances |
| Claim 3 — snapshot captures little of full dynamics | "the snapshot captured in an scRNA-seq data set recovers little of the full dynamics" / Results | supports |
| Claim 3 — lineage tracing as alternative + limits | "lineage-tracing assays… technically limited in many systems, such as human tissues" / Introduction | nuances |
| Claim 1 — model assumptions break / generalization limits | "These assumptions are often violated…"; "might be violated in practice" / Intro, Discussion | supports |
| Claim 1 — fundamental limit shared by all velocity models | "a fundamental issue to all existing models for velocity estimation" / Methods | supports |
| Claim 2 — scRNA-seq lacks spatial information | "spatial single-cell RNA profiling… additional information on relative cell positions" / Discussion | supports |
| Claim 4 — RNA-only modality; protein not captured | "Extending the kinetic model to protein translation has been proposed…" / Discussion | nuances |
| Claim 4 / Claim 3 — extra readout (labeling) for temporal info | "Metabolic labeling… total RNA levels together with newly transcribed RNA" / Discussion | nuances |
| Claim 8 — integrate spatial + temporal as constraints | "Spatial coordinates as well as experimental time might also be leveraged as additional constraints" / Discussion | supports |
| Claim 10 — protocol/measurement trade-offs | "full-length scRNA-seq protocols, such as Smart-seq2…" / Discussion | nuances |
| Axis A — phenotype / perturbation response | "promising candidate for studying cellular responses to perturbation" / Discussion | nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1b | States that in transient cell populations steady states are often not reached (e.g., induction terminates before mRNA saturation, "early switching"), motivating why a snapshot may not capture full dynamics. |
| Fig. 3d | Compares scVelo latent time vs diffusion pseudo-time against known real developmental chronology (α-cells before E12.5; β-cells E12.5–E15.5); latent time recovers the ordering, pseudo-time does not. |

*(Other figures/numbers — simulation correlations, runtime/scaling benchmarks — concern method accuracy and engineering, which fall outside the roadmap and are omitted.)*

---

## Primary Sources Behind Key Quotes
- Fundamental limits of inferring dynamics from a single snapshot → Weinreb, C. et al. Fundamental limits on dynamic inference from single-cell snapshots. Proc. Natl Acad. Sci. USA 115, E2467–E2476 (2018), ref #9.
- Limits of learning developmental trajectories from snapshots → Tritschler, S. et al. Concepts and limitations for learning developmental trajectories from single cell genomics. Development 146, dev170506 (2019), ref #10.
- Original RNA velocity concept → La Manno, G. et al. RNA velocity of single cells. Nature 560, 494 (2018), ref #18.
- Lineage tracing (real lineage information vs snapshots) → e.g., Kester, L. & van Oudenaarden, A. Single-cell transcriptomics meets lineage tracing. Cell Stem Cell 23, 166–179 (2018), ref #16; Ludwig, L. S. et al. Lineage tracing in humans enabled by mitochondrial mutations and single-cell genomics. Cell 176, 1325–1339.e22 (2019), ref #17.
- Spatial transcriptomics (missing spatial dimension) → Moor, A. E. & Itzkovitz, S. Spatial transcriptomics: paving the way for tissue-level systems biology. Curr. Opin. Biotechnol. 46, 126–133 (2017), ref #41; Xia, C. et al. (MERFISH) Proc. Natl Acad. Sci. USA 116, 19490–19499 (2019), ref #42.
- Protein velocity (protein modality not captured by RNA) → Gorin, G., Svensson, V. & Pachter, L. Protein velocity and acceleration from single-cell multiomics experiments. Genome Biol. 21, 39 (2020), ref #44.
- Metabolic labeling for new vs total RNA → Erhard, F. et al. scSLAM-seq reveals core features of transcription dynamics in single cells. Nature 571, 419–423 (2019), ref #45.
- ML perturbation-response models → Lotfollahi, M. et al. scGen predicts single-cell perturbation responses. Nat. Methods 16, 715–721 (2019), ref #48.
- Diffusion pseudo-time (baseline for inferred time) → Haghverdi, L. et al. Diffusion pseudotime robustly reconstructs lineage branching. Nat. Methods 13, 845–848 (2016), ref #3.

---

## Flags
- [ ] Metadata unverified: journal volume/issue/page numbers are NOT printed in the cleaned text. Journal name ("Nature Biotechnology") is inferred from the DOI prefix s41587 (uniquely Nature Biotechnology) and from in-paper self-citations to "Nat. Biotechnol."; DOI (10.1038/s41587-020-0591-3) and dates (Received 28 Oct 2019; Accepted 5 Jun 2020; Published online 3 Aug 2020) are confirmed in the text.
- [ ] Reconstructed (NOT in source text): none — full author names are printed verbatim in the source (Authors section).
- [ ] Read at source: Weinreb et al. 2018 (PNAS, "Fundamental limits on dynamic inference from single-cell snapshots") is the single most on-thesis primary source for Claim 3 and is worth reading first-hand rather than via this paper; also La Manno et al. 2018 (original RNA velocity) and Gorin et al. 2020 (protein velocity).
- [ ] Scope note: this is a single-modality (spliced/unspliced mRNA) computational methods paper; its algorithmic internals (EM/ODE/likelihood derivations, runtime benchmarks) are out of scope per the context file and were deliberately not captured — only the data-foundation concessions and modality/temporal/spatial statements were extracted.
- [ ] Source inconsistency: none material; page numbers above are approximate (cleaned MD has no print pagination — "p.X" approximates position within the body).
