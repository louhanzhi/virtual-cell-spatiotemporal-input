# Insights, opportunities, and challenges provided by large cell atlases — Source Index

**Authors:** Martin Hemberg, Federico Marini, Shila Ghazanfar, Ahmad Al Ajami, Najla Abassi, Benedict Anchang, Bérénice A. Benayoun, Yue Cao, Ken Chen, Yesid Cuesta-Astroz, Zachary DeBruine, Calliope A. Dendrou, Iwijn De Vlaminck, Katharina Imkeller, Ilya Korsunsky, Alex R. Lederer, Jessica Jingyi Li, Pieter Meysman, Clint L. Miller, Kerry A. Mullan, Uwe Ohler, Pratibha Panwar, Nikolaos Patikas, Jonas Schuck, Jacqueline H. Y. Siu, Timothy J. Triche Jr., Alex Tsankov, Sander W. van der Laan, Masanao Yajima, Jean Yang, Fabio Zanini, and Ivana Jelic. (Hemberg, Marini, Ghazanfar contributed equally; all authors participated in CZI Single-Cell Biology program meetings.)
**Journal / Venue:** unverified; Springer Nature / BMC open-access "REVIEW" article (sections include "Peer review information", "Authors' contributions", "Publisher's Note: Springer Nature") — see Flags
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/06 - Insights, opportunities, and challenges provided by large cell atlases_cleaned.md (raw is on disk; section names below are jump-back anchors)

---

## In One Sentence
A large multi-author review, written by contributors to the Chan Zuckerberg Initiative's Data Insights program, surveying how large single-cell "cell atlases" (e.g., CZ CELLxGENE, HuBMAP, DISCO, Single Cell Atlas) are built, ingested, accessed, integrated, benchmarked, and used — cataloguing achievements, open computational/data challenges (FAIR compliance, batch effects, metadata/ontologies, integration, benchmarking ground truth, foundation models), and the anticipated move beyond dissociated scRNA-seq toward multimodal, spatial, proteomic, and metabolomic data.

## Orientation (non-binding)
A transcriptomics-centric, infrastructure-and-methods review that sits squarely on our "data foundation" critique. It most strongly feeds Claim 9 (data silos / standards / cross-study comparability) and the Standard/integration through-line, and it supplies forward-looking concessions for Claim 1 (foundation-model generalization limits), Claim 2/Axis C (spatial), Claim 4/8 (modality narrowness & multi-omics integration), and Axis A protein/metabolite gap (proteomics/metabolomics "not yet at scale"). It can serve BOTH as support (it concedes RNA dominance, missing modalities, weak foundation-model trust, and that proteomics/metabolomics single-cell profiling is still in the future) AND as a foil (its envisioned future remains atlas/scRNA-centric; it treats the temporal axis via trajectory inference and timepoint metadata rather than confronting destructive-measurement / paired-observation limits — Claim 3 core).

---

## Load-Bearing Excerpts

> "A central goal for any scientifc resource is to make sure that it adheres to the FAIR principles [15], i.e., ensuring that data is fndable, accessible, interoperable, and reusable. By serving as central repositories, cell atlases make it easier to fnd and access data... Although straightforward in principle, the scale and complexity of a cell atlas make it difcult to achieve these goals."
> — Data ingestion, access, and representation · bears on: C9, Standard · the paper states FAIR/standardization is the goal but hard to achieve at atlas scale.

> "preprocessing is a key step that is often poorly documented and difcult to reproduce due to the use of diferent versions of software packages. Although preprocessing can improve the internal consistency, it does not prevent the emergence of discrepancies within and across atlases."
> — Data pre-processing · bears on: C9, Standard · preprocessing is poorly reproducible and does not prevent within/across-atlas discrepancies.

