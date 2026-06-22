# Nicheformer: a foundation model for single-cell and spatial omics — Source Index

**Authors:** Alejandro Tejada-Lapuerta, Anna C. Schaar, Robert Gutgesell, Giovanni Palla, Lennard Halle, Mariia Minaeva, Larsen Vornholz, Leander Dony, Francesca Drummer, Till Richter, Mojtaba Bahrami & Fabian J. Theis
**Journal / Venue:** Nature Methods, 2025 (volume/issue/pages not printed in source; see Flags). Received 24 Oct 2024; Accepted 11 Aug 2025; Published online 30 Oct 2025.
**DOI:** doi:10.1038/s41592-025-02814-z
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/07 - Nicheformer - a foundation model for single-cell and spatial omics_cleaned.md

---

## In One Sentence
Nicheformer is a transformer-based foundation model pretrained on SpatialCorpus-110M — a curated corpus of >110 million dissociated single-cell and image-based spatial transcriptomics cells from human and mouse across 73 tissues — that learns spatially aware cell representations, outperforms dissociated-only foundation models on a newly designed set of spatial downstream tasks (niche/region label prediction, neighborhood composition and density prediction), and shows that models trained only on dissociated data fail to recover the complexity of spatial microenvironments.

## Orientation (non-binding)
Sits squarely on our spatial axis (Axis C). Likely strong support for Claim 2 (dissociated scRNA-seq loses spatial information) and Claim 7 (microenvironment/neighborhood shapes cell state and is prognostic), and a useful concession source for Claim 1 (foundation-model benchmark fragility; data diversity > data quantity), Claim 9 (no standardized benchmarks; cross-technology batch effects), and Claims 4/8 (the authors explicitly concede that protein abundance and epigenetic modalities, plus paired multimodal data, are needed for a "true representation of the cellular state"). It can EQUALLY serve as a foil: its central pitch is that spatial context can be computationally *inferred* from transcriptome alone and transferred onto dissociated data — an argument that one can partly recover what dissociation discards without measuring it, which a writer may deploy against our "space must be measured explicitly" line. Silent on the temporal axis (Axis B / Claim 3).

---

## Load-Bearing Excerpts

> "Tissue makeup depends on the local cellular microenvironment."
> — Abstract / p.1 · bears on: Claim 7, Axis C · opening premise that tissue composition is governed by local spatial context.

> "single-cell RNA sequencing (scRNA-seq) requires cell dissociation, losing information about the cellular microenvironment and hindering a complete understanding of molecular variation"
> — Introduction / p.1 · bears on: Claim 2, Axis C · states dissociation discards microenvironment information.

> "Critically, we show that models trained only on dissociated data fail to recover the complexity of spatial microenvironments, underscoring the need for multiscale integration."
> — Abstract / p.1 · bears on: Claim 1, Claim 2, Claim 8, Axis C · dissociated-only data cannot recover spatial microenvironment complexity.

> "In situ spatial omics has revealed spatial components of cellular variations such as cell–cell communication and spatial gradients as well as emergent properties of tissue niches"
> — Introduction / p.1 · bears on: Claim 7, Axis C · spatial measurement reveals communication, gradients and niche-level emergent properties.

> "Current results are promising but not entirely replicated in independent benchmarks."
> — Introduction / p.2 · bears on: Claim 1, Claim 9 · concedes single-cell foundation-model results are not reproduced by independent benchmarks.

> "Notably, these models do not account for spatial relationships of cells during training, with the exception of CellPLM, which, however, is trained on a limited dataset of 9 million dissociated and 2 million spatial transcriptomics cells and not fine-tuned on spatial tasks beyond gene imputation."
> — Introduction / p.2 · bears on: Claim 2, Axis C · existing single-cell foundation models ignore spatial relationships during training.

