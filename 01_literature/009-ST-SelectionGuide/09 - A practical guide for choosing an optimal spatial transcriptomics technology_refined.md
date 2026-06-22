# A practical guide for choosing an optimal spatial transcriptomics technology from seven major commercially available options — Source Index

**Authors:** Hyun Ju Lim, Ye Wang, Anton Buzdin, Xinmin Li
**Journal / Venue:** unverified — not printed in source text; "REVIEW, Open Access"; corresponding/first authors affiliated with UCLA (NIH grants R01DE29173, P30CA016042); see Flags
**DOI:** not found in text (only a bioRxiv DOI appears inside reference 8); see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/09 - A practical guide for choosing an optimal spatial transcriptomics technology_cleaned.md

---

## In One Sentence
A practical review that outlines the core chemistry of seven commercially available spatial transcriptomics platforms (10X Visium, Visium HD, GeoMx DSP, Stereo-seq, Merscope, Xenium, CosMx SMI), groups them by resolution, compares their technical parameters (resolution, gene/protein coverage, sensitivity, throughput, cost), and gives decision guidance for matching a platform to a biological question.

## Orientation (non-binding)
This paper sits squarely on our **spatial axis (Axis C)** and on the measurement-end **trade-off claim (Claim 10)**: it opens by asserting that spatial information is destroyed by bulk and single-cell sequencing, then documents in detail how no current spatial platform simultaneously achieves whole-transcriptome coverage, true single-cell resolution, high throughput, and multimodality — every platform trades one against another. It also feeds the **modality-narrowness critique (Axis A / Claim 4)**: these are RNA-first technologies, and where protein is offered it is a small panel (handful to ~68 proteins). It can serve as **support** (spatial loss is real; spatial context is essential for microenvironment/perturbation questions) and as a **factual substrate / mild foil** (it treats spatial transcriptomics as the frontier, while conceding the field is "early stage," cross-platform "single-cell resolution" is "misleading," and benchmarks disagree — useful for our standards/comparability claim, Claim 9). It is silent on the temporal axis (snapshots of fixed tissue only).

---

## Load-Bearing Excerpts

> "However, this functionally critical spatial information is lost in widely used bulking sequencing and popular single cell sequencing due to the disruption of tissue structural organization during the sample process."
> — Background · bears on: Claim 2 (scRNA/bulk lose spatial info), Axis C · the paper's framing motivation: dissociation/bulk destroys tissue spatial organization.

> "comprehending the precise locations where genes are expressed within highly structured tissues is essential for elucidating various fundamental biological processes, such as gene functions, gene-gene interactions, cell-cell communication, dynamic molecular and cellular processes, and microenvironmental influences [1]."
> — Background · bears on: Claim 7 (spatial/microenvironment matters), Axis C · states why spatial location is functionally necessary.

> "Spatial transcriptomics technology enables the mapping of gene expression within tissues, allowing researchers to visualize the spatial distribution of RNA molecules and gain insights into cellular organization, interactions, and functions in their native environments."
> — Abstract · bears on: Axis C, Claim 2 · defines what spatial transcriptomics recovers that dissociated methods do not.

> "In general, imaging-based technologies ofer singlecell or subcellular resolution, high RNA detection sensitivity, specificity, and reproducibility. However, they are limited to gene panels ranging from several hundred to six thousand genes, require longer imaging times varying from two days to a week or more, and have low throughput. Sequencing-based technologies provide whole transcriptome analysis, though most lack single-cell resolution. They typically have lower RNA capture eficiency and detection sensitivity compared to imaging-based technologies, especially for low-abundance transcripts [20]."
> — Sequencing-based technologies (closing paragraph) · bears on: Claim 10 (resolution × coverage × throughput × sensitivity trade-off) · the central trade-off axis: gene coverage vs single-cell resolution vs throughput vs sensitivity.

> "The main limitation is the lack of single-cell resolution, which is due to the ≥ 55 μm spot size in Visium (the average size of a mammalian cell is typically around 10  μm in diameter) and the ≥ 50-cell ROI size (Vendor recommended) in GeoMx. Consequently, each spot or ROI captures transcripts from multiple cell types, resulting in an average or mixed gene expression signal across these cell types."
> — Group 1 (G1) · bears on: Claim 10, Axis C · spot/ROI larger than a cell yields mixed multi-cell-type signal.

