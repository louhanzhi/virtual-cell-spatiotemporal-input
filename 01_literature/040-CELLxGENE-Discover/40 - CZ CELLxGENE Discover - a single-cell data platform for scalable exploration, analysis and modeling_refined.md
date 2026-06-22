# CZ CELLxGENE Discover: a single-cell data platform for scalable exploration, analysis and modeling of aggregated data — Source Index

**Authors:** CZI Cell Science Program; Shibla Abdulla, Brian Aevermann, Pedro Assis, Seve Badajoz, Sidney M. Bell, Emanuele Bezzi, Batuhan Cakir, Jim Chaffer, Signe Chambers, J. Michael Cherry, Tiffany Chi, Jennifer Chien, Leah Dorman, Pablo Garcia-Nieto, Nayib Gloria, Mim Hastie, Daniel Hegeman, Jason Hilton, Timmy Huang, Amanda Infeld, Ana-Maria Istrate, Ivana Jelic, Kuni Katsuya, Yang Joon Kim, Karen Liang, Mike Lin, Maximilian Lombardo, Bailey Marshall, Bruce Martin, Fran McDade, Colin Megill, Nikhil Patel, Alexander Predeus, Brian Raymor, Behnam Robatmili, Dave Rogers, Erica Rutherford, Dana Sadgat, Andrew Shin, Corinn Small, Trent Smith, Prathap Sridharan, Alexander Tarashansky, Norbert Tavares, Harley Thomas, Andrew Tolopko, Meghan Urisko, Joyce Yan, Garabet Yeretssian, Jennifer Zamanian, Arathi Mani*, Jonah Cool* and Ambrose Carr* (*corresponding)
**Journal / Venue:** Nucleic Acids Research (NAR) — inferred from "Supplementary Data are available at NAR Online"; year/volume/issue/pages not stated in text (see Flags)
**DOI:** not found in text; see Flags
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/40 - CZ CELLxGENE Discover - a single-cell data platform for scalable exploration, analysis and modeling_cleaned.md

---

## In One Sentence
The paper presents CZ CELLxGENE Discover, a free open-source platform that curates and standardizes community-contributed single-cell transcriptomic data (over 93.6 million unique cells across 449 tissues) to a minimal versioned metadata schema, and provides visual (Explorer, Gene Expression) and programmatic (Census, via TileDB-SOMA) tools for cross-corpus exploration, meta-analysis and machine-learning model training at scale.

## Orientation (non-binding)
This is a concrete, large-scale standardization-and-integration effort, so it most directly feeds the **standard / integration axis** and **Claim 9** (data silos / cross-paper incomparability / missing standards) — both as an existence proof that standardization is needed/attempted and as a source of explicit concessions. It is simultaneously a **foil**: it concedes the corpus is nearly all dissociated RNA (Claim 4 / modality axis), that Census excludes spatial data and that spatial support is still "ongoing work" (Claim 2 / spatial axis), and that batch effects distort cross-dataset comparison even after standardization (Claim 9). It also touches the data-substrate-for-foundation-models thread (Claim 1). It says essentially nothing on the temporal / destructive-measurement axis (Claim 3). The downstream agent decides whether to deploy it as a supporting example of standards-building or as a named opponent that admits the very gaps we build on.

---

## Load-Bearing Excerpts

> "Even in the presence of such portals, efforts to explore or (re)analyze many datasets face a requirement to first standardize across individual data portals and resources, with only an estimated 25% of publicly available datasets providing the cell-level metadata needed for reuse (9)."
> — Introduction · bears on: Claim 9, standard axis · quantifies how few public single-cell datasets carry reuse-ready cell-level metadata.

> "Built-for-purpose portals enable rapid publication of studies and dissemination of unique biological features in specific datasets but lack the scalability and standardization needed for efficient meta-analysis."
> — Introduction · bears on: Claim 9, standard axis · states that per-study portals lack the standardization needed for meta-analysis.

> "Data interoperability is a particularly important challenge for both individual users and the broader community to realize the promise of single-cell biology both now and in future applications that involve training models or assembling integrated references."
> — Introduction · bears on: Claim 1, Claim 9, standard axis · frames interoperability as a prerequisite for training models and building integrated references.

> "CZ CELLxGENE is differentiated from other single-cell data portals by its enforcement of a standardized schema for gene, cell, assay and donor metadata that evolves to address contributor requirements."
> — Introduction · bears on: Claim 9, standard axis · describes the platform's core mechanism as an enforced, evolving standardized metadata schema.

