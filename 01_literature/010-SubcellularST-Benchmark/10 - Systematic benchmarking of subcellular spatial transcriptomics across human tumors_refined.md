# Systematic benchmarking of high-throughput subcellular spatial transcriptomics across human tumors — Source Index

**Authors:** Pengfei Ren, Rui Zhang, Yunfeng Wang, Peng Zhang, Ce Luo, Suyan Wang, Xiaohong Li, Zongxu Zhang, Yanping Zhao, Yufeng He, Haorui Zhang, Yufeng Li, Zhidong Gao, Xiuping Zhang, Yahui Zhao, Zhihua Liu, Yuanguang Meng, Zhe Zhang & Zexian Zeng
**Journal / Venue:** Nature Communications, 2025 (volume/article-number not printed in text; see Flags)
**DOI:** doi:10.1038/s41467-025-64292-3
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/10 - Systematic benchmarking of subcellular spatial transcriptomics across human tumors_cleaned.md
*(Received 26 Jan 2025; Accepted 15 Sep 2025; Published online 17 Oct 2025. Section names below are jump-back anchors into the raw file.)*

---

## In One Sentence
The authors generated serial tissue sections from three human tumors (colon adenocarcinoma, hepatocellular carcinoma, ovarian cancer) under uniform processing and benchmarked four commercial high-throughput, subcellular-resolution spatial transcriptomics (ST) platforms (Stereo-seq v1.3, Visium HD FFPE, CosMx 6K, Xenium 5K) against orthogonal CODEX protein profiling and matched scRNA-seq, scoring sensitivity, specificity, diffusion, segmentation, annotation, clustering, and transcript–protein concordance across an 8.13-million-cell multi-omics resource.

## Orientation (non-binding)
Sits squarely on the **spatial axis (Axis C)** and the **standard/comparability cross-cutting axis**: its entire motivation is that prior ST benchmarks were non-comparable (varying conditions, no consistent ground truth), so it feeds Claim 2 (scRNA-seq loses spatial → spatial omics), Claim 9 (data islands / cross-study non-comparability / need for unified benchmarking & ground truth), and Claim 10 (measurement trade-offs across resolution / throughput / sensitivity / diffusion). It is also a concrete instance of **cross-modal ground-truthing** — CODEX protein + scRNA-seq used as references for an RNA-spatial assay — bearing on Claims 4/8. It can serve as a **foil too**: the study is transcriptome-centric (protein appears only as a 16-plex reference), purely snapshot/destructive with no temporal dimension, and explicitly calls for "nondestructive spatial profiling" and "integration with multiomic modalities" as future work — direct ammunition for Claim 3 (temporal/destructiveness) and the multimodal-integration argument. Downstream agent decides the role.

---

## Load-Bearing Excerpts

> "Spatially resolved transcriptomics integrates high-throughput transcriptomic profiling with spatially contextualized tissue architecture, bridging the gap in single-cell RNA sequencing (scRNA-seq) by linking molecular profiles to their spatial context. With preserved spatial information, this technology offers unprecedented insights into cellular states, intercellular interactions, and tissue organization."
> — Introduction · bears on: Claim 2, Axis C · positions ST as the technology that restores the spatial context that scRNA-seq lacks.

> "in cancer biology, it provides detailed characterization of tumor microenvironments and immune landscapes."
> — Introduction · bears on: Claim 7, Axis C · spatial profiling resolves the tumor microenvironment / immune landscape.

> "These complementary approaches underscore the strengths of ST, with sST providing unbiased transcriptome-wide coverage and iST offering high resolution and sensitivity for the detection of target genes."
> — Introduction · bears on: Claim 10 · names the core sequencing-based vs imaging-based trade-off (unbiased breadth vs targeted resolution/sensitivity).

> "While these studies provide valuable insights, they primarily focus on ST technologies with lower spatial resolution or limited gene panel sizes. Furthermore, many benchmarking studies rely on public datasets generated under varying experimental conditions or with varying tissue types, which often lack consistent ground truth data for robust evaluation. As a result, existing efforts offer only a partial understanding of the latest advancements in ST technologies. This underscores the urgent need for a systematic benchmarking study conducted under unified experimental conditions to comprehensively evaluate the performance and comparative strengths of current high-resolution, high-throughput ST platforms."
> — Introduction · bears on: Claim 9, Standard axis · prior datasets were generated under varying conditions and lack consistent ground truth, making them non-comparable — the explicit case for unified-condition benchmarking.