> "To address this limitation, deconvolution tools have been developed and commonly used in analyzing G1 data. By integrating spatial transcriptomic data with singlecell RNA sequencing data from adjacent tissue sections, deconvolution can assign specific gene expression profiles to distinct cell types within each spot, allowing for a more accurate understanding of cellular architecture in tissues [21, 22]."
> — Group 1 (G1) · bears on: Claim 8 (multimodal/cross-dataset integration) · computational integration of spatial + scRNA-seq used to recover cell-type signal.

> "However, it is important to note that feature size is not the only factor influencing actual resolution; lateral difusion during tissue permeabilization also significantly impacts the spatial accuracy of transcript detection. Stereoseq has shown notable lateral difusion in some tissues [2]."
> — Group 2 (G2) · bears on: Claim 9 (comparability/standards), Claim 10 · nominal feature size overstates real resolution; diffusion is a confounder.

> "Additionally, the term ‘single-cell resolution’ can be somewhat misleading. Platforms like Visium HD and Stereo-seq can detect only a few hundred to a thousand genes when data are exported to achieve single-cell scale/resolution. This level of resolution comes at the expense of a reduced number of detectable genes."
> — Group 2 (G2) · bears on: Claim 9, Claim 10 · marketing-term "single-cell resolution" is qualified; resolution and gene count trade off.

> "As of now, sequencing-based spatial technologies are not yet capable of delivering whole-transcriptome data at true single-cell resolution."
> — Group 2 (G2) · bears on: Claim 10 · explicit author concession that whole-transcriptome × true single-cell resolution is currently unattainable.

> "Typically, if the goal is to generate hypotheses, sequencing-based platforms like 10X Visium and GeoMx are ideal, as they provide an unbiased view of the whole transcriptome. If the aim is to test hypotheses, imaging-based platforms such as Xenium, CosMx, and Merscope are optimal, ofering in-depth analysis of a specific gene panel at single-cell resolution. For those seeking flexible control over both resolution and the number of genes analyzed, Visium HD or Stereo-seq are better choices. By adjusting the bin size of the data output, you can balance resolution with gene coverage: lower resolution supports whole transcriptome analysis, while higher resolution detects fewer genes."
> — Number of genes profiled · bears on: Claim 10 · the resolution↔gene-coverage trade-off stated as an explicit user-tunable knob (bin size).

> "As of November 28, 2024, G2 group is limited to transcriptome analysis only."
> — Group 2 (G2) · bears on: Axis A (modality narrowness) · highest-resolution sequencing platforms are RNA-only.

> "Decide whether you’re interested in profiling RNA alone or both RNA and protein. As of November 28, 2024, Visium HD, Stereoseq, and Xenium are limited to transcriptomic (RNA) analysis only. The remaining platforms are capable of both RNA and protein profiling."
> — Analyte · bears on: Axis A · spatial multimodality (RNA+protein) only partially available across platforms.

> "Merscope enables simultaneous RNA and protein profiling on the same slide, while CosMx performs this sequentially, and Xenium does not currently support protein panel."
> — Group 3 (G3) · bears on: Axis A · spatial RNA+protein co-measurement exists but is platform-limited and modest in scale.

> "the spatial content in the dataset is crucial for answering your questions that cannot be satisfactorily addressed by other simpler or more cost-efective technologies."
> — Defining your biological questions · bears on: Claim 2, Claim 7 · spatial content is non-substitutable for certain questions.

> "Examples of such questions include understanding how tumor cells interact with immune cells, how the tumor microenvironment afects tumor metastasis, and how drug treatment activates immune pathways, facilitates immune cell infiltration, and impacts tumor cell viability. If your aim is to address these dynamic interaction processes in situ, spatial context is essential."
> — Defining your biological questions · bears on: Claim 7 (microenvironment alters cell state and perturbation/drug response), Axis C · names microenvironment and drug-perturbation responses as questions requiring in-situ spatial context.

> "Imaging-based platforms generally ofer superior detection sensitivity and specificity compared to sequencing-based platforms. Among sequencing technologies, probe-based methods outperform polyAbased approaches, particularly for detecting lowly expressed genes. Studies indicate that 10X Xenium and Merscope technologies provide better sensitivity and specificity than CosMx [23, 24]. Probe-based Visium technology is considered more efective than Stereo-seq [2]."
> — Sensitivity & specificity · bears on: Claim 9 (cross-platform performance differs), Claim 10 · platform performance varies by chemistry; benchmarks rank them differently.

> "Spatial transcriptomics technologies are still in the early stages of development and are rapidly evolving. The performance of each technology is likely to improve over time with ongoing advancements. Therefore, this practical guide will need to be updated accordingly."
> — Sensitivity & specificity (closing) · bears on: Claim 9, Claim 10 · the field is immature and the standard/comparison landscape is unstable.

