# Modeling intercellular communication in tissues using spatial graphs of cells — Source Index

**Authors:** David S. Fischer, Anna C. Schaar, Fabian J. Theis
**Journal / Venue:** Nature Biotechnology, 2022 (published online 27 October 2022); volume/pages not given in text — see Flags
**DOI:** doi:10.1038/s41587-022-01467-z
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/38 - Modeling intercellular communication in tissues using spatial graphs of cells_cleaned.md

---

## In One Sentence
The authors introduce node-centric expression models (NCEMs) — linear/nonlinear graph neural networks and CVAEs — that predict a cell's gene expression from its spatial niche composition in image-based spatial molecular profiling (RNA or protein) data, and use them across six spatial datasets plus deconvoluted Visium spots to recover statistically significant cell–cell dependencies at physiologically relevant length scales.

## Orientation (non-binding)
This paper opens by indicting the standard cell-communication paradigm for relying on **dissociated** molecular profiles that **ignore spatial proximity in situ** — directly on-thesis for the "dissociation loses space" argument (Claim 2) and for the spatial axis (Axis C). Its core demonstration — that **niche/microenvironment composition explains within-cell-type expression variation** — feeds Claim 7 (microenvironment changes cell state). It also touches multimodal integration (spatial + scRNA-seq imputation; Claim 8) and the limited-panel trade-off of targeted spatial assays (Claim 10). It is **single-snapshot spatial only** — it offers no temporal/time-course or lineage evidence, so it does not feed Claim 3. Note it can serve as BOTH support (spatial data recovers niche signal lost by dissociation) and a tempering counter-line (the added spatial signal ΔR² is small versus cell-type identity variance). Detailed model architecture (loss functions, CVAE math, design matrices) is out of scope per the context file's "no modeling methods" boundary and is not captured.

---

## Load-Bearing Excerpts

> "Models of intercellular communication in tissues are based on molecular profiles of dissociated cells, are limited to receptor–ligand signaling and ignore spatial proximity in situ."
> — Abstract · bears on: Claim 2, Axis C · states that the prevailing cell-communication models use dissociated data and discard in-situ spatial position.

> "We present node-centric expression modeling, a method based on graph neural networks that estimates the effects of niche composition on gene expression in an unbiased manner from spatial molecular profiling data."
> — Abstract · bears on: Claim 7, Axis C · the method quantifies how niche composition shapes a cell's gene expression.

> "Usually, these communication events cannot be directly observed but are critical to understand emergent phenomena in tissue niches."
> — Introduction · bears on: Claim 7 · cell–cell communication events are largely unobservable yet drive tissue-niche-level phenomena.

> "Molecular signatures of sender and receiver cell types are used to infer latent cell communication events in a tissue through co-occurrence of ligand and receptor expression across putatively communicating cell types and through gene expression signatures in the receiving cell."
> — Introduction · bears on: Claim 2 · describes the existing (non-spatial) ligand–receptor co-occurrence inference the paper aims to improve.

> "We infer cell communication from image-structured molecular profiling assays of RNA or proteins with subcellular resolution (Fig. 1a)."
> — Introduction · bears on: Axis A, Axis C · the input is spatial imaging of RNA **or proteins** at subcellular resolution.

> "We defined an NCEM as a graph neural network that predicts a cell's observed gene expression vector from its cell type label and its niche."
> — Introduction · bears on: Claim 7 · a cell's expression is modeled as a function of its cell type plus its spatial niche.

> "Cell–cell dependencies may be caused by diverse molecular mechanisms not limited to ligand–receptor-based communication. Therefore, we consider the effects of niche composition on all genes in an unbiased manner."
> — Introduction · bears on: Claim 7, Claim 4 · cell–cell dependencies arise from many molecular mechanisms beyond ligand–receptor signaling, so all genes are modeled.