> "As of 1 October 2024, the platform hosts over 1550 datasets and 169.3 million cells (93.6 million unique cells)... for all major human and mouse organs."
> — Introduction · bears on: Claim 1, standard axis · gives the corpus scale (1550+ datasets, 169.3M cells, 93.6M unique).

> "To avoid deterring or inhibiting data submission and adoption, we limit the schema to 11 required fields considered most valuable for data integration and reuse."
> — Results / A minimal cell-level schema · bears on: standard axis, Claim 9 · the standardization is deliberately minimal (11 required fields).

> "The required fields represent attributes that are often variable within or across studies and are often identified as strong covariates correlated with gene expression variation within cells (20,21)."
> — Results / A minimal cell-level schema · bears on: standard axis, Claim 9 · the standardized fields are chosen because they are strong covariates of expression variation across studies.

> "To fully capture gene count information for each dataset, a layer of raw data, meaning non-normalized mapped reads, is required for submission of data from all transcriptomic assays to fulfill common computational reuse cases (25–27)."
> — Results / A minimal cell-level schema · bears on: standard axis, Claim 9 · raw counts are mandated for reuse/reproducibility.

> "The full schema specifications have been adopted by multiple consortia, including the HCA, BRAIN Initiative and Kidney Precision Medicine Project (28), and are available to the research community to support interoperability with current and future efforts."
> — Results / A minimal cell-level schema · bears on: standard axis, Claim 9 · the schema has cross-consortium adoption.

> "We designed the minimal schema to be supportive of changes and review the data corpus every 6 months for opportunities to make it increasingly comprehensive and standardized. With each schema update, previously submitted data are migrated to meet the new schema, even if that requires re-curation."
> — Results / Schema evolution · bears on: standard axis · describes versioned schema evolution with retroactive data migration so all datasets meet current standards.

> "CZ CELLxGENE hosts the largest curated collection of publicly available single-cell data, with data obtained from both single cells and single nuclei across 449 tissues and 40 unique assay types transcriptomics (Figure 2A–C)."
> — Results / Community resource · bears on: Axis A (modality), standard axis · scale and breadth, with assays characterized as transcriptomics.

> "Current data is primarily single-cell transcriptomic, although CZ CELLxGENE accepts additional modalities to support the growing number of studies that incorporate a multitude of assays and co-assays (Figure 2B)."
> — Results / Community resource · bears on: Claim 4, Axis A (modality) · concedes the corpus is primarily transcriptomic.

> "Of the 93+ million unique cells available in the data corpus, 63% of the total cells in the corpus are human, 32% are mouse and <5% are from other species (Figure 2C)."
> — Results / Community resource · bears on: standard axis · species composition of the corpus.

> "Of the human data, ∼62% is defined as coming from healthy donors, and the remaining 38% span 132 unique diseases."
> — Results / Community resource · bears on: standard axis · health/disease composition of the human corpus.

> "While CZ CELLxGENE data corpus remains the largest publicly available single-cell data resource, significant data deficiencies exist in many tissues and systems across both mouse and human (Figure 2D)."
> — Results / Community resource · bears on: standard axis, Claim 9 · concedes large gaps remain across tissues/systems even in the largest corpus.

> "diverse ethnicities and age groups are grossly underrepresented, with the majority of data coming from adults of European or Unknown ethnicity (Figure 2E–G)."
> — Results / Community resource · bears on: standard axis · concedes demographic bias / underrepresentation in the corpus.

> "Explorer, a feature of CZ CELLxGENE, is a visualization platform that allows researchers to dynamically explore, compute and query individual datasets for up to 4.3 million cells in <1 min."
> — Results / Explorer · bears on: Claim 1 · scalability figure for interactive visualization (up to 4.3M cells).

> "Single-cell transcriptomic data suffers from batch effects which distort biological signal when comparing between datasets."
> — Results / Aggregation partially mitigates batch effects · bears on: Claim 9, Claim 1 · direct statement that batch effects distort cross-dataset comparison.

> "Despite many advances in methods development for data integration, the current state-of-the-art methods produce output in a lower-dimensional space than the original count matrix, making them unsuitable for our application."
> — Results / Aggregation partially mitigates batch effects · bears on: Claim 9, Claim 8 · concedes state-of-the-art integration methods only yield low-dimensional output.

> "Thus, our simple pre-processing pipeline uses log transformed pseudocounts to normalize each cell's gene expression data, but this does not aim to eliminate batch effects between datasets."
> — Results / Aggregation partially mitigates batch effects · bears on: Claim 9 · concedes its pipeline does not remove cross-dataset batch effects.