> "Spatial transcriptomics has undergone remarkable advancements, with commercial platforms now achieving subcellular resolution and high-throughput gene detection."
> — Introduction · bears on: Claim 6, Axis C, Claim 10 · subcellular spatial resolution at high gene throughput is now commercially available.

> "To establish ground truth datasets, we profile proteins on tissue sections adjacent to all platforms using CODEX and perform single-cell RNA sequencing on the same samples."
> — Abstract · bears on: Claim 4, Claim 8, Standard axis · protein (CODEX) and scRNA-seq used as orthogonal cross-modal references for evaluating an RNA-spatial assay.

> "The uniformly generated and processed multi-omics dataset could advance computational method development and biological discoveries."
> — Abstract · bears on: Claim 1, Standard axis · uniform multi-omics data positioned as input for computational method development.

> "The resulting uniformly generated, processed, and annotated multi-omics dataset, comprising 8.13 million cells, serves as a valuable resource for advancing computational method development and enabling biological discoveries."
> — Introduction · bears on: Claim 1, Standard axis · scale and uniformity of the resource (8.13M cells) framed as method-development fuel.

> "Stereo-seq v1.3, Visium HD FFPE, and Xenium 5K showed high correlations with scRNA-seq. Although CosMx 6K detected a higher total number of transcripts than Xenium 5K, its gene-wise transcript counts showed substantial deviation from matched scRNA-seq reference."
> — Results: Evaluation of molecular capture efficiency across entire gene panels · bears on: Claim 8, Claim 10, Standard axis · cross-modal/cross-platform concordance varies by platform; higher raw counts ≠ higher fidelity.

> "Visium HD FFPE and Xenium 5K showed higher concordance with CODEX than Stereo-seq v1.3 and CosMx 6K, respectively."
> — Results: Evaluation of transcript identification and localization accuracy · bears on: Claim 4, Claim 8, Standard axis · transcript-level spatial patterns benchmarked against an orthogonal protein modality (CODEX).

> "Compared to the ST platforms, scRNA-seq consistently detected more transcripts and genes per cell... However, when restricting the analysis to a shared gene set (2522 genes), the iST platforms demonstrated comparable transcripts and genes per cell to scRNA-seq."
> — Results: Evaluation of the single-cell segmentation · bears on: Claim 10 · dissociated scRNA-seq retains a per-cell depth advantage over spatial assays at whole-panel scale; gap narrows on shared genes.

> "In COAD samples, ST data revealed substantial coexpression of the epithelial marker and immune markers and within the same cell... The co-expression levels observed in ST data were notably higher than those observed in scRNA-seq."
> — Results: Evaluation of the single-cell segmentation · bears on: Claim 10, Axis C · spatial assays show artificial within-cell co-expression (segmentation/spillover artifact) absent from scRNA-seq.

> "scRNA-seq consistently exhibited lower co-expression than ST platforms. Among ST platforms, Xenium 5K showed the greatest reduction in artificial co-expression after segmentation, indicating better single-cell segmentation results."
> — Results: Evaluation of the single-cell segmentation · bears on: Claim 10, Axis C · single-cell segmentation quality is a key differentiator of spatial single-cell fidelity.

> "Clustering performance, evaluated using the average silhouette score, showed that scRNA-seq provided the most effective separation of cell populations. Among the ST platforms, iST technologies achieved better resolution of transcriptomic differences between cell clusters, highlighting the advantage of their higher spatial resolution."
> — Results: Evaluation of cell clustering and cell type annotation · bears on: Claim 10 · dissociated scRNA-seq still gives the cleanest cell-state separation; among spatial assays higher resolution helps.

> "Furthermore, multimodal cell segmentation enabled the identification of multinucleated cells, including neutrophils and hepatocytes, which were poorly resolved using nucleus-only segmentation approaches."
> — Results: Evaluation of cell clustering and cell type annotation · bears on: Claim 8, Axis C · multimodal (membrane + nuclear + cytoplasm) staining improves segmentation that single-channel/nucleus-only misses.