> "A particular concern for cell atlases is batch efects, technical artifacts that emerge due to diferences in how the data was obtained and processed. Although batch efects can be reduced, they cannot be eliminated altogether. Fortunately, it is possible to detect and correct batch efects post hoc, provided that detailed information about the processing is available."
> — Data pre-processing · bears on: C9, C8, Standard · batch effects can be reduced but not eliminated; post-hoc correction depends on detailed processing metadata.

> "However, tools for indexing, metadata standardization, and cross-cohort queries are in their infancy, and this limits the ability of users to identify suitable datasets [2, 17]... anyone interested in analyzing a large number of datasets needs to have both programming skills and sufcient computational resources. Tis creates a barrier for many users"
> — Data accessibility, interoperability, and reusability · bears on: C9, Standard · metadata standardization and cross-cohort query tools are immature, limiting dataset discovery and reuse.

> "Complete and well-curated metadata can transform a cell atlas from being a static reference to a dynamic hypothesis-generating tool, enabling a variety of stratifed analyses. For example, metadata capturing timepoints post-infection enables reconstruction of disease trajectories. On the other hand, missing or incomplete metadata could mislead data interpretation (e.g., in a human study, efects that are actually due to donor sex or age would erroneously be attributed to treatment)."
> — Metadata and ontologies · bears on: C9, C3, Axis B, Standard · metadata (incl. timepoints) is essential; missing metadata misleads interpretation; time is handled as timepoint metadata for trajectory reconstruction.

> "Although reporting and adhering to technical standards is important, it is essential to couple this to the establishment of a culture where data generators recognize their responsibility in providing complete metadata."
> — Metadata and ontologies · bears on: C9, Standard · technical standards must be paired with a data-generator culture of complete metadata.

> "No universally accepted defnition of cell types exists; however, as our knowledge of cell biology and identities is ever improving, consequently, ontologies must remain fexible... when aggregating datasets, it is often the case that they have not been annotated consistently, and assigning a consistent set of cell labels remains a major challenge."
> — Metadata and ontologies · bears on: C9, Standard · no universal cell-type definition; inconsistent annotation across aggregated datasets is a major harmonization challenge.

> "Cross-species comparisons can be particularly challenging due to diferences not only in nomenclature but also in function... when querying a “normal” atlas with disease-specifc data, researchers must account for the potential lack of representation or mismatch in cell types [26]."
> — Metadata and ontologies · bears on: C9, Standard · cross-species and normal-vs-disease querying face representation/mismatch problems.

> "Given their size, already exceeding 1 TB using standard data structures, this can require signifcant bandwidth and be prohibitive to many research labs without high-memory computing resources. For most users, working with this data requires out-of-core processing, high-performance computing, and signifcant efort in data wrangling [27]."
> — Data representation and subsampling · bears on: C9, C10, Standard · atlas datasets exceed 1 TB, prohibitive for many labs without HPC.

> "Subsampling can ease computation over diverse datasets and help reduce bias of highly represented signals, but may also compromise the unprecedented modeling power that comes with a dataset of this size. Issues include racial and gender bias in samples [28], over-representation of specifc cell types [29], opportunistic collection of rare samples [30]... Simple random subsampling does not address signal representation and can miss rare subpopulations [31, 32]"
> — Data representation and subsampling · bears on: C9, C10 · subsampling trades off computation against modeling power and risks losing rare subpopulations; samples carry racial/gender/cell-type bias.

> "A useful data integration algorithm must account for all of these sources of information and allow users to retain or remove specifc variation relevant to their analyses... data integration is not a static tool to be applied prior to further analysis, but rather needs to be adaptable to the research question at hand."
> — Data integration and meta-analysis · bears on: C8, Standard · integration must adaptively retain/remove technical vs biological variation per research question.

> "Successful data integration algorithms must address these emerging complexities, and they must (1) scale to 10,000 s of confounder levels (corresponding to the number of donors), (2) account for all sources of technical and biological variation in a way that lets users select which to account for, (3) perform consistently across a wide variety of cell atlas queries, (4) be fast and fexible enough to integrate diverse queries on the fy, (5) provide views of their impact on data distortion and signal degradation"
> — Data integration and meta-analysis · bears on: C8, Standard · five stated requirements for atlas-scale integration algorithms.

