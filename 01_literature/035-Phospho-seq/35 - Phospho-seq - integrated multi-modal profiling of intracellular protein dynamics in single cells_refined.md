# Phospho-seq: integrated, multi-modal profiling of intracellular protein dynamics in single cells — Source Index

**Authors:** John D. Blair, Austin Hartman, Fides Zenk, Philipp Wahle, Giovanna Brancati, Carol Dalgarno, Barbara Treutlein & Rahul Satija
**Journal / Venue:** Nature Communications, 2025 (article no. via DOI; volume/page not printed in cleaned text — see Flags)
**DOI:** doi:10.1038/s41467-025-56590-7
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/35 - Phospho-seq - integrated multi-modal profiling of intracellular protein dynamics in single cells_cleaned.md

---

## In One Sentence
The authors introduce Phospho-seq, a benchtop antibody-conjugation single-cell workflow that simultaneously quantifies up to 64 intracellular/intranuclear proteins (including 20 phospho-states) together with chromatin accessibility (scATAC) and — experimentally or via computational "bridge integration" — transcriptomes, and apply it to cell lines and retinal/brain organoids to link signaling-pathway activity, transcription factors, cis-regulatory elements, and gene expression in neurodevelopment.

## Orientation (non-binding)
This is a single-cell **multimodal method** paper whose center of gravity is the **protein / post-translational-modification (phospho) modality** that the dominant scRNA-seq paradigm omits — directly relevant to Axis A (modality) and Claims 4, 5, 6, 8. It supplies unusually clean ammunition for the **measurement trade-off / "trilemma" (Claim 10)**: it quantifies exactly how much per-modality data quality is lost when more modalities are captured at once. It can serve as **both support and foil**: support for "protein/phospho carries orthogonal, irreplaceable information that RNA and chromatin cannot recover" (Claim 4/5), and foil for "the dissociative single-cell paradigm still strips tissue-level **space** and observes **time** only through computational pseudotime, not paired real-time tracking" (Claims 2, 3; Axes B, C). Routing hint only — the downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "Signal transduction links the activation of signaling pathways to downstream changes in cellular chromatin, transcription, and translation, and is primarily regulated by changes in post-translational modifications."
> — Introduction / p.1 · bears on: Claim 5, Axis A (PTM / protein-state) · the regulatory/functional layer of the cell is governed by PTMs, a modality distinct from transcript abundance.

> "methods that can accurately measure and quantify phosphorylation states at single-cell resolution alongside additional molecular modalities offer substantial promise to improve our understanding of cellular activity and function."
> — Introduction / p.1 · bears on: Claim 5, Axis A · motivates measuring phospho-state as its own modality.

> "While powerful, these technologies focus exclusively on the profiling of cell surface proteins. They are therefore widely applied to analyze hematopoietic samples, where well-characterized panels of cell surface proteins are associated with distinct cell states, but have limited utility in other contexts, including neurodevelopment."
> — Introduction / p.1 · bears on: Claim 4, Axis A · CITE-seq-class methods capture only surface protein; intracellular/intranuclear protein remains an unmeasured modality in most contexts.

> "no existing approaches can quantify intracellular proteins (including phosphorylation states), transcriptional output, and chromatin profiling in the same biological system."
> — Introduction / p.1 · bears on: Claim 8, Axis A · states the prior gap in simultaneous multimodal (protein+RNA+chromatin) measurement.

> "while changes in PI3K/AKT/mTOR pathway activity did not drive genome-wide changes in chromatin accessibility, we observed a clear increase in pRPS6 levels within stimulated cells compared to inhibited cells independent of total RPS6 levels. This reflects a biological context where phosphorylation measurements are highly informative for distinguishing cellular states even when genome-wide modalities cannot."
> — Results: Phospho-seq simultaneously quantifies… / p.2 (Fig. 1M–P) · bears on: Claim 4, Axis A · phospho-protein state discriminates cell states that chromatin accessibility (a genome-wide modality) cannot — direct evidence of cross-modality non-substitutability.

> "only pSTAT3 levels (as opposed to total protein levels) correlated with STAT3 transcription factor activities… we conclude that… phosphorylated protein levels are more reflective of cellular state and transcription factor activities compared to total protein levels."
> — Results: Phospho-seq simultaneously quantifies… / p.2 (Fig. S1L) · bears on: Claim 4, Claim 5, Axis A (PTM) · the phospho-state, not total protein nor RNA, tracks functional TF activity.