> "they … did not work on targeted protocols with limited ligand and receptor gene capture … or relied on leave-one-gene hold-outs, which can result in false discoveries of dependencies"
> — Introduction (critique of prior methods, Supplementary Table 1) · bears on: Claim 10 · targeted spatial protocols have limited ligand/receptor gene capture, a known coverage constraint.

> "We demonstrate cell communication inference with NCEMs on six datasets measured with MERFISH, CODEX, MIBI-TOF, MELC and chip cytometry."
> — Results · bears on: Axis A, Axis C · spans RNA imaging (MERFISH) and protein imaging (CODEX, MIBI-TOF, MELC, chip cytometry).

> "On average, intracell-type variance accounted for 40.6% of the total variance (Supplementary Fig. 1 and Methods)."
> — Results · bears on: Claim 7 · a large fraction of total expression variance lies *within* cell types, leaving room for niche to explain it. (quantitative)

> "Linear NCEMs were most predictive on an intermediate length scale of 69 µm across the six datasets (Fig. 1c), showing that cell–cell dependencies appear on length scales characteristic of molecular mechanisms of cell communication."
> — Results · bears on: Claim 7, Axis C · spatial dependencies peak at a characteristic ~69 µm length scale. (quantitative)

> "NCEMs outperformed nonspatial baseline models consistently by an average ΔR2 (Online Methods) of 0.016 (Fig. 1c)."
> — Results · bears on: Claim 2, Claim 7 · adding spatial niche information improves expression prediction over a nonspatial baseline. (quantitative)

> "As expected, the ΔR2 is small compared to the baseline model R2 that characterizes between-cell-type variance (0.39–0.79) because cell type identity accounts for a large fraction of variance in single-cell gene expression assays."
> — Results · bears on: Claim 7 (nuance) · the spatial/niche contribution is real but small relative to the variance explained by cell-type identity. (quantitative; tempering counter-line)

> "The spatial effect on model performance varies between target cell types, suggesting that cell-type-specific molecular mediators of cell–cell dependency are captured (Supplementary Fig. 3)."
> — Results · bears on: Claim 7 · the strength of niche effects is cell-type specific.

> "We found putatively interacting ligand–receptor pairs for almost all type couplings in CellPhoneDB and NicheNet analyses of matched single-cell RNA sequencing (scRNA-seq) data, thus demonstrating the need for a quantitative description of statistical couplings in niches (Extended Data Fig. 4e–g)."
> — Results · bears on: Claim 2, Claim 7, Claim 8 · scRNA-seq-based tools flag candidate ligand–receptor pairs for nearly all couplings, motivating spatial, quantitative coupling estimates.

> "We identified a bidirectional dependency of B cells and follicular dendritic cells (FDCs) that is indicative of positive feedback between both cell types in germinal center organization (Fig. 2a,b and Extended Data Fig. 4c)."
> — Results · bears on: Claim 7 · a recovered spatial dependency maps to a known microenvironmental biology (germinal-center positive feedback).

> "The interpretation of spatial dependencies inferred on targeted spatial molecular profiling assays is constrained by the limited capture of ligand–receptor pairs. We imputed the cell-wise gene expression in the MERFISH fetal liver data using corresponding scRNA-seq data (Extended Data Fig. 10)."
> — Results · bears on: Claim 10, Claim 8 · targeted spatial assays capture too few ligand–receptor genes, addressed here by imputing the full transcriptome from matched scRNA-seq.

> "The peak predictive performance of the ligand–receptor nonlinear NCEM was much higher compared to the nonlinear NCEM (R2 of 0.799 and 0.947), demonstrating the increased complexity of the input compared to categorical cell type labels."
> — Results · bears on: Claim 8, Axis A · imputed continuous receptor/ligand expression carries far more predictive information than categorical cell-type labels. (quantitative)

> "The statistical identifiability of cell type couplings may improve with increased capture of niche heterogeneity, through the inclusion of three-dimensional data, by increasing the number of cells measured and by increasing the variation in the training data through perturbations of niche structure."
> — Discussion · bears on: Claim 7, Claim 10, Axis C · authors concede that better inference needs more cells, 3D spatial data, and **perturbations of niche structure**. (author-conceded directions)