> "Numerous methods for carrying out batch integration have been proposed... However, several challenges remain, and existing methods often struggle in more complex scenarios, e.g., involving diferent species [42], imbalanced datasets [43], or very large numbers of cells. As quantitative metrics of batch integration provide an incomplete view, evaluation of the fve criteria above will also require careful considerations based on the biological interpretations."
> — Data integration and meta-analysis · bears on: C8, C9, Standard · existing integration methods struggle with cross-species/imbalanced/very-large data; quantitative batch metrics give an incomplete view.

> "even for single-cell atlases, biological replicates should consist of samples procured from independent biological sources/individuals, and not just independent cells from the same sample [50–52]... This requires sufcient numbers of true biological replicates, similar to bulk approaches [53]."
> — Building cell atlases in context · bears on: C9, C10, Standard · true biological replicates (independent individuals, not cells from one sample) are required, as in bulk.

> "One of the main challenges when comparing methods is that for most problems, we do not have an independent ground truth. Hence, evaluating the performance will involve some degree of subjectivity. One way of circumventing this challenge is to use simulations to create synthetic data. However, most synthetic datasets are unable to capture the full spectrum of complexities found in real datasets"
> — Benchmarking and development of novel methods · bears on: C1, C9, Standard · benchmarking lacks independent ground truth, making evaluation subjective; synthetic data cannot capture real-data complexity.

> "As such, there is tremendous value in datasets that can be considered as a “gold standard” by virtue of orthogonal means. Carefully curated cell atlases can serve an important role here by being commonly used for benchmarking specifc analytical tasks."
> — Benchmarking and development of novel methods · bears on: C9, C4, Standard · gold-standard datasets validated by orthogonal means are highly valuable for benchmarking.

> "Many methods that are commonly used may not scale well to tens of millions of cells and thousands of conditions, and consequently, there is a need to increase computational and algorithmic efciency. Tis is likely to involve various types of approximations and lossy compression"
> — Benchmarking and development of novel methods · bears on: C1, C9 · common methods do not scale to tens of millions of cells / thousands of conditions.

> "Several groups have developed foundation models leveraging the large-scale data collected via cell atlas eforts, e.g., Geneformer [60], scGPT [61], scFoundation [62], scBERT [63], CellFM [64], UCE [65]... Foundation models learn generalizable representations of cell type and state from gene expression profles, and they can be used to annotate new datasets, project them into shared latent spaces, infer missing modalities, and simulate responses to genetic or pharmacological perturbations."
> — Benchmarking and development of novel methods · bears on: C1, C4, Axis A · single-cell foundation models are trained on gene-expression profiles (RNA) and can infer missing modalities / simulate perturbation responses.

> "Despite these advances, widespread practical use remains limited. Current challenges include technical barriers to applying these models in user-friendly interfaces, dealing with memory and computational infrastructure requirements, limited interpretability and explainability of model predictions and representations, and the lack of widespread stress-testing of models on noisy, rare and disease-specifc single cell datasets to improve trust."
> — Benchmarking and development of novel methods · bears on: C1 · authors concede single-cell foundation models have limited practical use, limited interpretability, and lack stress-testing on noisy/rare/disease data.

> "An example of an established method that requires novel frameworks to be applicable to new types of data is RNA velocity. A manifold-constrained and biologically tailored velocity, as opposed to general-purpose tools, could be designed to statistically compare estimates in the case–control setting [58, 59]."
> — Benchmarking and development of novel methods · bears on: C3, Axis B · temporal dynamics treated via RNA-velocity inference, proposed for case–control comparison.