> "A limiting factor for image-based spatial transcriptomics data is the targeted feature space, measuring only hundreds to a few thousands of genes, depending on technology and panel"
> — Results, transformer-based model overview / p.2 · bears on: Claim 10, Axis A · spatial gain comes at the cost of a narrow targeted gene panel (resolution vs breadth trade-off).

> "Only expression data were used during pretraining to train the model to integrate data from dissociated and targeted spatial technologies, both of which show substantial batch effects"
> — Results, model overview / p.2 · bears on: Claim 9, Standard · dissociated and spatial assays both carry substantial batch effects.

> "Previous works have demonstrably shown technology-dependent biases between spatial and dissociated transcriptomics data, with spatial data often yielding higher gene counts due to preprocessing steps."
> — Results, cell representation / p.3 · bears on: Claim 9, Claim 10, Standard · documented technology-dependent biases between spatial and dissociated data.

> "training on dissociated data alone (even three times the amount of spatial data) resulted in lower performance across downstream tasks … indicating that dissociated data alone cannot capture spatial variation."
> — Results, model design and training / p.3 · bears on: Claim 1, Claim 2, Axis C · 3× more dissociated data still cannot compensate for spatial information.

> "Importantly, this result is not influenced by the sheer number of cells since all models are trained with the same number of cells; the only difference is the diversity of the data. These findings are statistically significant … and highlight the importance of data diversity in model training for optimal performance across context"
> — Results, model design and training / p.3 · bears on: Claim 1 · data diversity, not raw cell count, drives model performance.

> "It includes 57.06 million dissociated cells and 53.8 million spatial cells across human and mouse tissues."
> — Results, SpatialCorpus-110M / p.3 · bears on: Claim 2, Axis C · scale of the assembled dissociated vs spatial corpus.

> "Most cells originated from the brain (60.46%, n = 32,146,779 cells) and the lung (9.95%, n = 3,199,548 cells). A large proportion of the publicly available spatial omics datasets we collected are not annotated (55.23%). We included both healthy samples (64.07%) and cancer samples (31.98%)"
> — Results, SpatialCorpus-110M / p.4 · bears on: Claim 1, Claim 9 · public spatial data are brain-dominated and majority-unannotated (heterogeneous, imbalanced supply).

> "Importantly, we did not integrate datasets into a unified latent space. Our goal was to preserve biological and technical variability while offering a large-scale resource for model training. Like CellXGene, SpatialCorpus-110M provides curated raw inputs, allowing researchers to choose their own normalization and integration strategies."
> — Results, SpatialCorpus-110M / p.4 · bears on: Claim 9, Standard · deliberate non-integration; curated raw inputs with harmonized metadata as a shared resource.

> "However, cell types are defined ignoring the spatial context, which provides additional value for understanding cellular microenvironments"
> — Results, label transfer / p.5 · bears on: Claim 2, Claim 7, Axis C · standard cell-type definitions omit spatial context.

> "Transferring labels between dissociated and spatial data is challenging due to limited gene overlap, and modality-specific methods are not designed to learn from reference atlases at the scale of hundreds of million of cells."
> — Results, label transfer / p.5 · bears on: Claim 8, Claim 9, Standard · cross-modality integration is hard due to limited gene overlap and scale.

> "Differences in neighborhood composition have been shown to have an important effect on gene expression and can be associated with cell–cell communication events."
> — Results, neighborhood compositions / p.6 · bears on: Claim 7, Axis C · neighborhood composition causally shapes a cell's gene expression.

> "Furthermore, the cellular composition of neighborhoods in the tumor microenvironment may hold prognostic value, because immune cell infiltration in the spatial context is a predictor for cancer survival."
> — Results, neighborhood compositions / p.6 · bears on: Claim 7, Axis C · spatial neighborhood composition has clinical/prognostic value.

> "It is long known that cell density can strongly affect growth behavior in vivo and in culture; also, increased cell density is a key feature of the formation of the tumor microenvironment, which leads to the creation of a hypoxic environment and depletion of infiltrating immune cell populations."
> — Results, niche density / p.7 · bears on: Claim 7, Axis C · local cell density alters cell behavior and tumor microenvironment.