> "Spatial clustering also enabled the identification of spatially distinct cellular subtypes... spatial clustering revealed distinct subsets of CD8+ T cells, those infiltrating the tumor versus those positioned at the periphery, based on their spatial co-localization with cancer cells. This highlights the utility of spatial clustering in characterizing immune cell localization and heterogeneity within the TME."
> — Results: Evaluation of spatial clustering and spatial pathway enrichment · bears on: Claim 7, Axis C · spatial position (infiltrating vs peripheral) defines functionally distinct cell subsets within the microenvironment.

> "Our findings provide practical guidance for selecting ST platforms based on study objectives. For single-cell level analyses, iST platforms are preferable due to their use of multichannel staining and full-cell segmentation, which enable more accurate cell boundary delineation and reduce transcript spillover... In contrast, for spatial analyses focused on tissue-region level patterns, sST platforms may be more suitable due to their broader gene coverage, which improves sensitivity for pathway-level enrichment analyses."
> — Discussion · bears on: Claim 10, Standard axis · no single platform wins; the right data depends on the question — single-cell resolution vs transcriptome-wide region-level coverage is a forced trade-off.

> "For iST technologies, expanding toward whole-transcriptome coverage while maintaining high specificity and detection efficiency is a critical frontier. However, optical crowding remains a limiting factor, as larger gene panels may reduce detection efficiency due to signal overlap."
> — Discussion · bears on: Claim 10 · throughput vs specificity tension for imaging-based ST — optical crowding caps panel expansion (resolution × throughput trade-off).

> "For sST platforms, improvements in spatial resolution, control of transcript diffusion, and accurate segmentation are needed to limit transcript leakage from neighboring cells."
> — Discussion · bears on: Claim 10, Axis C · sequencing-based ST trades single-cell precision for breadth; transcript diffusion/leakage limits subcellular accuracy.

> "This consideration is especially critical for FFPE samples relative to FF samples, as FFPE embedding can compromise RNA integrity. The resulting RNA fragmentation increases the likelihood of transcript leakage during the permeabilization process."
> — Discussion · bears on: Claim 10, Standard axis · sample-preparation chemistry (FFPE vs fresh-frozen) is itself a confounder of data quality and comparability.

> "The development of three-dimensional spatial transcriptomics for thick tissue sections, relaxation of sample input constraints, progress in nondestructive spatial profiling, and integration with multiomic modalities will collectively expand the scope, accessibility, and impact of ST technologies in both research and clinical settings."
> — Discussion · bears on: Claim 3, Claim 8, Axis B, Axis C · field-stated future needs name nondestructive profiling (temporal enabler), 3D spatial, and multiomic integration as open gaps.

> "The tissue samples were destroyed after the analysis."
> — Methods: Human sample collection and preprocessing · bears on: Claim 3, Axis B · measurement is terminal/destructive — the same tissue cannot be re-observed.

> "Second, CODEX was performed on adjacent tissue sections instead of the original ST sections, which provided essential reference but also introduced morphological discrepancies that may impact direct comparisons across platforms."
> — Discussion (Limitations) · bears on: Claim 8, Standard axis · cross-modal pairing here is on adjacent (not same) sections — a concession that true co-registered multimodal measurement on one sample is not achieved.

> "Lastly, as our study exclusively used freshly collected samples, the generalizability of our findings to archived or long-term stored samples remains unclear, underscoring the need for further validation in a broader range of sample types and conditions."
> — Discussion (Limitations) · bears on: Claim 9, Standard axis · author-conceded limit on generalizability across sample types.

> "Due to the limited availability of samples and experimental kits, each experiment was performed once and no independent replicates were generated."
> — Statistics & reproducibility · bears on: Claim 9, Standard axis · conceded reproducibility limitation (n=1 per condition, no replicates).

> "CODEX enables accurate measurement of marker protein distribution across major cell types, providing a reliable reference for tissue architecture."
> — Methods: Spatial clustering of ST and CODEX data · bears on: Claim 4, Claim 5, Claim 8 · protein (spatial) treated as a reliable orthogonal reference for tissue architecture that RNA assays are evaluated against.