> "Single-cell RNA-seq was the frst high-throughput method that allows for a high-plex characterization of individual cells, and thus it has been the most widely used approach [1, 88]. However, there are numerous other single-cell technologies under active development, and we foresee that over the coming years cell atlases will see an infux of other modalities [89]. Tese include TCR and BCR sequencing, ATAC-seq, and long-read sequencing."
> — Beyond atlases of dissociated single-cell transcriptomes · bears on: C4, Axis A · scRNA-seq is the dominant/most-used modality; other modalities are still "under active development" and only anticipated to flow into atlases.

> "Ensuring that diferent modalities can be combined for joint analyses is key, but it will present some major challenges, e.g., developing pre-processing pipelines, ontologies, and determining what metadata to include."
> — Beyond atlases of dissociated single-cell transcriptomes · bears on: C8, Standard · combining modalities for joint analysis faces pipeline/ontology/metadata challenges.

> "by combining ATAC-seq and RNA-seq data, we are likely to improve our ability to infer gene regulatory networks [91]. However, integrating such data across tissues, donors, and platforms at the cell atlas scale presents substantial challenges. As multi-omics datasets become more complex and heterogeneous, future integration frameworks will need to account for missing modalities, difering noise characteristics, and scale."
> — Beyond atlases of dissociated single-cell transcriptomes · bears on: C4, C8, Standard · multimodal combinations add information (e.g., GRN inference) but raise missing-modality, noise, and scale integration problems.

> "Perhaps the most important direction of new technologies is toward spatial methods, primarily for transcriptomics and proteomics, but other modalities are likely to follow. Spatial data brings numerous challenges along with great potential for additional insights [94]."
> — Beyond atlases of dissociated single-cell transcriptomes · bears on: C2, C7, Axis C · spatial methods (transcriptomics and proteomics) framed as the most important new direction.

> "For multiple samples, it may be more useful to map cells/spots to a common coordinate system, either informed by relative landmarks [95] or by merging across multiple samples [96]. Tere is also a need for further algorithmic development of methods, tools, and community standards for mining spatial data."
> — Beyond atlases of dissociated single-cell transcriptomes · bears on: C2, C7, Standard, Axis C · multi-sample spatial data needs a common coordinate system and lacks mature standards/methods.

> "Mining spatial data typically involves fnding subcellular patterns in cells associated with disease, type, and outcomes [97]... As technologies evolve and are able to profle larger tissue sections at subcellular resolution, a particular challenge will be to develop methods that can bridge molecular, cellular, and tissue-level patterns."
> — Beyond atlases of dissociated single-cell transcriptomes · bears on: C7, Axis C · spatial analysis spans subcellular → cellular → tissue patterns linked to disease/outcome.

> "Most likely, within the next few years, advancements in the felds of proteomics and metabolomics will enable the profling of large numbers of single cells via these modalities, unlocking more accurate modeling of metabolism, signaling, and cell–cell communication."
> — Conclusions and outlook · bears on: C4, C5, C6, Axis A · authors concede single-cell proteomics/metabolomics is not yet at scale and is needed for accurate modeling of metabolism, signaling, and cell–cell communication (RNA alone insufficient for these).

> "To realize the potential not just for biomedical research, but for other aspects of biology, we need better coverage of human populations across the age spectra and for multiple disease states. Moreover, additional species are needed."
> — Conclusions and outlook · bears on: C9, Axis B · current atlas coverage is incomplete across age, disease states, and species.