> "While Phospho-seq exhibited a higher SI on average (mean SI = 1.26 vs. 0.74 for flow cytometry), we did not identify a statistically significant difference between the two (p = 0.375)… suggesting that our Phospho-seq data is comparable to gold-standard approaches."
> — Results: quantitative benchmarking / p.2 (Fig. S2C) · bears on: Claim 6, Standard · sequencing-based intracellular protein quantification is benchmark-comparable to flow cytometry (a quantitative cross-protocol comparison).

> "Comparing the mean expression of pRPS6 between gated populations in Phospho-seq, we observed quantitative agreement (R2 = 0.90)… With ASAP-seq, we observed a weaker correlation (R2 = 0.12)… We conclude that Phospho-seq exhibits best-in-class performance for technologies measuring protein and chromatin at single-cell resolution."
> — Results: quantitative benchmarking / p.2 (Fig. S2K, L) · bears on: Claim 6, Standard · ground-truth (FACS) vs sequencing benchmark; method-to-method quality varies sharply, underscoring comparability concerns across protocols.

> "we observed a large, previously unreported difference in pRPS6 signal between rods and cones, which we validated through immunofluorescent imaging. Photoreceptors are among the most metabolically demanding cell types in the body, requiring high levels of mTOR signaling, which in turn phosphorylates RPS6, to properly function."
> — Results: retinal organoids / p.3 (Fig. 2E–G) · bears on: Claim 5, Axis A · a functional/metabolic cell-state difference is visible only in the phospho-protein readout (and confirmed by imaging).

> "Our Phospho-seq protocol utilizes the 10x scATAC-seq kit to generate scalable and high-quality chromatin accessibility profiles but lacks transcriptomic measurements, which are highly valuable for fine-grained cell annotation and gene regulatory network reconstruction."
> — Results: incorporating transcriptomics / p.3 · bears on: Claim 4, Claim 8 · chromatin + protein still do not substitute for RNA; each modality contributes non-redundant information.

> "the simultaneous acquisition of multiple modalities came at a substantial cost in data quality and throughput when compared to either our existing Phospho-seq data, or scRNA-seq on retinal organoids. Specifically, we observed a 70% reduction in molecular sensitivity for scATAC-seq profiles and a 91% reduction for gene expression profiles."
> — Results: incorporating transcriptomics / p.3 (Fig. S4C, D) · bears on: Claim 10 · quantifies the throughput/quality penalty of measuring more modalities at once — the resolution × throughput × destructiveness trade-off made concrete.

> "We further observed a significant reduction in the staining index for both intracellular and intranuclear ADT levels, with a range of 45–70% reduction between three pairs of cell types… these data are consistent with previous studies that exhibit lower per-modality molecular sensitivity when using the 10x multiome kit, and demonstrate the inherent challenges for multimodal technologies to generate high-quality data from each measurement type."
> — Results: incorporating transcriptomics / p.3 (Fig. 3C, S4E) · bears on: Claim 10 · multimodal capture degrades protein-measurement quality too; generalizes the trade-off across modalities.

> "this workflow can successfully integrate distinct modalities collected in different experiments by leveraging a separately obtained multiomic dataset as a 'bridge', even if the bridge dataset has reduced technical quality… but requires that the multiomic dataset is biologically representative (i.e. inclusive of all cell types and states) of the single-modality datasets."
> — Results: incorporating transcriptomics / p.3 (Fig. 3D) · bears on: Claim 8, Claim 9, Standard · computational integration of separately-generated datasets is feasible but conditioned on biological representativeness — a comparability/standard requirement.

> "while it is possible to use the Phospho-seq workflow to perform experimental trimodal profiling, this comes with a cost in data quality and thus integrated analysis may result in improved data quality for multiple modalities."
> — Results: incorporating transcriptomics / p.4 · bears on: Claim 10, Claim 8 · explicit conclusion that experimental multiplexing trades off quality, motivating integration of separate high-quality unimodal datasets instead.

> "While SOX2 gene expression decreased at the initial stages of differentiation, we observed a developmental lag in the decrease of downstream modalities including SOX2 ADT levels and SOX2 transcription factor activity… we identified a specific stage of the developmental trajectory where protein and RNA levels were discordant and confirmed that in these cells, only SOX2 protein levels (and not RNA levels) were correlated with chromVAR scores."
> — Results: brain organoids / p.4 (Fig. S7B, C) · bears on: Claim 4, Axis B (temporal) · RNA and protein are temporally discordant; protein, not RNA, tracks functional activity at the lagged stage — RNA cannot stand in for protein dynamics.