> "Spatial technologies are advancing rapidly, with key areas for further improvement, such as enhancing spatial resolution without significantly reducing the number of detectable genes for sequencing-based technologies and increasing the number of profiled genes without substantially extending scanning time for imaging-based technologies."
> — Move forward · bears on: Claim 10 · names the two open trade-offs directly: resolution↔gene number (sequencing) and gene number↔scanning time/throughput (imaging).

> "One future direction for spatial genomics is the development of 3D spatial multiomics technologies. StellarOmics’ imaging-based in-situ sequencing technology shows great promise in this area [25]. Unlike the standard 5–10 μm thick sections used in current spatial technologies, StellarOmics can image tissue sections up to 200 μm thick, enabling multi-cell layer profiling for deeper insights into tissue architecture and function."
> — Move forward · bears on: Axis C (3D/depth), Axis A (multiomics), Claim 8 · current spatial methods are thin 2D sections; 3D spatial multiomics is named as the future direction.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA/bulk lose spatial info | "this functionally critical spatial information is lost…" / Background | supports |
| Axis C — spatial resolution needed | "visualize the spatial distribution of RNA molecules…" / Abstract; "spatial content… is crucial…" / Defining questions | supports |
| Claim 7 — microenvironment alters cell state & perturbation response | "how the tumor microenvironment afects tumor metastasis… drug treatment…" / Defining questions | supports |
| Claim 10 — resolution × throughput × destructiveness trade-off | "not yet capable of delivering whole-transcriptome data at true single-cell resolution" / G2; "enhancing spatial resolution without… reducing… detectable genes" / Move forward | supports |
| Claim 9 — cross-platform incomparability / lack of standards | "the term 'single-cell resolution' can be somewhat misleading" / G2; "still in the early stages… will need to be updated" / Sensitivity | supports / nuances |
| Axis A — modality narrowness (RNA-centric) | "limited to transcriptomic (RNA) analysis only" / Analyte; "G2 group is limited to transcriptome analysis only" / G2 | supports |
| Claim 8 — multimodal / cross-dataset integration | "integrating spatial transcriptomic data with singlecell RNA sequencing data… deconvolution" / G1; "3D spatial multiomics" / Move forward | supports |
| Claim 6 — high-throughput spatial proteomics feasible | protein panel sizes (35/570/6/68 proteins) / Table 1; "Merscope enables simultaneous RNA and protein…" / G3 | nuances (shows spatial protein exists but is small-scale) |
| Claim 3 / Axis B — temporal trajectory, destructive sampling | (not addressed; all platforms snapshot fixed/sectioned tissue) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 | Comparative summary of 7 platforms across: suitable species, applicable tissue (FF/FFPE/FxF/cultured), capture area, gene number, protein number, resolution, sequencing reads, hands-on/scanning time, specificity, cost, experimental aim. (OCR partly garbled — see Flags.) |
| Table 2 | Simplified decision guide: maps key parameters (species, hypothesis generation vs testing, resolution, gene/protein profiled, tissue size, cost relative to cells analyzed) to the 8 platform variants. |
| Fig. 1 | Probe design / hybridization / signal amplification / gene decoding schematics for the three imaging platforms (Xenium 8 padlock probes + RCA; Merscope 30–50 probes, binary barcode with four "1"s; CosMx 5 probes, 16 sub-domains, color×position code). |
| Fig. 2 | Feature/ROI size and spatial-decoding for Visium (55 μm), Visium HD (2 μm), Stereo-seq (0.22 μm), and GeoMx (ROI + UV-cleavable DSP barcode). |
| Resolution numbers | Visium 55 μm spot; Visium HD 2 μm spot (no gap); Stereo-seq 0.2 μm DNB, 0.5 μm center-to-center (feature ~0.22 μm); mammalian cell ~10 μm diameter; GeoMx ROI ≥50 cells (vendor-recommended). |
| Gene coverage | Sequencing (Visium/Visium HD/GeoMx/Stereo-seq): whole transcriptome. Imaging panels: Merscope ~500 predesigned +~500 custom (full custom up to 1000 genes, any species); Xenium up to 5000 +~100 custom; CosMx up to 6000 +~200 custom. Imaging range overall "several hundred to six thousand genes." Single-cell-scale export: only "a few hundred to a thousand genes." |
| Protein counts | Visium 35 (sequential, separate slide from RNA); GeoMx 570 (sequential); Merscope 6 (simultaneous co-imaging with RNA, same slide); CosMx 68 (sequential). Visium HD / Stereo-seq / Xenium: protein not available. |
| Cost (UCLA estimate) | Visium $3293+seq; GeoMx $3837+seq; Visium HD $6645+seq; Stereo-seq $3054+seq; Merscope ~$6733; Xenium $3878; CosMx $6325. (Visium HD ~2× Stereo-seq for library construction despite fewer cells; Xenium most affordable imaging platform.) |
| Time | Hands-on: Visium 1–2 d, GeoMx 3 d, Visium HD 2 d, Stereo-seq 2–3 d, Merscope 4–5 d, Xenium 3 d, CosMx 2 d. Imaging/scanning: Merscope 1–2 d, Xenium 2–6 d, CosMx 3–7 d. |
| Capture area | Visium 6.5 × 6.5 mm (×4 areas V1 / ×2 V2); GeoMx 36 × 14 mm; Visium HD 6.5 × 6.5 mm; Stereo-seq 10 × 10 mm or 20 × 30 mm; Merscope 18 × 22 mm (approx.); Xenium ~10–22 mm; CosMx ~15–20 mm. (Table OCR partly scrambled.) |

