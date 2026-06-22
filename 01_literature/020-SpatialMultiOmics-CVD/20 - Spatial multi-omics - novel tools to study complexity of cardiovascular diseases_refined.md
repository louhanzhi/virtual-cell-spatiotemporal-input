# Spatial multi-omics: novel tools to study the complexity of cardiovascular diseases — Source Index

**Authors:** Paul Kiessling¹ and Christoph Kuppe¹ * (both authors contributed equally)
**Journal / Venue:** unverified — journal name not printed in source text; Open Access Review, Springer Nature (per Publisher's Note); see Flags
**DOI:** not found in text (no article DOI in body or header; only DOIs of cited references appear); see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/20 - Spatial multi-omics - novel tools to study complexity of cardiovascular diseases_cleaned.md
**Dates (from end of body):** Received 15 August 2023 · Accepted 2 January 2024 · Published online 18 January 2024

---

## In One Sentence
A review surveying spatial multi-omics technologies (NGS-array, imaging/FISH/ISS, and MS-based at cellular-to-subcellular resolution), their computational pipelines (segmentation, multi-omic data integration, cell-cell interaction, subcellular pattern analysis), and the experimental/computational challenges, framed around applications to cardiovascular (heart and kidney) disease.

## Orientation (non-binding)
Directly load-bearing for the spatial axis (Axis C) and the modality axis (Axis A): the paper repeatedly states that dissociated single-cell/single-nucleus data lose spatial context, that the transcriptome alone is an incomplete proxy for protein/metabolite state, and that "true" same-cell multi-omic measurement is currently very limited so researchers fall back on diagonal integration / imputation. It also supplies quantitative ammunition for Claim 4 (mRNA–protein correlation ~40%; 30,000× more protein than mRNA) and Claim 9/standard (no integration tool exceeds Pearson 0.5 vs ground truth; standardization and independent benchmarks "urgently needed"). It can serve BOTH as support (spatial/multimodal gaps are real and consequential) AND as a foil/nuance (it is optimistic about foundation models and frames many gaps as soon-to-be-solved). The downstream agent decides deployment.

---

## Load-Bearing Excerpts

> "While single-cell and single-nuclei studies of the human heart in health [11, 12] and disease [4, 13–15] have led to valuable insights, spatial information was lacking."
> — Background (and repeated in §NGS-sequencing-based spatial multi-omics) · bears on: Claim 2, Axis C (spatial) · states that dissociated single-cell heart studies omitted spatial information.

> "Spatial biology enables researchers to observe and decode these complex patterns and communications of cells within their native tissue environments."
> — Background · bears on: Claim 2, Claim 7, Axis C · positions spatial measurement as recovering native-tissue context lost by dissociation.

> "However, it has become clear that for a comprehensive understanding of intrinsic and extrinsic factors which control cell fate decisions in tissues, it is crucial to consider and include spatial molecular information."
> — Background · bears on: Claim 2, Claim 7, Axis C · claims spatial molecular information is necessary for understanding cell fate.

> "Tese technologies aim to close the gaps inherent to dissociated single-cell data providing information on the colocalization of cell types and cell states, spatial covariance of gene expression changes, and defning cellular tissue niches and how they change in disease (Fig. 1)."
> — §NGS-sequencing-based spatial multi-omics · bears on: Claim 2, Claim 7, Axis C · names the specific information classes that dissociated single-cell data lack.

> "Spatial resolution was crucial for these fndings, as myocarditis shows distinct zonation and border zones with unique infammatory signatures that could potentially be missed in single-cell RNA sequencing studies of dissociated tissue."
> — §NGS-sequencing-based spatial multi-omics (viral myocarditis example) · bears on: Claim 2, Claim 7, Axis C · concrete case where dissociated scRNA-seq would miss spatially zonated signatures.

> "Organ function is dependent on tight control of intrinsic and extrinsic stimuli within the tissue microenvironment to control cell fate decisions in development, health, and disease."
> — Background · bears on: Claim 7, Axis C · asserts microenvironment governs cell fate.

> "In heart disease, infammatory and fbrotic responses are not randomly located in the tissue but possess specifc motifs or principles. In MI, ANKRD1 and NPPB show a gradient across the border zone of the infarct [4], and the epicardium has been shown to contain distinct niches of plasma B cells [22]."
> — §Integration of multi-omic datasets · bears on: Claim 7, Axis C · quantal example of spatially organized (gradient/niche) disease responses.

> "Tis is however problematic, as most forms of cell-cell communication are short ranged and very much dependent on the spatial tissue organization."
> — §Cell-cell interaction in space · bears on: Claim 7, Axis C · argues cell-cell communication analysis requires spatial position, not dissociated data.

> "Until recently, programs had to rely on dissociated single-cell data for this task. Tis is however problematic, as most forms of cell-cell communication are short ranged and very much dependent on the spatial tissue organization."
> — §Cell-cell interaction in space · bears on: Claim 2, Claim 7, Axis C · states the prior reliance on dissociated data was a limitation for CCC.

> "While transcriptome information is widely used to model protein expression dynamics, the genome-wide correlation between mRNA and protein is estimated to be only around 40% [60, 61]."
> — §Non-NGS-based spatial multi-omics · bears on: Claim 4, Claim 5, Axis A · quantitative statement that mRNA is a weak proxy for protein. (citation [60,61] appears mismatched — see Flags.)

> "Furthermore, the transcriptome alone cannot provide information about processes induced by posttranslational protein modifcations, which can have important efects on cell biology."
> — §Non-NGS-based spatial multi-omics · bears on: Claim 4, Axis A · states PTM information is not recoverable from transcriptome.

> "Compared to the transcripts, resolving the proteome at single-cell resolution or in tissues is much more challenging. Cells typically contain 30,000× more protein molecules than mRNA molecules [67], and proteins are very heterogeneous in size and structure and, unlike nucleic acids, cannot be amplifed. Tis has limited the multiplexing and throughput of spatial proteome measurements."
> — §Non-NGS-based spatial multi-omics · bears on: Claim 4, Claim 6, Claim 10, Axis A · concedes why spatial proteomics lags transcriptomics (no amplification, abundance/heterogeneity); quantitative 30,000× figure.

> "Nevertheless, enormous progress has been made in generating multiplex proteomics datasets from tissues."
> — §Non-NGS-based spatial multi-omics · bears on: Claim 6, Axis A · asserts feasibility/progress of tissue multiplex proteomics.

> "Another approach to enable unbiased single-cell or spatial proteomics is based on highly sensitive LC-MS-based proteomics (reviewed here [67, 74–76]), which has been adapted to spatial proteomics as deep visual proteomics (DVP) [77, 78]. DVP combines laser-capture microdissection of distinct cell types from tissue and performs MS proteomics of the collected tissues extending bulk proteomics of the human heart [79] with cell type and spatially resolved information in the near future."
> — §Non-NGS-based spatial multi-omics · bears on: Claim 6, Axis A, Axis C · describes an unbiased, spatially-resolved MS proteomics route (DVP) extending bulk human-heart proteomics.

> "Based on transcriptomic data alone, the diferentiation of naïve or mature immune cells is generally challenging, but additional protein markers such as CD45RO/CD45RA commonly used in FACS can signifcantly aid the identifcation of the correct immune cell state."
> — §NGS-sequencing-based spatial multi-omics · bears on: Claim 4, Claim 5, Axis A · protein markers carry cell-state information transcriptome cannot resolve.

> "Cell typing is much improved when information about both transcriptome and proteome is available, as cells like NK-cells, which play a major role in infammatory heart disease [142, 143], are notoriously hard to classify based solely on their low transcript counts."
> — §Integration of multi-omic datasets · bears on: Claim 4, Claim 5, Claim 8, Axis A · concrete case (NK cells) where protein modality is needed beyond transcript counts.

> "Spatial metabolomics has reached 5–10 μm resolution and has been recently applied to study cell-type-specifc dynamics of metabolism in kidney repair [82]. … MALDI-MSI-based metabolomics combined with 13C-labeled nutrients allowed the authors to study the dynamics of metabolic changes at subcellular resolution. Tey subsequently used multiplexed immunofuorescence microscopy to identify cell types which seemed unnecessary, as cell types could be diferentiated just based on the lipid profles."
> — §Non-NGS-based spatial multi-omics · bears on: Claim 4, Claim 5, Axis A, Axis B, Axis C · metabolite/lipid profiles carry orthogonal cell-type-distinguishing information; 13C labeling adds metabolic time dynamics at subcellular resolution.

> "Cell morphology is another resource that remains underutilized in the analysis of spatial datasets. Cardiomyocytes and fibroblasts are known to change their cellular phenotype and morphology in response to stress, such as hypertrophy, elongation, or thickening [117]. These features offer valuable insight into cell state that could be integrated with existing omics measurements."
> — §Integration of multi-omic datasets · bears on: Claim 4, Claim 5, Axis A · morphology/imaging is an additional, under-used modality reflecting cell state.

> "Te cellular location of proteins is often disturbed in disease like in familial atrial fbrillation, for example, which is caused by a mutation that impedes HSP70 import [153]. Te role of RNA localization remains poorly understood but has been implicated in developmental processes [154] and diseases like Huntington's disease [155]."
> — §Integration of multi-omic datasets · bears on: Claim 4, Claim 7, Axis C · subcellular localization of proteins/RNA is itself disease-relevant information.

> "To unlock the synergy of multi-omic measurements, integrating the datasets with each other is necessary. Tis is a nontrivial task as the data generated by diferent modalities exist in entirely diferent feature spaces."
> — §Integration of multi-omic datasets · bears on: Claim 8, standard · states integration is necessary but hard because modalities live in different feature spaces.

> "Argelaguet et al. [125] proposed three categories of integration tasks: Horizontal integration is used when the same modality is measured across diferent samples. … Vertical integration describes the integration of measurements in the same cells … Te most challenging case is diagonal integration. Here, neither the cells nor features are shared across datasets, and integration instead relies on a strong biological signal that can be captured with diferent modalities independently from each other."
> — §Integration of multi-omic datasets · bears on: Claim 8, standard · defines horizontal/vertical/diagonal integration; diagonal (no shared cells or features) is hardest.

> "At the moment, the parallel measurement of multiple modalities of the same cells in a "true" multi-omic experiment is very limited, and researchers instead rely on algorithms that diagonally integrate separate measurements or impute missing data. Tis emphasizes the importance of reliable integration."
> — §Computational challenges · bears on: Claim 3, Claim 4, Claim 8, standard · concedes same-cell multi-omic measurement is rarely possible; modalities are typically measured separately and reconciled computationally.

> "It is necessary to scrutinize integrated datasets for biological plausibility, especially as a recent review of transcriptomics integration methods found that no tool reached a Pearson correlation coefcient of more than 0.5 compared to ground truth [177]. Multi-omic integration is likely even more challenging as the link between datasets is weaker."
> — §Computational challenges · bears on: Claim 1, Claim 8, standard · quantitative ceiling: no integration tool exceeded Pearson 0.5 vs ground truth; cross-modal integration is harder still.

> "One possible way forward might be the creation of foundation models for spatial multi-omics, analogues to eforts in natural language processing [178], and single-cell transcriptomics [179–181]. Tese models, trained on a large corpus of spatial and single-cell multiomic datasets, might be able to deconvolute underlying patterns necessary for successful integrations."
> — §Computational challenges · bears on: Claim 1, Claim 8 · proposes foundation models trained on large corpora as a path to integration (optimistic framing — potential foil).

> "For data analysis, we envision that large-scale foundation models, which have been recently employed for the analysis of single-cell RNA sequencing data, will spur advancements in spatial multi-omics data analysis in a diverse range of downstream tasks, including data integration, cell-type annotation spatial gene expression analysis, and perturbation prediction, e.g., from drug and genetic perturbations and gene network inference."
> — §Future perspectives · bears on: Claim 1, Claim 7 (perturbation), Claim 8 · forecasts foundation models extending to spatial integration and perturbation prediction.

> "An independent benchmark of spatial-omics integration algorithms is urgently needed and would help scientists in their choice of integration strategy and inform their experimental designs."
> — §Integration of multi-omic datasets · bears on: Claim 9, standard · explicit admission that benchmarking/comparability for integration tools is missing.

> "While these tools show promise, it is important to note that as of the time of this article's publication, several tools have not undergone peer review."
> — §Integration of multi-omic datasets · bears on: Claim 9, standard · concedes immaturity / lack of validation of integration tooling.

> "However, an independent benchmark that compares sensitivity, specifcity, and other performance metrics has not been carried out."
> — §Spatial multi-omics technologies at single-molecular resolution (re CosMx, Molecular Cartography) · bears on: Claim 9, Claim 10, standard · no head-to-head performance benchmark across competing platforms.

> "It remains to be seen which approach yields the most biologically relevant information, as no comparative benchmarking has been published so far."
> — §Cell-cell interaction in space · bears on: Claim 9, standard · no comparative benchmark for spatial CCC algorithms.

> "Despite nontrivial challenges, such as the need for standardization of experimental setups, data analysis, and improved computational tools, the application of spatial multi-omics holds tremendous potential…"
> — Abstract · bears on: Claim 9, standard · names standardization of setups and analysis as an outstanding need.

> "As with single-cell RNA sequencing, standardized sample preparation is key for successful experiments and high data quality. … standardized protocols need to be followed for tissue sampling, fxation, freezing, and tissue sectioning."
> — §Experimental challenges · bears on: Claim 9, standard · standardized preparation framed as prerequisite for data quality.

> "A guide on how diferent tissues should be handled for each spatial multi-omics technology is currently lacking but would greatly increase reproducibility in the feld."
> — §Experimental challenges · bears on: Claim 9, standard · concedes absence of standardized tissue-handling guidance harms reproducibility.

> "Ecosystems that process spatial multi-omics data in a standardized way are just beginning to emerge. … Tis infrastructure is critical to unify the heterogeneous data from diferent technology-specifc vendor formats and the various images, tables, and polygons that a single experiment can generate…"
> — §Cell segmentation · bears on: Claim 9, standard · standardized data containers/formats are nascent; data are heterogeneous and vendor-specific.

> "Multiple platforms have been established to facilitate the sharing of data and easy inbrowser viewing of datasets [182–187]. However, these repositories remain underused, with every website only containing a small subset of published data. … Ideally, scientifc journals would require sharing of data in a digestible and convenient fashion as ofered by these data stores."
> — §Computational challenges · bears on: Claim 9, standard · data sharing repositories exist but are underused; data remain fragmented across stores.

> "It is often unclear which algorithm produces the best result, as the generation of ground truth for performance evaluation relies on tedious manual annotation of the target tissue. Furthermore, the performance of segmentation algorithms is highly tissue and disease-state dependent."
> — §Computational challenges · bears on: Claim 9, standard · concedes lack of ground truth and tissue-dependence of segmentation performance.

> "Spatial multi-omics experiments are costly and complex to establish and should only be employed in settings where a clear zonation of the tissue is expected."
> — §Design considerations for spatial multi-omic experiments · bears on: Claim 10, standard · cost/complexity constrain deployment of spatial multi-omics.

> "As an example, rare cells, like neuronal cells or pericytes, would best be studied with a high-resolution technique, as detection might not be possible in lower resolution measurements which confate multiple cells into spots. Te analysis of lowly expressed genes like transcription factors is best served by approaches with maximal sensitivity, such as ISS or ISH."
> — §Design considerations · bears on: Claim 10, Axis C · resolution vs sensitivity trade-off; low-resolution spots conflate cells.

> "Generally speaking, methods with a larger feature scale such as NGS-based multi-omics and microdissection MS lend themselves well to an exploratory setting, while more targeted approaches like imaging-based multi-omics and ion-label MS shine in confrming well-defned research questions."
> — §Design considerations · bears on: Claim 10, Axis A · feature-scale (breadth) vs targeted (depth/specificity) trade-off across platforms.

> "An imaging-based spatial transcriptomics measurement can generate around 5 TB of raw data (e.g., MERFISH, own experience), necessitating a robust data storage strategy to which many academic laboratories might not have access."
> — §Computational challenges · bears on: Claim 10, standard · quantitative data-volume burden (~5 TB per MERFISH run).

> "In our spatial multi-omic study of human myocardial infarction [4], we utilized multi-omic techniques such as single-cell gene expression sequencing, chromatin accessibility sequencing (scATAC-seq), and ST to build a molecular map of cardiac remodeling, including multiple clinical time points."
> — §NGS-sequencing-based spatial multi-omics · bears on: Claim 3, Claim 8, Axis B, Axis C · multimodal spatial map across multiple post-MI time points (time captured via separate samples, not paired single-cell tracking).

> "While several barcoding technologies exist to uncover the hierarchical structure or lineage tree of cellular differentiation on single-cell level, we expect that these technologies will be more employed in tissues like in intMEMOIR [190] to uncover hierarchical tissue maps. Tese might also be applied to human tissue based on somatic mutations or mutational signatures from mitochondria [191] or leveraging clonotype information from, e.g., the TCR of T cells. Furthermore, they may be combined with other digital recording systems for biological events [192, 193], further refning insights for biological time traveling in tissues."
> — §Future perspectives · bears on: Claim 3, Axis B · lineage-tracing / recording approaches proposed to recover temporal/lineage history in tissue ("biological time traveling").

> "Additionally, one can predict a rise in the combination of geneediting experiments and spatial multi-omics. Similar to single-cell-based CRISPR screenings, these assays can be implemented in vivo or in vitro in organoids or bioprinted constructs and spatial gene or drug perturbations consequences analyzed, thus extending the functional analysis toolbox (Fig. 3)."
> — §Future perspectives · bears on: Claim 7 (perturbation response), Axis A (phenotype/perturbation) · forecasts spatial perturbation (CRISPR/drug) readouts.

> "Recent developments of transgenic mice have enabled metabolic labeling of proteins using Cre-recombinase-induced expression of a mutant methionyl-tRNA synthetase [80, 81] from a given cell population. Combined with unbiased MS-proteomic approaches, this might be well suited to resolve the cell secretome or for the discovery of novel biomarkers…"
> — §Non-NGS-based spatial multi-omics · bears on: Claim 5, Claim 6, Axis A, Axis B · cell-type-specific metabolic protein labeling adds a temporal (nascent-proteome) dimension to proteomics.

> "Similarly to the speed of development of single-cell assays (from 1 cell [27] to 100,000 s with ultrahigh throughput [28, 29] within 10 years), the development of spatial technologies has recently gained pace…"
> — Background · bears on: Claim 6, Claim 10 · quantitative throughput trajectory of single-cell assays as a pacing analogy for spatial methods.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 (data bottleneck / foundation-model generalization) | "no tool reached a Pearson correlation coefcient of more than 0.5…" / §Computational challenges | supports |
| Claim 1 (foundation models) | "creation of foundation models for spatial multi-omics…" / §Computational challenges & §Future | nuances |
| Claim 2 (scRNA-seq loses spatial information) | "spatial information was lacking" / Background & §NGS | supports |
| Claim 2 | "could potentially be missed in single-cell RNA sequencing studies of dissociated tissue" / §NGS (myocarditis) | supports |
| Claim 3 (destructive seq → no paired temporal observation) | "parallel measurement … of the same cells … is very limited" / §Computational challenges | supports |
| Claim 3 (temporal / trajectory) | "multiple clinical time points" / §NGS; "biological time traveling" / §Future | nuances |
| Claim 4 (modalities orthogonal / non-substitutable) | "mRNA and protein … only around 40%" / §Non-NGS | supports |
| Claim 4 | "transcriptome alone cannot provide information about … posttranslational protein modifcations" / §Non-NGS | supports |
| Claim 4 | "30,000× more protein molecules than mRNA" / §Non-NGS | supports |
| Claim 5 (protein/metabolite indispensable for function/phenotype) | "NK-cells … notoriously hard to classify based solely on their low transcript counts" / §Integration | supports |
| Claim 5 | "cell types could be diferentiated just based on the lipid profles" / §Non-NGS | supports |
| Claim 6 (high-throughput spatial(temporal) proteomics feasible) | "enormous progress … multiplex proteomics datasets from tissues"; "DVP" / §Non-NGS | supports |
| Claim 6 (proteomics still harder than RNA) | "resolving the proteome … is much more challenging … cannot be amplifed" / §Non-NGS | challenges |
| Claim 7 (spatial organization/microenvironment shapes cell state) | "responses are not randomly located … ANKRD1 and NPPB show a gradient" / §Integration | supports |
| Claim 7 | "cell-cell communication … dependent on the spatial tissue organization" / §Cell-cell interaction | supports |
| Claim 8 (multi-modal orthogonal info, needs integration) | "three categories of integration tasks … diagonal integration" / §Integration | supports |
| Claim 8 | "To unlock the synergy … integrating the datasets … is necessary" / §Integration | supports |
| Claim 9 (data islands / incomparable / no standards) | "independent benchmark … is urgently needed" / §Integration | supports |
| Claim 9 | "need for standardization of experimental setups, data analysis" / Abstract; "guide … is currently lacking" / §Experimental challenges | supports |
| Claim 9 | "repositories remain underused … small subset of published data" / §Computational challenges | supports |
| Claim 10 (resolution × throughput × destructiveness trilemma) | "larger feature scale … exploratory … targeted … confrming" / §Design considerations | supports |
| Claim 10 | "rare cells … high-resolution … lower resolution … confate multiple cells into spots" / §Design considerations | supports |
| Claim 10 | "~5 TB of raw data (e.g., MERFISH)" / §Computational challenges | nuances |
| Axis A (modality) | mRNA–protein 40%; 30,000× protein; PTM; lipid profiles; morphology underutilized | supports |
| Axis B (temporal) | clinical time points; 13C metabolic dynamics; metabolic protein labeling; lineage tracing / "time traveling" | nuances |
| Axis C (spatial) | "native tissue environments"; subcellular localization; zonation/niches/border zone | supports |
| Standard / integration | benchmarks lacking; standardized prep/handling lacking; data sharing fragmented; standardized ecosystems "just beginning to emerge" | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 | Overview of spatial multi-omics methods grouped as NGS-based, imaging-based, and MS-based. Columns include method, instrument, analyte principle, modalities, feature scale, resolution, cost. Reports e.g. Visium 1–55 μm / Stereo-seq 200 nm; DBiT-Seq 10 μm; multiplex-ISH beyond diffraction limit sub-5 nm; ion-labelled antibodies (IMC/MIBI) 100 nm–1 μm; DVP (microdissection) 5–10 μm (cellular). Feature scale ranges from ~1–50 (ion-labelled) to "10.000s" (NGS RNA) to "unlimited" (microdissection MS). Cost coded "+" to "++++". |
| mRNA–protein correlation | Genome-wide mRNA–protein correlation "estimated to be only around 40%" (§Non-NGS). |
| Protein vs mRNA abundance | Cells contain "30,000× more protein molecules than mRNA molecules" (§Non-NGS, ref [67]). |
| Integration accuracy ceiling | No transcriptomics-integration tool reached Pearson correlation > 0.5 vs ground truth (§Computational challenges, ref [177]). |
| Visium resolution | 55-μm diameter spots in a hexagonal array, 100-μm center-to-center spacing (§NGS). |
| Subcellular ST resolution | Stereo-Seq ~220-nm diameter / 200 nm (Table 1 & §single-molecular). |
| Spatial metabolomics resolution | 5–10 μm (§Non-NGS, ref [82]). |
| Raw data volume | Imaging-based ST (e.g., MERFISH) can generate ~5 TB raw data per measurement (§Computational challenges, "own experience"). |
| Single-cell throughput trajectory | From 1 cell (2009) to >100,000 s with ultrahigh throughput within ~10 years (Background, refs [27–29]). |
| Figs 1–3 | Fig 1: NGS-based spatial multi-omics (non-deterministic vs deterministic barcoding). Fig 2: computational analysis areas (spatial patterns, cell-cell interaction, morphology/subcellular, data integration). Fig 3: future perspectives (gene-editing/perturbation, lineage barcoding, high-res receptor-ligand, pathomics, foundation models, 3D). |

---

## Primary Sources Behind Key Quotes
- Human MI spatial multi-omic map (border-zone gradients; scATAC + ST + multiple time points) → Kuppe C, Ramirez Flores RO, Li Z, et al. "Spatial multi-omic map of human myocardial infarction." Nature. 2022;608:766–77 (ref #4).
- Spatially resolved multiomics of human cardiac niches (drug2cell; plasma B-cell niches) → Kanemaru K, Cranley J, Muraro D, et al. Nature. 2023, doi:10.1038/s41586-023-06311-1 (ref #22).
- 30,000× more protein than mRNA; proteome sampling limits → MacCoss MJ, Alfaro JA, Faivre DA, et al. "Sampling the proteome by emerging single-molecule and mass spectrometry methods." Nat Methods. 2023;20:339–46 (ref #67).
- Three integration categories (horizontal/vertical/diagonal) → Argelaguet R, Cuomo ASE, Stegle O, Marioni JC. "Computational principles and challenges in single-cell data integration." Nat Biotechnol. 2021;39:1202–15 (ref #125).
- Integration benchmark Pearson < 0.5 vs ground truth → Li B, Zhang W, Guo C, et al. "Benchmarking spatial and single-cell transcriptomics integration methods…" Nat Methods. 2022;19:662–70 (ref #177).
- Deep Visual Proteomics (DVP) → Mund A, Coscia F, Kriston A, et al. "Deep visual proteomics defines single-cell identity and heterogeneity." Nat Biotechnol. 2022;40:1231–40 (ref #77).
- Bulk proteomic map of the human heart (extended by DVP) → Doll S, Dreßen M, Geyer PE, et al. "Region and cell-type resolved quantitative proteomic map of the human heart." Nat Commun. 2017;8:1469 (ref #79).
- Original high-throughput spatial transcriptomics (Visium basis) → Ståhl PL, Salmén F, Vickovic S, et al. "Visualization and analysis of gene expression in tissue sections by spatial transcriptomics." Science. 2016;353:78–82 (ref #35).
- Spatial metabolomics of cell-type-specific metabolism in kidney repair (13C + MALDI-MSI) → Wang G, Heijs B, Kostidis S, et al. "Analyzing cell-type-specific dynamics of metabolism in kidney repair." Nat Metab. 2022;4:1109–18 (ref #82).
- NK cells in inflammatory heart disease → Ong S, Rose NR, Cihakova D. Clin Immunol. 2017;175:26 (ref #142); Sun K, Li Y-Y, Jin J. Signal Transduct Target Ther. 2021;6:1–16 (ref #143).

---

## Flags
- [ ] Metadata unverified — journal/venue: The source text does NOT print the journal name. The article is an Open Access Review under Springer Nature (per "Publisher's Note"). Venue therefore left unverified in the header; do not assert a journal name without checking the DOI/landing page.
- [ ] Metadata unverified — article DOI: No DOI for THIS article appears in the body or header of the cleaned file (only DOIs of cited references are present). Recorded as "not found in text."
- [ ] Source inconsistency — citation mismatch: The "~40% mRNA–protein correlation" sentence cites "[60, 61]," but in this paper's reference list ref #60 = Wirth et al. (spatial transcriptomics via multiplexed deterministic barcoding, Nat Commun 2023) and ref #61 = Kishi et al. (Light-Seq, Nat Methods 2022) — neither is an obvious primary source for the 40% figure. Treat the 40% number as quoted-but-unsourced here; verify the original mRNA–protein correlation source before citing first-hand.
- [ ] Read at source (worth first-hand reading for our thesis): ref #4 (Kuppe 2022, Nature — spatial MI map, co-authored by this paper's senior author; directly on spatial + temporal + multimodal heart data); ref #22 (Kanemaru 2023, Nature — human cardiac niches); ref #67 (MacCoss 2023, Nat Methods — proteome sampling limits / 30,000× figure); ref #125 (Argelaguet 2021 — integration taxonomy); ref #177 (Li 2022, Nat Methods — integration benchmark / Pearson < 0.5); ref #77 (Mund 2022 — DVP); ref #82 (Wang 2022, Nat Metab — spatial metabolomics dynamics).
- [ ] OCR artifacts in source: The cleaned MD drops several "fi/fl" ligatures (e.g., "fbroblasts," "infammation," "specifc," "Tey/Te" for "They/The"). Quotes above reproduce the source text verbatim, including these artifacts; the raw file on disk is the system of record.
- [ ] Scope note: The paper contains extensive catalogs of computational tools (segmentation: Cellpose/Baysor/Mesmer…; integration: Moscot/MaxFuse/SpatialGlue…; spatial-pattern: SPARK/SpaGCN/STAGATE…). These are modeling-method details and are out of our perspective's scope (we argue "what data," not "how to model"); they were intentionally NOT captured as excerpts except where a tool's existence demonstrates an integration/standard gap (Claims 8/9).