> "integrated Phospho-seq data can perform multimodal characterization of the distinct temporal patterns and gene regulatory relationships that drive cellular dynamics."
> — Results: brain organoids / p.4 · bears on: Axis B (temporal) · claims temporal/dynamic characterization — note this is reconstructed from pseudotime over a snapshot, not paired real-time tracking (see Methods quote below).

> "The destiny package in R was used to create diffusion maps based on the lsi embeddings from these subset datasets. Monocle3 was then run on the diffusion maps to calculate pseudotime, setting the cell with the minimum value in diffusion component 1 as the origin."
> — Methods: Pseudotime and trajectory analysis / p.6 · bears on: Claim 3, Axis B (temporal) · the "trajectory" is computationally inferred pseudotime from a single destructive snapshot — time is reconstructed from a distribution of cells, not observed by tracking the same cell over time.

> "While CUT&Tag data revealed 331,131 GLI3 binding sites across the genome, only a small percentage (5108, 1.5%) of these were associated with differential accessibility (DA) upon GLI3 perturbation… we found that our Phospho-seq data for GLI3 could help predict which genomic regions would respond to perturbation."
> — Results: GLI3 co-factors / p.4–5 (Fig. 5C, G) · bears on: Claim 4, Claim 5 · single-cell protein-level measurement carries functional/regulatory information that a genome-wide binding map (CUT&Tag) does not — modality orthogonality at the functional level.

> "subcategories of glial cells we identified matched to different regions in the developing brain: GLI3+ glia and glial PCs were derived from the forebrain and telencephalon, and that S100B+ glia were from an equal distribution of non-telencephalic origin… these functional characteristics are known to vary across both cell types and brain regions."
> — Results: signaling network activity / p.4 (Fig. S9E) · bears on: Claim 7, Axis C (spatial) · signaling-state heterogeneity maps onto spatial/regional origin in the brain — but recovered here by reference-mapping to an atlas, not by direct spatial measurement (the assay is dissociative).

> "samples are dissociated into single-cells, fixed, permeabilized, hashed, stained for intracellular proteins with self-conjugated DNA-bound antibodies, and run through the 10X Genomics single-cell ATAC-seq protocol."
> — Results: Benchtop conjugation / p.1 · bears on: Claim 2, Axis C (spatial) · the workflow begins by dissociating tissue — like scRNA-seq, it discards tissue-level spatial organization.

> "we and others have found that simultaneous profiling of ATAC and RNA in cells or nuclei reduces the data quality associated with each modality… a bridge-based experimental design may represent a flexible alternative for multimodal analysis where only a subset of samples need to be profiled with multiomic technologies."
> — Discussion / p.5 · bears on: Claim 10, Claim 8, Claim 9 · author-conceded trade-off of simultaneous multimodal capture, plus a proposed standardizable design pattern (sparse multiomic "bridge" + many unimodal datasets).

> "applying Phospho-seq in concert with spatially-resolved profiling technologies may shed light on both intercellular and intracellular signaling networks."
> — Discussion / p.5 · bears on: Claim 2, Axis C (spatial) · the authors explicitly flag spatial resolution as a missing dimension and a future extension — the present method is spatially blind at tissue scale.

> "we designed custom panels to profile up to 64 intracellular proteins (including 20 phospho-states)… an expanded set of 40 paired cell-signaling antibodies."
> — Abstract/Introduction & brain-organoid Results / p.1, p.4 · bears on: Claim 6, Axis A · demonstrates that scalable single-cell intracellular + phospho-protein profiling is technically feasible at panel scale (antibody/sequencing-based).