> "Uncertainty in segmentation of cells or nuclei can be improved on the level of the spatial measurement or may be addressed in model extensions."
> — Discussion · bears on: Claim 10, Standard · cell/nucleus segmentation uncertainty is a measurement-level (QC) limitation of spatial assays.

> "We integrated scRNA-seq with MERFISH data to impute the full gene expression in the spatial graph of cells measured in MERFISH. … We used 131 out of 132 genes from the MERFISH fetal liver (WT) data, which were both present in the MERFISH and the scRNA-seq dataset, to perform the mapping."
> — Methods (MERFISH-scRNA-seq integration) · bears on: Claim 8, Axis A, Claim 10 · the targeted MERFISH panel is only 132 genes, motivating integration with scRNA-seq to recover transcriptome-wide signal. (quantitative)

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq / dissociation loses spatial info | "Models … are based on molecular profiles of dissociated cells … ignore spatial proximity in situ" / Abstract | supports |
| Claim 2 — scRNA-seq loses spatial info | "Molecular signatures of sender and receiver cell types are used to infer latent cell communication…" / Intro | supports |
| Claim 7 — microenvironment/niche changes cell state | "estimates the effects of niche composition on gene expression" / Abstract | supports |
| Claim 7 — niche effects | "Linear NCEMs were most predictive on an intermediate length scale of 69 µm" / Results | supports |
| Claim 7 — niche effects (magnitude) | "the ΔR2 is small compared to the baseline model R2 … cell type identity accounts for a large fraction of variance" / Results | nuances |
| Claim 7 — niche effects (biology) | "bidirectional dependency of B cells and follicular dendritic cells … germinal center organization" / Results | supports |
| Claim 4 — mechanisms beyond a single modality/channel | "diverse molecular mechanisms not limited to ligand–receptor-based communication … all genes" / Intro | supports |
| Claim 8 — multimodal integration needed | "integrated scRNA-seq with MERFISH data to impute the full gene expression" / Methods | supports |
| Claim 8 — integration adds info | "ligand–receptor nonlinear NCEM … R2 of 0.799 and 0.947" / Results | supports |
| Claim 10 — resolution × throughput × coverage trade-off | "targeted protocols with limited ligand and receptor gene capture" / Intro | supports |
| Claim 10 — limited panel of spatial assays | "131 out of 132 genes from the MERFISH fetal liver (WT) data" / Methods | supports |
| Claim 10 / Standard — QC, segmentation | "Uncertainty in segmentation of cells or nuclei … improved on the level of the spatial measurement" / Discussion | supports |
| Axis A — modality (RNA *and* protein imaging) | "image-structured molecular profiling assays of RNA or proteins with subcellular resolution" / Intro | supports |
| Axis C — spatial resolution / subcellular → tissue | "spatial graphs of cells", "subcellular resolution", "three-dimensional data" / Intro, Discussion | supports |
| Claim 3 — destructive measurement / temporal trajectory | (no time-course or lineage data; single-snapshot spatial only) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Six spatial datasets (Methods, Extended Data Fig. 2) | MERFISH brain: 254 genes, 284,098 cells (2 mice). MERFISH fetal liver: 132 genes, 40,864 WT + 54,970 Tet2−/− cells (E14.5). Chip cytometry colon: 19 genes, 11,321 cells (1 patient). MIBI-TOF cancer (colorectal): 36 genes, 63,747 cells (4 individuals). MELC tonsils: 51 genes, 9,512 cells (1 patient). CODEX cancer (colorectal): 57 genes, 272,266 cells (35 patients). — illustrates small targeted panels (19–254 genes) vs. high cell counts of spatial/imaging assays. |
| Fig. 1c | R² vs. neighborhood resolution for six datasets; linear NCEM vs. nonspatial baseline; peak dependency at ~69 µm; average ΔR² = 0.016; baseline R² range 0.39–0.79. |
| Fig. 1e,f | Linear NCEM vs. nonspatial baseline on deconvoluted Visium lymph-node spots, globally and per cell type (n = 3 CV splits). |
| Fig. 2g,h | Ligand–receptor graph-kernel NCEM on imputed MERFISH fetal liver; peak R² 0.947 (NL-NCEM-LR) vs. 0.799 (NL-NCEM). |
| Variance decomposition (Eq. 1, Methods) | Total single-cell variance = inter-cell-type + intra-cell-type + gene variance; intra-cell-type variance averaged 40.6% of total. |
| Extended Data Fig. 3 | Length scales robust to downsampling, out-of-domain Tet2−/− knockout, simulated segmentation errors (10%/50% of nodes), and removal of interaction terms. |