> "Consistent with literature observations, we observed a higher average cellular density in the cancer sections (colon, 12.3 cells; lung, 12.1 cells) compared to healthy tissue (colon, 10.7 cells; lung, 10.7 cells) when extracting cellular neighborhoods at the same radius"
> — Results, niche density / p.7 · bears on: Claim 7 · quantitative density difference between cancer and healthy tissue.

> "The linear-probing models trained on the scVI and PCA embeddings failed to correctly predict the mean density and performed worse than random prediction, resulting in negative R2 values for both tissues."
> — Results, niche density / p.7 · bears on: Claim 1 · standard embedding baselines fail (worse than random) at recovering spatial density.

> "These results strongly suggest that spatial context can be effectively inferred from transcriptomics data using Nicheformer."
> — Discussion / p.8 · bears on: Claim 2, Axis C · COUNTER/nuance — claims spatial context is computationally inferable from transcriptome alone.

> "Notably, Nicheformer enables the direct transfer of spatially aware annotations from spatial to dissociated single-cell data by using a simple linear layer."
> — Results, label transfer / p.5 · bears on: Claim 2, Claim 8, Axis C · COUNTER/nuance — spatial annotations transferred onto dissociated data computationally.

> "More generally, it will be necessary to operate on multimodal data to generate a true representation of the cellular state. While spatial transcriptomics captures the cellular microenvironment in tissues well, integrating additional data modalities, such as protein abundance or epigenetic modifications, will provide a more complete picture of the cellular state."
> — Discussion / p.8 · bears on: Claim 4, Claim 5, Claim 8, Axis A · concedes transcriptomics is insufficient and that protein/epigenetic modalities are needed for a true cell-state representation.

> "One key hurdle is the lack of sufficient paired data measured across multiple or even all cellular modalities."
> — Discussion / p.8 · bears on: Claim 4, Claim 8, Standard · concedes scarcity of paired multimodal data.

> "Incorporating additional modalities will remain a challenge in the future as, for example, epigenetic modifications, protein abundance and gene expression all have unique characteristics, and effectively combining them in a way that leverages their strengths remains an ongoing research area."
> — Discussion / p.8 · bears on: Claim 4, Claim 8, Axis A · concedes each modality has unique, non-interchangeable characteristics.

> "A long-term vision in systems biology has been to create multi-scale models, from molecules and cells up to tissue, organs and eventually the whole organism."
> — Discussion / p.8 · bears on: Claim 7, Claim 8 · frames the multiscale (molecule→tissue→organism) modeling vision.

> "Firstly, Nicheformer performance depends on the data abundance and transcriptional diversity of the cells under study."
> — Discussion (limitations) / p.8 · bears on: Claim 1 · conceded limitation — performance bounded by data abundance/diversity.

> "Secondly, Nicheformer does not explicitly incorporate the physical location of a cell during pretraining, limiting its capability to fully leverage the available information on spatial context. We deliberately chose not to include spatial coordinates during pretraining"
> — Discussion (limitations) / p.8 · bears on: Claim 2, Axis C · conceded limitation — even this spatial model does not encode physical coordinates.

> "However, unlike more established AI domains, there's a crucial gap in the form of standardized benchmarks for evaluating these models. Establishing robust benchmarks is a critical next step to compare and improve performance, rigorously assess methodological progress and guide future model development"
> — Discussion (limitations) / p.8 · bears on: Claim 9, Standard · concedes the field lacks standardized benchmarks.