> "This suggests that batch effects are at least partially mitigated by aggregation and log normalization compared to raw counts; however, users should be advised that the displayed values may still be affected by batch effects, especially for rare cell types."
> — Results / Aggregation partially mitigates batch effects · bears on: Claim 9 · concedes residual batch effects remain, especially for rare cell types.

> "We found an average recall of 33% (Figure 5)... the moderately low sensitivity values are likely influenced by the fact that the HuBMAP dataset we use as our 'ground truth' includes annotations from a variety of different assay types and are quite noisy."
> — Results / computationally derived marker genes · bears on: Claim 9, standard axis · concedes only 33% average marker-gene recall and attributes part of it to noisy cross-assay ground-truth annotations.

> "Many tools that are widely used for analysis, or even meta-analysis, are not designed to operate on datasets of this scale (38)."
> — Results / Census · bears on: Claim 1, Claim 10 · concedes a scalability gap in existing analysis tools.

> "While these tools are increasing the scale to which computational biologists can access and analyze data, many of these solutions are still limited to only millions of cells and more importantly, lack of interoperability between R and Python."
> — Results / Census · bears on: Claim 9, Claim 1 · concedes existing tools cap at millions of cells and lack R/Python interoperability.

> "Modeling of single-cell data at scale is an important aspect of Census, as well as the broader single-cell field, given its demonstrated uses for in silico experimentation (51,52), data integration and annotation (53,54), cell state prediction (55,56) and clinical applications (57–59)."
> — Results / Census · bears on: Claim 1 · positions large-scale single-cell data as the substrate for modeling and prediction.

> "PyTorch (60) is one of the most popular machine learning frameworks in singlecell, with notable models built using the PyTorch library including scvi-tools, Geneformer (61) and scGPT (62)."
> — Results / Census · bears on: Claim 1 · names the foundation/ML models built on single-cell data.

> "To allow existing and new machine learning models to be trained on Census-scale data, we implemented PyTorch iterable data loaders that work natively with Census via TileDB-SOMA... allowing models to be trained on Census-scale data using readily available computing resources."
> — Results / Census · bears on: Claim 1 · the platform is explicitly engineered as a data feeder for ML model training.

> "Initial datasets included in Census were generated using non-spatial RNA technologies, contain cells from human or mouse, provide raw counts and utilize only standardized cell and gene metadata as described in the CZ CELLxGENE dataset schema description above."
> — Results / Census · bears on: Claim 2, Claim 4, Axis C (spatial), Axis A (modality) · concedes Census is restricted to non-spatial RNA (human/mouse) data.

> "TileDB-SOMA was then used to build Census – a large data object hosted in the cloud with initial data covering all RNA non-spatial transcriptomic data from CZ CELLxGENE."
> — Results / Census · bears on: Claim 2, Claim 4, Axis C (spatial) · reiterates Census covers RNA non-spatial transcriptomic data only.

> "A recent demonstration of the power of CZ CELLxGENE data is on its application to train scGPT, a generative pretrained model, on 33 M cells, which the authors used for cell-type annotation, multi-batch integration, multi-omic integration, genetic perturbation prediction and gene network inference."
> — Discussion · bears on: Claim 1 · cites scGPT trained on 33M CZ CELLxGENE cells as the flagship modeling use case.

> "Importantly, the field has acknowledged the importance of spatial information in the context of single-cell biology (69,70), and ongoing work in both CZ CELLxGENE Explorer as well as Census seeks to support these efforts and technologies."
> — Discussion · bears on: Claim 2, Axis C (spatial) · concedes spatial information is important and that platform support for it is still ongoing/incomplete.

> "Finally, we recognize the ongoing importance of new modalities beyond dissociated RNA and have begun to provide support for a growing array of data modalities."
> — Discussion · bears on: Claim 4, Claim 2, Axis A (modality), Axis C (spatial) · concedes the corpus has been built on dissociated RNA and that broader modality support is only beginning.

> "Workflows, such as cell type prediction, projecting a new dataset onto the reference corpus and alignment of unanalyzed modalities, still require downloading an embedding and working outside of the platform."
> — Discussion · bears on: Claim 8, Claim 1 · concedes multimodal alignment workflows are not yet integrated into the platform.

> "Integration enables the compilation of datasets into atlases and has become a core computational task within single-cell biology (13,14). It allows for the inference of multi-modal measurements, cell type prediction and cross-species analysis that underpins insights into a wide array of biological questions as well as the ambitions of community efforts to integrate individual datasets into references (15)."
> — Results / A minimal cell-level schema · bears on: Claim 8, standard axis · frames integration as the core task enabling multi-modal inference and reference-building.