> "Developmental atlases, such as those of the human fetus [101], human brain [102], zebrafsh [103], fruit fy [104], and mouse [105], provide rich datasets for understanding cell fate decisions and lineage specifcation"
> — Conclusions and outlook · bears on: C3, Axis B · developmental atlases supply trajectory/lineage data (cross-sectional developmental stages).

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| C1 data is bottleneck / foundation-model generalization | "Despite these advances, widespread practical use remains limited…" / Benchmarking | supports |
| C1 (no ground truth / scale) | "we do not have an independent ground truth…" ; "may not scale well to tens of millions…" / Benchmarking | supports |
| C2 scRNA-seq loses spatial | "the most important direction… is toward spatial methods" / Beyond dissociated | supports |
| C3 destructive seq → no paired time | "metadata capturing timepoints post-infection enables reconstruction of disease trajectories" ; RNA velocity / Metadata, Benchmarking | nuances |
| C4 modalities orthogonal / irreplaceable | "the most widely used approach… infux of other modalities" ; "proteomics and metabolomics… modeling of metabolism, signaling" / Beyond, Conclusions | supports |
| C5 protein/metabolism indispensable for function | "unlocking more accurate modeling of metabolism, signaling, and cell–cell communication" / Conclusions | supports |
| C6 high-throughput spatiotemporal proteomics feasible | "within the next few years, advancements in… proteomics and metabolomics will enable… profling of large numbers of single cells" / Conclusions | nuances (frames as future, not yet achieved) |
| C7 spatial microenvironment shapes cell state | "fnding subcellular patterns in cells associated with disease… bridge molecular, cellular, and tissue-level patterns" / Beyond | supports |
| C8 multimodal orthogonal info → integrate | "combining ATAC-seq and RNA-seq… infer gene regulatory networks" ; five integration criteria / Beyond, Integration | supports |
| C9 data silos / no standard / not comparable | FAIR "difcult to achieve" ; "batch efects… cannot be eliminated" ; "metadata standardization… in their infancy" ; "no independent ground truth" / multiple §§ | supports |
| C10 resolution × throughput × destructiveness trilemma | "exceeding 1 TB… prohibitive" ; subsampling "compromise the unprecedented modeling power" / Data representation | nuances (compute/scale trade-off, not measurement trilemma) |
| Standard / integration (through-line) | "discrepancies within and across atlases" ; "common coordinate system… community standards" ; "true biological replicates" / multiple §§ | supports |
| Axis A modality | foundation models "from gene expression profles" ; proteomics/metabolomics future / Benchmarking, Conclusions | supports |
| Axis B temporal | "timepoints post-infection" ; RNA velocity ; developmental atlases / Metadata, Benchmarking, Conclusions | nuances |
| Axis C spatial | "toggle between gene expression space (UMAP) and physical space" ; "common coordinate system" / Beyond | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 (atlas inventory) | Lists major cell atlases with cell counts: CZ CELLxGENE Discover 112.8 M cells / 5 k donors / 7 species (CZI, 2022); Single Cell Portal 57.6 M / 18 species (Broad, 2020); Single Cell Expression Atlas 13.5 M / 21 species (EMBL-EBI, 2018); HuBMAP (NIH, 1 species, 2018); Human Cell Atlas (HCA) 65.4 M / 9.6 k donors (2016); Allen Brain Cell (ABC) Atlas 4.0 M / 1 species; TISCH2 6.3 M / 2 species; DISCO 125.6 M (Singapore Immunology Network, 2022); Single Cell Atlas 200 M / 125 donors / 1 species (2024); AIDA 1.3 M / 625 donors (HCA-Asia, 2023); 3CA Curated Cancer Cell Atlas (Weizmann, 2025); **scMMO-atlas (single-cell multimodal omics) only 3.2 M / 2 species (CAS, 2025)**; PlaqView 1.7 M (2022). Quantitatively shows transcriptomics-scale atlases (≥100 M cells) dwarf the lone multimodal atlas (3.2 M). |
| Fig. 1 | Schematic: atlases ingest data from many labs by criteria (species, disease, tissue), process coherently, and serve queries via a portal for download/interrogation, yielding new findings. |
| Fig. 2 | Summary schematic of key challenges, opportunities, and issues regarding cell atlases today. |

---