> "While we observed no difference between using them and not using them in the downstream tasks focused on one modality … we observed that transferring labels between spatial and dissociated datasets did not work at all when using the contextual tokens in the aggregation. Further investigation revealed that the output norm of the contextual token of modality was always the highest one, independently of the tissue … hence playing a big role in the cell representation and biasing it toward the respective modality."
> — Methods, evaluation/linear probing / p.13 · bears on: Claim 9, Claim 8, Standard · modality batch signal so dominant it had to be excluded for cross-modality transfer to work at all.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data is bottleneck; data-driven models generalize poorly | "Current results are promising but not entirely replicated…" / Intro; "training on dissociated data alone (even three times…" / Results; "the only difference is the diversity of the data" / Results | supports |
| Claim 2 — scRNA-seq loses spatial information | "scRNA-seq requires cell dissociation, losing information about the cellular microenvironment" / Intro; "models trained only on dissociated data fail to recover…" / Abstract | supports |
| Claim 2 — (counterpoint) | "spatial context can be effectively inferred from transcriptomics data" / Discussion; "direct transfer of spatially aware annotations… by using a simple linear layer" / Results | challenges |
| Claim 3 — destructive sequencing cannot observe time pairwise | (paper is cross-sectional; does not address temporal axis) | — |
| Claim 4 — modalities orthogonal / mutually irreplaceable | "protein abundance and gene expression all have unique characteristics" / Discussion; "integrating additional data modalities, such as protein abundance or epigenetic modifications" / Discussion | supports |
| Claim 5 — protein/metabolite indispensable to function/phenotype | "integrating additional data modalities… will provide a more complete picture of the cellular state" / Discussion | supports (indirect) |
| Claim 6 — high-throughput spatiotemporal proteomics feasible | (transcriptomics-only; spatial protein imaging only cited via ref 38) | — |
| Claim 7 — microenvironment changes cell state & response | "Tissue makeup depends on the local cellular microenvironment" / Abstract; "Differences in neighborhood composition have… an important effect on gene expression" / Results; "immune cell infiltration… is a predictor for cancer survival" / Results | supports |
| Claim 8 — multimodal orthogonal info, needs integration | "it will be necessary to operate on multimodal data to generate a true representation" / Discussion; "lack of sufficient paired data measured across… all cellular modalities" / Discussion | supports |
| Claim 9 — data islands / incomparable / no standard | "crucial gap in the form of standardized benchmarks" / Discussion; "technology-dependent biases between spatial and dissociated" / Results; "not entirely replicated in independent benchmarks" / Intro | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "targeted feature space, measuring only hundreds to a few thousands of genes" / Results | supports (spatial-vs-breadth facet) |
| Axis C — spatial | nearly all excerpts above | supports |
| Standard — QC / comparability / integration | "we did not integrate datasets into a unified latent space… curated raw inputs" / Results; contextual-token norm bias / Methods | supports/nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Overview: Nicheformer pretrained on SpatialCorpus-110M; gene-rank tokenizer with species/modality/assay context tokens; new downstream tasks (cell-type/niche/region label, neighborhood density, neighborhood composition) on brain (MERFISH), liver/lung (CosMx), lung/colon (Xenium). |
| Fig. 2 | SpatialCorpus-110M composition: 57.06M dissociated cells (17 organs, 18 cell lines) + 53.83M spatial cells (4 technologies, 15 solid organs); harmonized metadata schema. |
| Extended Data Fig. 2 | A model trained on 1% spatial data outperforms models on equal or 3× dissociated data on spatial tasks; mouse-only / human-only models underperform on the missing organism; results FDR-significant — evidence that dissociated data cannot substitute for spatial, and that diversity matters. |
| Fig. 6 | Neighborhood density prediction: Nicheformer linear probe beats scVI and PCA (which give negative R²) on Xenium lung and colon; cancer sections denser than healthy. |
| Supplementary Table 2 | Catalog of new spatially aware downstream tasks vs prior dissociated-only foundation-model tasks. |
| Architecture numbers | 1,500-token context; 12 transformer layers; 16 heads; FFN size 1,024; 512-dim embedding; 49.3M parameters; 20,310 gene tokens (16,981 orthologous, 3,178 human-specific, 151 mouse-specific); >350 datasets, 8 sequencing technologies, 2 species; pretrained ~10 days on 12 × A100 40GB GPUs; masked-language-modeling (15% masking, BERT schema). |