---

## Primary Sources Behind Key Quotes
- Spatial information lost by bulk/single-cell; "spatially resolved transcriptomics and beyond" → Crosetto N, Bienko M, van Oudenaarden A. Nat Rev Genet. 2015;16(1):57–66 (ref #1).
- Lateral diffusion in Stereo-seq; probe-based Visium > polyA Stereo-seq; systematic sequencing-platform comparison → You Y, Fu Y, Li L, et al. Nat Methods. 2024;21(9):1743–54 (ref #2).
- Imaging-platform benchmarking (Xenium/Merscope > CosMx sensitivity & specificity) → Wang H, Huang R, Nelson J, et al. bioRxiv. 2023 (ref #23); Hartman A, Satija R. bioRxiv. 2024 (ref #24).
- Deconvolution integrating spatial + scRNA-seq → Li Y, Li N, Qi J, et al. Genome Biol. 2024;25(1):271 (ref #21); Zhang Y, Liu X, Yu Z, et al. Comput Struct Biotechnol J. 2022;21:176–84 (ref #22).
- GeoMx digital spatial profiling of proteins and RNA → Merritt CR, Ong GT, Church SE, et al. Nat Biotechnol. 2020;38(5):586–99 (ref #7).
- CosMx high-plex RNA + protein at subcellular resolution → He S, Bhatt R, Brown C, et al. Nat Biotechnol. 2022;40(12):1794–806 (ref #12).
- Stereo-seq spatiotemporal atlas (DNB arrays) → Chen A, Liao S, Cheng M, et al. Cell. 2022;185(10):1777– (ref #9).
- 3D spatial multiomics (StellarOmics, thick-tissue in-situ sequencing) → Sui X, Lo JA, Luo S, et al. bioRxiv. 2024 (ref #25).

---

## Flags
- [ ] Metadata unverified: Journal/venue name does not appear in the source text (the body shows only "REVIEW / Open Access"). UCLA affiliation and NIH grants R01DE29173 / P30CA016042 are stated; venue must be confirmed from the original PDF/publisher page before citing.
- [ ] DOI not found in source text: no article DOI is printed; the only DOI in the file (10.1101/2024.06.04.597233) belongs to reference 8 (a bioRxiv preprint), not to this paper.
- [ ] Source inconsistency / OCR garble: Table 1 numeric cells are partially scrambled in the cleaned MD (resolution, protein-count, capture-area, and reads columns are misaligned). Specific table numbers transcribed here are best-effort — verify each against the original figure/table.
- [ ] Date stated in text: "Received: 15 October 2024 / Accepted: 10 January 2025 / Published online: 20 January 2025." Multiple platform statements are time-stamped "As of November 28, 2024" — capabilities (e.g., which platforms add protein) are explicitly volatile.
- [ ] Temporal axis not addressed: the paper covers only fixed/sectioned-tissue snapshots and is silent on time-course/trajectory; relevant as an absence for Claim 3 / Axis B, not as a stated claim.
- [ ] Read at source: You Y et al., Nat Methods 2024 (ref #2) and the imaging benchmarks Wang H et al. / Hartman & Satija (refs #23, #24) are the primary comparability evidence behind this paper's sensitivity/specificity and "single-cell-resolution-is-misleading" claims — read first-hand for Claim 9/10.