## Primary Sources Behind Key Quotes
- Single-cell foundation models (RNA-trained) → Geneformer: Theodoris CV et al., Nature 2023;618(7965):616–24, ref #60 · scGPT: Cui H et al., Nat Methods 2024, ref #61 · scFoundation: Hao M et al., Nat Methods 2024;21(8):1481–91, ref #62 · scBERT: Yang F et al., Nat Mach Intell 2022;4(10):852–66, ref #63 · CellFM: Zeng Y et al., Nat Commun 2025;16(1), ref #64 · UCE: Rosen Y et al., bioRxiv 2023, ref #65
- Atlas-level batch integration benchmark → Luecken MD et al., Nat Methods 2022;19(1):41–50, ref #37
- Considerations for building/using integrated atlases → Hrovatin K et al., Nat Methods 2025;22(1):41–57, ref #87
- Multi-omics methods/applications review → Vandereyken K et al., Nat Rev Genet 2023;24(8):494–515, ref #92
- Best practices for single-cell analysis across modalities → Heumos L et al., Nat Rev Genet 2023;24(8):550–72, ref #90
- Dissociation protocols bias transcriptome → Truong DD et al., BMC Cancer 2023;23(1):488, ref #29
- Identifying disease-altered cell states vs healthy reference → Dann E et al., Nat Genet 2023;55(11):1998–2008, ref #26
- Spatial transcriptomics introduction → Williams CG et al., Genome Med 2022;14(1), ref #94
- Manifold-constrained RNA velocity → Lederer AR et al., Nat Methods 2024;21:2271–86, ref #59 (and Cell2fate: Aivazidis A et al., Nat Methods 2025;22(4):698–707, ref #58)
- FAIR principles → Wilkinson MD et al., Sci Data 2016, ref #15

---

## Flags
- [ ] Metadata unverified: Journal/venue not stated anywhere in the cleaned text. Formatting (REVIEW header, "Peer review information", "Authors' contributions", "Publisher's Note: Springer Nature remains neutral…", Open Access) indicates a Springer Nature / BMC-family journal, but the specific title is not confirmable from the source. Do not assert venue without external check.
- [ ] Metadata unverified: No DOI for THIS article appears in the body. All `10.xxxx/…` strings found by grep belong to references / Table 1 atlas entries, not the paper itself.
- [ ] Dates confirmed from text: "Received: 14 June 2024  Accepted: 3 September 2025  Published online: 20 October 2025" (end of body, before Figure Descriptions).
- [ ] Source inconsistency (OCR / cleaning artifacts): Table 1 cells are garbled in places — e.g., HuBMAP "# donors" shows "Not reported 214" / 214 appears misplaced; HCA "# species" blank; AIDA/SCA "# species" misaligned; TISCH2 "Year started"/organization fields merged ("03 (publicationShanghai…"); 3CA "# cells" blank. Treat Table 1 numeric cells as approximate; verify against the published table before citing exact donor/species counts.
- [ ] Source inconsistency: pervasive dropped-ligature OCR errors throughout (e.g., "efects", "fndable", "diferent", "Te"/"Tis"/"Tese" for "The"/"This"/"These", "infux", "profle"). Quotes above are reproduced verbatim from the cleaned file including these artifacts.
- [ ] Read at source (primary papers worth first-hand reading for our thesis): foundation-model generalization limits — the model papers themselves (Geneformer #60, scGPT #61, scFoundation #62, UCE #65) and the integrated-atlas best-practices review (Hrovatin #87); multi-omics integration (Vandereyken #92); spatial transcriptomics (Williams #94); RNA-velocity case–control (Lederer #59).
- [ ] Scope note: This paper's drug-discovery / GWAS-molQTL applications (Using cell atlases for biomedical research) and the Cell-atlas-outreach section are off-roadmap and were not captured, except where they touch standards/multimodal integration. Subsampling content (Claim 10) is a compute/scale trade-off, not the measurement-side resolution×throughput×destructiveness trilemma — routed as "nuances," not direct support.