---

## Primary Sources Behind Key Quotes
- scRNA-seq dissociation loses microenvironment (Intro, ref 4) → Du, J. et al. Advances in spatial transcriptomics and related data analysis strategies. J. Transl. Med. 21, 330 (2023).
- Single-cell foundation models not replicated in independent benchmarks (Intro, refs 26–28) → esp. Kedzierska, K. Z. et al. Zero-shot evaluation reveals limitations of single-cell foundation models. Genome Biol. 26, 101 (2025) (ref 27); also Boiarsky et al. bioRxiv 2023 (ref 26); Alsabbagh et al. bioRxiv 2023 (ref 28).
- Cell types defined ignoring spatial context (Results, ref 53) → Palla, G., Fischer, D. S., Regev, A. & Theis, F. J. Spatial components of molecular tissue biology. Nat. Biotechnol. 40, 308–318 (2022).
- Neighborhood composition affects expression / cell–cell communication (Results, ref 6) → Fischer, D. S., Schaar, A. C. & Theis, F. J. Modeling intercellular communication in tissues using spatial graphs of cells. Nat. Biotechnol. 41, 332–336 (2023).
- Immune infiltration predicts cancer survival (Results, ref 55) → Fridman, W. H., Pagès, F., Sautès-Fridman, C. & Galon, J. The immune contexture in human tumours: impact on clinical outcome. Nat. Rev. Cancer 12, 298–306 (2012).
- Immune cell density and colorectal-tumor outcome (Results, ref 63) → Galon, J. et al. Type, density, and location of immune cells within human colorectal tumors predict clinical outcome. Science 313, 1960–1964 (2006).
- Cell density / tumor microenvironment / immune depletion (Results, ref 62) → Parra, E. R. et al. Immune cellular patterns of distribution affect outcomes of patients with non-small cell lung cancer. Nat. Commun. 14, 2364 (2023).
- Only prior spatial-trained foundation model (Intro, ref 29) → Wen, H. et al. CellPLM: Pre-training of cell language model beyond single cells. ICLR (2024).

---

## Flags
- [ ] Metadata unverified: Journal is Nature Methods (DOI prefix s41592 and the in-text "Peer review information Nature Methods thanks…" line confirm the venue), but the printed volume/issue/page numbers are not present in the cleaned source — only Received/Accepted/Published-online dates appear.
- [ ] Reconstructed (NOT in source text): none — full author names are printed verbatim in the "Authors" block of the source.
- [ ] Read at source: Kedzierska et al. 2025 (Genome Biol. 26:101, ref 27) for the independent-benchmark critique of single-cell foundation models; Palla et al. 2022 (Nat. Biotechnol. 40:308, ref 53) for "cell types are defined ignoring spatial context"; Du et al. 2023 (ref 4) for the dissociation-loses-microenvironment claim — all are first-hand for our Claims 1/2/7.
- [ ] Source inconsistency / OCR artifacts: the cleaned MD contains OCR glitches in non-quoted regions (e.g., "Spatia single-cell," "fne-tuning," "eforts," "afiliations") and the equations are partly garbled; quotes above were selected from clean passages. Ref 6 appears twice with differing pagination (line 127 as a 2022 advance-online without page numbers; line 227/ref 56 as Nat. Biotechnol. 41:332–336, 2023) — the same Fischer et al. paper is cited as both ref 6 and ref 56.
- [ ] Scope note: paper is purely transcriptomic and cross-sectional — it provides no direct evidence for the temporal axis (Claim 3) or for proteomic/metabolomic feasibility (Claim 6); its relevance to Claims 4/5/8 is via authors' Discussion-level concessions, not via experiments.