---

## Primary Sources Behind Key Quotes
- Non-spatial / dissociated ligand–receptor inference tools → NicheNet: Browaeys, Saelens & Saeys, Nat. Methods 17:159–162 (2020), ref 2; CellPhoneDB: Efremova, Vento-Tormo, Teichmann & Vento-Tormo, Nat. Protoc. 15:1484–1506 (2020), ref 3.
- Spatial components of tissue biology (review framing the spatial-data argument) → Palla, Fischer, Regev & Theis, Nat. Biotechnol. 40:308–318 (2022), ref 1.
- Spatial RNA imaging input (MERFISH fetal liver, incl. Kit signaling) → Lu et al., Cell Discov. 7:47 (2021), ref 11.
- Spatial RNA imaging input (MERFISH brain motor cortex) → Zhang et al., bioRxiv 2020.06.04.105700 (2020), ref 12.
- Protein imaging inputs → CODEX: Schürch et al., Cell 183:838 (2020), ref 13; MIBI-TOF: Hartmann et al., Nat. Biotechnol. 39:186–197 (2021), ref 14; MELC: Pascual-Reguant et al., Nat. Commun. 12:1737 (2021), ref 15; chip cytometry: Jarosch et al., Cell Rep. Methods 1:100104 (2021), ref 16.
- Spot deconvolution (extends NCEM to Visium) → cell2location: Kleshchevnikov et al., Nat. Biotechnol. 40:661–671 (2022), ref 19; DestVI: Lopez et al., Nat. Biotechnol. 40:1360–1369 (2022), ref 18.
- spatial + scRNA-seq integration / imputation → Tangram: Biancalani et al., Nat. Methods 18:1352–1362 (2021), ref 21.

---

## Flags
- [ ] Metadata unverified: journal volume and page numbers are not present in the cleaned text. Venue (Nature Biotechnology) and year (online 2022) are confirmed from the peer-review line and DOI prefix s41587; the print citation (likely 2023) is NOT in the text — do not fill it from memory.
- [ ] Source inconsistency: reference 10 reads "Garcia-Alonso, L. et al. … Nat. Genet. 53, 1698–1711 (2011)" — Nat. Genet. vol. 53 corresponds to 2021, so the year "2011" is likely an OCR/cleaning error.
- [ ] Source artifacts: the cleaned reference list contains OCR garbles (e.g., "Teis, F. J." for "Theis, F. J."; "classifcation", "profling", "Te Tabula Sapiens"). Author surname in refs 1/17/23 should read "Theis." Verify spellings against the published version before citing.
- [ ] Scope note (not an error): the paper is single-snapshot spatial; it provides no temporal/time-course, lineage-tracing, or destructive-measurement-pairing evidence, so it does not bear on Claim 3 despite being a spatial-data paper.
- [ ] Read at source: for first-hand spatial-data foundation arguments, Palla, Fischer, Regev & Theis, Nat. Biotechnol. 40:308–318 (2022) (ref 1) is the better primary review to cite than this method paper.