> "more fine-grained annotation is challenging for chromatin accessibility measurements in the absence of transcriptomic data."
> — Results: retinal organoids / p.3 · bears on: Claim 4, Claim 8 · one modality (chromatin) is insufficient alone; resolving cell state needs complementary modalities.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 4 — modalities orthogonal, RNA/chromatin cannot substitute for protein | "phosphorylation measurements are highly informative… even when genome-wide modalities cannot" / Fig.1 | supports |
| Claim 4 — RNA ≠ protein dynamics | "only SOX2 protein levels (and not RNA levels) were correlated…" / Fig.S7 | supports |
| Claim 4 — protein vs binding-map | "CUT&Tag… 331,131 binding sites… 1.5%… Phospho-seq… could help predict" / Fig.5 | supports |
| Claim 5 — protein/PTM indispensable for function & phenotype | "phosphorylated protein levels are more reflective of cellular state" / Fig.S1L; rods-vs-cones pRPS6 / Fig.2 | supports |
| Claim 6 — high-throughput single-cell (phospho)proteomics feasible | "up to 64 intracellular proteins (including 20 phospho-states)" / Intro | supports |
| Claim 2 — dissociation loses spatial | "samples are dissociated into single-cells…" / Results; "in concert with spatially-resolved profiling…" / Discussion | supports (as foil — method is itself dissociative) |
| Claim 3 — destructive measurement → time only inferred | "Monocle3… to calculate pseudotime" / Methods; "developmental lag… developmental trajectory" / Fig.S7 | nuances |
| Claim 7 — spatial/regional origin shapes cell signaling state | "subcategories of glial cells… matched to different regions" / Fig.S9 | supports (via reference-mapping, not direct spatial assay) |
| Claim 8 — multimodal modalities orthogonal, need integration | "lacks transcriptomic measurements, which are highly valuable…"; bridge integration / Fig.3 | supports |
| Claim 9 — data islands, comparability, standards | "integrate distinct modalities collected in different experiments… requires… biologically representative" / Fig.3 | supports / nuances |
| Claim 10 — resolution × throughput × destructiveness trilemma | "70% reduction… scATAC… 91% reduction… gene expression"; "45–70% reduction" SI; "reduces the data quality associated with each modality" / Fig.3, S4, Discussion | supports |
| Axis A (modality: proteome / PTM-protein-state) | entire paper; "post-translational modifications"; pRPS6/pSTAT3/pERK panels | supports |
| Axis B (temporal) | pseudotime trajectory; SOX2 protein–RNA temporal discordance / Fig.S7 | nuances |
| Axis C (spatial) | dissociative workflow; glial regional origin; spatial profiling as future work | challenges (method is spatially blind) |
| Standard / integration | staining-index cross-protocol benchmark; bridge integration representativeness requirement | supports / nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1M–P | Pilot: PI3K/AKT/mTOR modulation (EGF activate / PX-866 inhibit) raises pRPS6 in stimulated K562 independent of total RPS6, with no genome-wide chromatin-accessibility change → phospho-state orthogonal to chromatin. |
| Fig. 1G,H / S1I | ADT staining indices distinguishing iPSC vs K562: OCT4 SI 1.22, SOX2 SI 0.56, GATA1 SI 1.29 (all p < 0.001). |
| Fig. S2A–C | Phospho-seq vs flow cytometry on K562/HEK: mean SI 1.26 vs 0.74; no significant difference (p = 0.375). |
| Fig. S2K,L | Ground-truth (FACS-gated) vs sequencing for pRPS6: Phospho-seq R2 = 0.90; ASAP-seq R2 = 0.12. |
| Fig. 2E–G | Retinal organoids (34-week; 8,136 cells): pRPS6 higher in cones than rods; validated by immunofluorescence (240 rods, 64 cones). |
| Fig. 3C / S4C,D | Phospho-seq-multi (10x multiome) vs single-modality: 70% drop in scATAC sensitivity, 91% drop in RNA sensitivity, 45–70% drop in ADT staining index (1,474 cells; medians 866 RNA UMIs, 8,326 ATAC fragments, 39 ADT UMIs). |
| Fig. S7B–F | Brain-organoid forebrain trajectory (1,578 cells): SOX2 protein/TF-activity lags SOX2 RNA decline; at the discordant stage only protein (not RNA) correlates with chromVAR. |
| Fig. 4E–I | Diencephalic vs telencephalic lineage: elevated MAPK/ERK phosphorylation in diencephalon; pRPS6 variability tracks RPS6KA1 (ERK) accessibility, not RPS6KB1 (mTOR). |
| Fig. 5C–G | GLI3: CUT&Tag 331,131 binding sites, only 5,108 (1.5%) differentially accessible on KO; DA regions enriched for HD/2 motifs (median fold-enrichment 3.02) > GLI3 motif (2.11); Phospho-seq GLI3 protein predicts DAR responsiveness (p = 2.2×10⁻¹⁶). |
| Fig. 6 / S14 | GRN inference: 5,033 OTX2-linked peaks; 3,200 OTX2 targets (1,772 activating, 1,428 repressive); 481 pRPS6:TEAD1 CREs; 582 pSTAT3 peak-gene links validated against ChIP-seq. |
| Datasets | Brain: 9,028 (≈9,034) Phospho-seq cells + 19,280-cell scRNA reference + 4,958-nucleus multiome bridge, four iPS donors. Retina: 8,136 Phospho-seq cells; reference 22,011 cells, bridge 4,926 cells. |