> "CODEX data exhibited prominent non-specific binding signals in tumor regions and background signals across entire sections, which could bias cell annotation if based solely on the average signal intensity."
> — Methods: Annotation of ST and CODEX data · bears on: Claim 5, Standard axis · counter/nuance — the protein modality itself carries background/non-specificity artifacts requiring careful handling.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data is the bottleneck / fuel for methods | "The uniformly generated and processed multi-omics dataset could advance computational method development…" / Abstract; "…comprising 8.13 million cells, serves as a valuable resource…" / Intro | supports |
| Claim 2 — scRNA-seq loses spatial → spatial omics | "…bridging the gap in single-cell RNA sequencing (scRNA-seq) by linking molecular profiles to their spatial context." / Intro | supports |
| Claim 3 — destructive measurement, no paired time | "The tissue samples were destroyed after the analysis." / Methods; "…progress in nondestructive spatial profiling…" / Discussion | supports |
| Claim 4 — modalities orthogonal / protein as reference | "…profile proteins…using CODEX…" / Abstract; "…higher concordance with CODEX…" / Results | supports / nuances |
| Claim 5 — protein modality indispensable for function/phenotype | "CODEX enables accurate measurement of marker protein distribution…reliable reference for tissue architecture." / Methods; CODEX non-specific binding / Methods | supports / nuances |
| Claim 6 — high-throughput spatial profiling feasible | "…commercial platforms now achieving subcellular resolution and high-throughput gene detection." / Intro | supports |
| Claim 7 — spatial organization / microenvironment shapes cell state | "…tumor microenvironments and immune landscapes." / Intro; "…CD8+ T cells…infiltrating…versus…periphery…within the TME." / Results | supports |
| Claim 8 — multimodal orthogonal info needs integration | "…integration with multiomic modalities…" / Discussion; CODEX adjacent-section limitation / Discussion; multimodal segmentation / Results | supports / nuances |
| Claim 9 — data islands / non-comparable / no standard | "…datasets generated under varying experimental conditions…lack consistent ground truth data…urgent need for a systematic benchmarking study conducted under unified experimental conditions." / Intro; "…each experiment was performed once…" / Stats | supports |
| Claim 10 — resolution × throughput × destructiveness trade-offs | "…sST providing unbiased transcriptome-wide coverage and iST offering high resolution and sensitivity…" / Intro; "optical crowding…larger gene panels may reduce detection efficiency…" / Discussion; "…iST platforms are preferable…sST platforms may be more suitable…" / Discussion | supports |
| Axis C — spatial (subcellular → tissue) | segmentation, diffusion, spatial clustering, TLS / TME excerpts / Results & Discussion | supports |
| Axis B — temporal | snapshot/destructive design; nondestructive profiling as future work / Methods & Discussion | supports (by absence) |
| Standard / integration | unified processing, CODEX + scRNA-seq ground truth, registration, cross-platform concordance / throughout | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Platforms benchmarked | Stereo-seq v1.3 (BGI, sST, 0.5 μm resolution, OCT/fresh-frozen), Visium HD FFPE (10x, sST, 2 μm, ~18,085 genes), CosMx 6K (NanoString, iST, 6175 genes), Xenium 5K (10x, iST, 5001 genes) |
| Reference modalities | CODEX 16-plex protein panel (spatial proteomics, adjacent sections); matched scRNA-seq (10x Chromium 3' v3.1) on the same samples |
| Samples | 3 treatment-naïve human tumors — COAD, HCC, OV — one patient each; serial sections divided into FFPE / fresh-frozen-OCT / dissociated |
| Scale | 8.13 million cells total in the multi-omics resource; 72,405 cells manually nuclear-segmented across five 500×500 μm regions per dataset as ground truth |
| Analysis resolution | Bin-level analyses at 8 μm (≈ small-immune-cell diameter); ten ROIs of 400×400 μm for sensitivity |
| Shared gene sets | 2522 genes shared between CosMx 6K and Xenium 5K (text); Fig. 2b legend states "common genes (2552)" — see Flags |
| Negative controls (Fig 2b) | CosMx 6K: 20 NegProbes, 324 NegCodes; Xenium 5K: 40 NegProbes, 609 NegCodes; platform-specific genes 3623 (CosMx) / 2449 (Xenium) |
| Annotation tools | Five reference-based tools: SELINA, Celltypist, Spoint, Tangram, TACCO (consensus by majority vote) |
| Fig. 1 | Gene detection sensitivity across platforms; workflow; EPCAM/PanCK; gene-wise ST vs scRNA-seq correlation; per-bin counts; sequencing saturation |
| Fig. 2 | False positives / background: negative control signals, Moran's I, transcript diffusion outside tissue boundary |
| Fig. 3 | Transcript–protein correlation: ST cell-type signatures vs CODEX over spatial grids |
| Fig. 4 | Cell segmentation vs manual nuclear ground truth; transcripts/genes per cell; artificial co-expression of exclusive marker pairs (36 pairs) |
| Fig. 5 | Clustering (silhouette), annotation consistency across 5 tools, spatial alignment with adjacent CODEX |
| Fig. 6 | Spatial clustering (CellCharter) vs CODEX; tumor boundaries; spatial pathway enrichment (GO) |
| Web resource | SPATCH portal (http://spatch.pku-genomics.org/); raw data GSA HRA011129; images BioImage Archive S-BIAD1900; code github.com/zenglab-pku/SPATCH |

---

## Primary Sources Behind Key Quotes
- Prior sST benchmark comparison (Stereo-seq 0.5 μm vs Visium 55 μm; permeabilization affects diffusion) → You, Y. et al. "Systematic comparison of sequencing-based spatial transcriptomic methods." Nat. Methods 21:1743–1754 (2024), ref 30. *(in-text named "Yue et al." — see Flags)*
- Prior iST benchmarks (smaller panels / public data) → refs 31–35 (Wang bioRxiv 2023; Cervilla bioRxiv 2024; Rademacher bioRxiv 2024; Cook bioRxiv 2023; Hartman & Satija bioRxiv 2024).
- Optical crowding limits panel size → Bilous, M. et al. bioRxiv 2025.2004.2023.649965 (2025), ref 45.
- Stereo-seq platform → Chen, A. et al. Cell 185:1777–1792 (2022), ref 14.
- Visium platform → Ståhl, P. L. et al. Science 353:78–82 (2016), ref 11.
- CosMx / spatial molecular imaging → He, S. et al. Nat. Biotechnol. 40:1794–1806 (2022), ref 24.
- Xenium platform → Janesick, A. et al. Nat. Commun. 14:8353 (2023), ref 25.
- Tertiary lymphoid structures in immunotherapy → Sautés-Fridman, C. et al. Nat. Rev. Cancer 19:307–325 (2019), ref 37.

---

## Flags
- [ ] Metadata unverified: Journal inferred as **Nature Communications** from the peer-review note ("Nature Communications thanks…") and the 10.1038/s41467 DOI prefix; the **volume / article number / page** are not printed in the cleaned text. Year 2025 confirmed from publication dates and "© The Author(s) 2025".
- [ ] Source inconsistency: shared-gene count given as **2522** in Results (capture-efficiency section) but **2552** in the Fig. 2b legend.
- [ ] Source inconsistency: reference 30 is cited in-text as **"Yue et al."** but the reference list entry 30 is **"You, Y. et al."** (Nat. Methods 21:1743–1754, 2024).
- [ ] OCR normalization (NOT author wording changes): the cleaned source encodes "fi"/"fl" ligatures as `<sup>fi</sup>`/`<sup>fl</sup>` markup (e.g. "speci<sup>fi</sup>city"); excerpts above are quoted with those ligatures rendered as normal letters ("specificity", "profiling"). Superscript citation markers were dropped from quotes for readability. Some marker-gene names in the cleaned text were lost during OCR (rendered as blanks, e.g. "the epithelial marker and immune markers and"); blanks reflect the source, not omission by this note.
- [ ] Read at source: for the destructive-measurement / non-pairable-time argument (Claim 3), the primary trajectory/lineage literature is NOT in this paper — cite first-hand sources, not this benchmark.
- [ ] Scope note: detailed wet-lab protocols (per-platform reagents, incubation times, kit catalog numbers in Methods) were judged off-roadmap and not captured.