> "Importantly the flexibility of the SOMA data model allows for representations beyond the single-dataset paradigm and enables managing single-cell data from multiple modalities (e.g. RNA, spatial, epigenomics) across joint or disjoint observations."
> — Materials and methods / TileDB-SOMA · bears on: Claim 8, Axis C (spatial), Axis A (modality) · the data model is designed to hold RNA, spatial and epigenomic modalities across joint/disjoint observations.

> "It can accommodate multiple measurements from derivative views (e.g. spatial and non-spatial data) and embeddings of sparse and dense data, along with both observation (e.g. cells) and feature (e.g. genes) axis annotations."
> — Materials and methods / TileDB-SOMA · bears on: Claim 8, Axis C (spatial) · SOMA can represent both spatial and non-spatial measurements.

> "Any cell that has <500 genes expressed is excluded, which filters out about 8% of all data and does not eliminate any cell type in its entirety."
> — Materials and methods / Removal of low coverage cells · bears on: standard axis, Claim 9 · QC threshold and the fraction of data removed.

> "all of which can now be executed in a regular 8 GB memory laptop across 65 million cells and >60 000 genes."
> — Results / Census · bears on: Claim 1, Claim 10 · out-of-core access lets commodity hardware operate across 65M cells × 60,000+ genes.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 (data is bottleneck / data → foundation models) | "Modeling of single-cell data at scale…" / Census; "train scGPT… on 33 M cells" / Discussion; "PyTorch iterable data loaders…" / Census | supports |
| Claim 2 (scRNA-seq loses spatial) | "Initial datasets… non-spatial RNA technologies" / Census; "the field has acknowledged the importance of spatial information…" / Discussion | supports (concedes gap) |
| Claim 3 (destructive sequencing can't pair time) | — (paper does not address temporal/destructive measurement) | — |
| Claim 4 (modalities orthogonal / corpus too RNA-narrow) | "Current data is primarily single-cell transcriptomic…" / Community resource; "new modalities beyond dissociated RNA…" / Discussion | supports (concedes gap) |
| Claim 5 (protein/metabolome indispensable) | — (not addressed) | — |
| Claim 6 (high-throughput spatiotemporal proteomics feasible) | — (not addressed) | — |
| Claim 7 (spatial microenvironment changes cell state) | — (not addressed directly) | — |
| Claim 8 (multimodal orthogonal info; need integration) | "Integration… core computational task…" / schema; "SOMA… multiple modalities (RNA, spatial, epigenomics)…" / methods; "alignment of unanalyzed modalities still require… outside the platform" / Discussion | supports / nuances |
| Claim 9 (data silos / cross-paper incomparable / no standard) | "only an estimated 25%… cell-level metadata needed for reuse" / Introduction; "batch effects which distort biological signal when comparing between datasets" / Aggregation; "enforcement of a standardized schema…" / Introduction | supports |
| Claim 10 (resolution × throughput × destructiveness trilemma) | "many of these solutions are still limited to only millions of cells…" / Census | nuances |
| Standard axis (QC / cross-lab comparable / cross-modal pairable / unified reference) | "we limit the schema to 11 required fields…" / schema; "review the data corpus every 6 months… data migrated…" / Schema evolution; "raw data… is required for submission" / schema; "<500 genes expressed is excluded… 8%" / methods | supports |
| Axis A (modality) | "primarily single-cell transcriptomic" / Community resource; "40 unique assay types transcriptomics" / Community resource | supports (concedes RNA-dominance) |
| Axis C (spatial) | "non-spatial RNA technologies" / Census; "SOMA… spatial and non-spatial data" / methods | supports (concedes gap) / nuances |
| Axis B (temporal) | — (not addressed) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Figure 1A | Growth curve: total unique cells on CZ CELLxGENE now surpasses 93 million. |
| Figure 1B | The standard metadata schema; requires raw counts and ~10 generally available required metadata categories per sample/cell, plus the is_primary_data field (one 'primary' mark per observation corpus-wide). |
| Figure 2A–C | Corpus breakdown by suspension type, modality and organism (majority human/mouse, 10X transcriptomic assays); spatial/epigenomic/multimodal and additional species supported if they meet the minimal schema. |
| Figure 2D | Unique cells across major organ systems for mouse and human; shows tissue/system data deficiencies. |
| Figure 2E–G | Human-data summary across self-reported ethnicity, developmental stage and sex (ethnicities/ages underrepresented; majority European/Unknown). |
| Figure 3A | Explorer UMAP of all 483,152 cells in Tabula Sapiens colored by MT-RNR1 expression. |
| Figure 3B–C | Gene Expression heatmap (dot color = mean expression, dot size = % of cells expressing) and Group By stratification (e.g. by sex). |
| Figure 4 | One-way repeated-measures ANOVA on average normalized expression for marker and housekeeping genes in five cell types; for most cell types no significant difference across covariates (dataset_id, assay). |
| Figure 5 | Marker-gene recall vs HuBMAP canonical markers comparing raw counts, quantile normalization and log-transform normalization (average recall 33%). |
| Figure 6 | Census / TileDB-SOMA framework; queries across 65M+ cell measurements from 900+ datasets (human and mouse), out-of-core. |
| Table 1 | Sequencing assays included in the Gene Expression normalized data object with EFO ontology term IDs (sci-RNA-seq, 10× 3'/5' v1–v3, Seq-Well, Drop-seq, CEL-seq2, etc.). |
| Stat (Methods) | <500-genes filter removes ~8% of cells; ultra-low values (gene/cell counts ≤3) set to missing; normalization = ln(CPTT + 1), CPTT = Counts Per Ten Thousand; marker genes = Welch's t-test, top 25 by bootstrapped 10th-percentile effect size; batch-effect ANOVA used scaling factor 1,000,000. |

---

## Primary Sources Behind Key Quotes
- 25% of public datasets provide reuse-ready cell-level metadata → Puntambekar, Hesselberth, Riemondy, Fu 2021, PLoS Biol. 19:e3001077 (ref 9).
- Benchmarking atlas-level data integration / batch effects → Luecken et al. 2022, Nat. Methods 19:41–50 (ref 13); Stuart et al. 2019, Cell 177:1888–1902 (ref 14); Argelaguet, Cuomo, Stegle, Marioni 2021, Nat. Biotechnol. 39:1202–1215 (ref 15).
- scGPT generative model trained on 33M cells → Cui, Wang, Maan, Pang, Luo, Wang 2024, Nat. Methods 21:1470–1480 (ref 62).
- Geneformer (transfer learning in network biology) → Theodoris et al. 2023, Nature 618:616–624 (ref 61).
- Spatial information importance → Marx 2021, Nat. Methods 18:9–14 (ref 69); Palla, Fischer, Regev, Theis 2022, Nat. Biotechnol. 40:308–318 (ref 70).
- HuBMAP marker-gene "ground truth" → Jain et al. 2023, Nat. Cell Biol. 25:1089–1100 (ref 37).
- "Eleven grand challenges in single-cell data science" (tools not built for this scale) → Lähnemann et al. 2020, Genome Biol. 21:31 (ref 38).
- Visualization-tool comparison / sceasy 250–500k-cell tuning → Cakir, Prete, Huang, van Dongen, Pir, Kiselev 2020, NAR Genom. Bioinform. 2:lqaa052 (ref 30).

---

## Flags
- [ ] Metadata unverified: Venue is inferred as Nucleic Acids Research (NAR) from "Supplementary Data are available at NAR Online" (line 250); the article's own year, volume, issue and page numbers are not present in the cleaned text. The corpus snapshot is dated "As of 1 October 2024," suggesting a 2024/2025 publication, but this is not the article's publication date.
- [ ] Metadata unverified: No DOI for this article appears in the text (`grep` for `10.xxxx/` returned only reference-list DOIs, not the article's own). Funding listed as "No external funding"; conflict of interest "None declared."
- [ ] Reconstructed (NOT in source text): None — author names are printed in full in the source (Authors section); affiliations 1–5 listed (Wellcome Sanger Institute; Chan Zuckerberg Initiative; Stanford University; CZ Biohub SF; Clever Canary).
- [ ] Read at source: scGPT (ref 62, Cui et al. 2024) and Geneformer (ref 61, Theodoris et al. 2023) for the foundation-model-on-single-cell-data claim; Luecken et al. 2022 (ref 13) and Argelaguet et al. 2021 (ref 15) for integration/batch-effect limitations; Palla et al. 2022 (ref 70) for spatial single-cell components — all worth citing first-hand rather than via this platform paper.
- [ ] Source inconsistency: Body text states "11 required fields" (Results / A minimal cell-level schema) while Figure 1 legend states "10 generally available categories" plus the separately described is_primary_data field (i.e. 10 + 1 = 11) — consistent once is_primary_data is counted. Also note Table 1's assay names contain OCR/formatting artifacts (e.g. "$10×3' v1$") in the cleaned source; EFO IDs are intact.
- [ ] Scope note: The paper does not address the temporal axis / destructive-measurement-prevents-paired-observation argument (Claim 3), nor proteomic/metabolomic indispensability (Claims 5–6) — absences, not captured as content.