---

## Primary Sources Behind Key Quotes
- ASAP-seq (the only prior protein+chromatin single-cell method, benchmarked against here) → Mimitou, E. P. et al. *Nat. Biotechnol.* 39:1246–1258 (2021), ref #18.
- Bridge integration / dictionary learning (the computational integration used to add RNA) → Hao, Y. et al. *Nat. Biotechnology* 42:293–304 (2024), ref #23.
- NEAT-seq (intranuclear protein + SSB background reduction; multiome trimodal) → Chen, A. F. et al. *Nat. Methods* (2022), ref #16.
- CITE-seq (digital, UMI-based protein quantification dynamic range) → Stoeckius, M. et al. *Nat. Methods* 14:865–868 (2017), ref #15.
- TEA-seq / lower per-modality sensitivity of 10x multiome → Swanson, E. et al. *Elife* 10:e63632 (2021), ref #20.
- Multiome reduces per-modality quality (cortex) → Trevino, A. E. et al. *Cell* 184:5053–5069 (2021), ref #49.
- Retinal-organoid reference + multiome bridge datasets → Wahle, P. et al. *Nat. Biotechnol.* (2023), ref #32.
- Brain-organoid regulome + GLI3 perturbation/CUT&Tag + multiome → Fleck, J. S. et al. *Nature* 621:365–372 (2023), ref #37.
- Staining index metric definition → Maecker, H. T. et al. *Cytometry A* 62:169–173 (2004), ref #30.

---

## Flags
- [ ] Metadata partially unverified: Journal confirmed as **Nature Communications** (from peer-review notice and DOI prefix 10.1038/s41467) and year **2025** (© The Author(s) 2025); the article/volume/page number is not printed in the cleaned text (Nature Communications uses an article-number scheme; DOI 10.1038/s41467-025-56590-7 is the locator). Received/accepted/published exact dates are **not present** in the cleaned MD.
- [ ] OCR normalization (NOT verbatim glyph-for-glyph): the cleaned source encodes the "fi"/"fl" ligatures as `<sup>fi</sup>`/`<sup>fl</sup>` and garbles some statistics (e.g., superscript R², stray spacing in p-values). Quotes above are normalized to readable form (e.g., "profiling", "flow", "R2 = 0.90", "p = 0.375") with wording otherwise preserved — verify exact figures against the raw file before publication.
- [ ] Cell-count minor inconsistency in source: brain-organoid final dataset stated as "9,028 cells" (Results) and "9,034 cells" (Methods, ADT processing); retinal Phospho-seq stated as 8,136 cells; reference/bridge counts differ slightly between Results (22,011 / 4,926) and other mentions — use Methods numbers for citation.
- [ ] Read at source (cite first-hand, not via this paper): for the spatial gap → spatial-omics references (ref #77 Deng et al. *Nature* 2022); for trajectory/pseudotime limits → Monocle3 (ref #41 Cao et al. *Nature* 2019) and destiny (ref #42); for the multiome quality-loss claim → Swanson 2021 (#20) and Trevino 2021 (#49); for bridge integration → Hao 2024 (#23).
- [ ] Scope note: this paper's protein modality is **antibody/sequencing-based (ADT)**, not mass-spectrometry spatial proteomics (the Guo-lab capability the perspective foregrounds). It is evidence that single-cell intracellular/phospho-protein profiling is feasible and orthogonal to RNA, but it is a different technology platform — do not conflate with MS-based high-throughput spatiotemporal proteomics when deploying for Claim 6.
- [ ] Temporal caveat: all "trajectory"/"temporal"/"dynamics" claims rest on **computational pseudotime over a single destructive snapshot** (diffusion maps + Monocle3), not paired longitudinal observation — supports Claim 3's premise rather than refuting it.
