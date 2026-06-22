# DeepSea is an efficient deep-learning model for single-cell segmentation and tracking in time-lapse microscopy — Source Index

**Authors:** Abolfazl Zargari, Gerrald A. Lodewijk, Najmeh Mashhadi, Nathan Cook, Celine W. Neudorf, Kimiasadat Araghbidikashani, Robert Hays, Sayaka Kozuki, Stefany Rubio, Eva Hrabeta-Robinson, Angela Brooks, Lindsay Hinck, S. Ali Shariati
**Journal / Venue:** Cell Reports Methods, 2023, 3(6):100500 (ISSN 2667-2375)
**DOI:** doi:10.1016/j.crmeth.2023.100500
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/30_cleaned.md

---

## In One Sentence
The authors build DeepSea, a compact deep-learning model plus a user-friendly software, to automatically segment and track individual mammalian cells across phase-contrast time-lapse microscopy sequences (including mitosis/lineage detection), report higher precision than prior segmentation and tracking tools, and showcase it by quantifying cell-size control across full cell-cycle trajectories in mouse embryonic stem cells.

## Orientation (non-binding)
This is a methods/modality paper for non-destructive, label-free live-cell imaging — the modality that can re-observe the *same* single cell over time and reconstruct real birth-to-division trajectories and lineage trees. It most likely feeds Axis B (temporal) and Claim 3 (destructive sequencing cannot pair-observe time → here is the imaging route that directly can), and Axis A (imaging/morphology as a modality). It can serve BOTH as support (real single-cell temporal trajectories and lineage tracking are achievable) AND as a foil/nuance (imaging here captures only morphology/dynamics — size, shape, cycle — not molecular content, illustrating the per-modality complementarity and the resolution-vs-content trade-off). Secondary touchpoints: data-as-bottleneck and benchmark comparability (Claims 1, 9). The downstream agent decides the role.

---

## Load-Bearing Excerpts

> "Time-lapse microscopy is the only method that can directly capture the dynamics and heterogeneity of fundamental cellular processes at the single-cell level with high temporal resolution."
> — § SUMMARY · bears on: Claim 3, Axis B · the paper claims live imaging is uniquely able to directly capture single-cell dynamics over time.

> "Time-lapse microscopy allows for direct observation of cell biological processes at the single-cell level with high temporal resolution."
> — § MOTIVATION · bears on: Claim 3, Axis B · direct (non-inferred) single-cell temporal observation.

> "In recent years, it has become clear that single-cell-level analysis over time is essential for revealing the dynamics and heterogeneity of individual cells."
> — § INTRODUCTION (cites refs 2,3) · bears on: Axis B, Claim 3 · temporal single-cell analysis stated as essential.

> "Single-cell quantitative live microscopy can directly capture both dynamics and heterogeneity of cellular decisions by continuous long-term measurements of cellular features."
> — § INTRODUCTION (cites refs 4,5) · bears on: Axis B, Claim 3 · continuous long-term per-cell measurement.

> "Widely available microscopy techniques such as label-free phasecontrast live microscopy allow for monitoring the dynamics of morphological features such as the size and shape of the cells."
> — § INTRODUCTION · bears on: Axis A (imaging/morphology), Axis B, Claim 3 · label-free (non-destructive) imaging tracks morphological dynamics.

> "Typical live-cell imaging of biological features of cells is a multi-day experiment that produces several gigabytes of images collected from thousands of cells."
> — § INTRODUCTION (cites ref 4) · bears on: Claim 10, Axis B · scale/throughput of multi-day live imaging.

> "With this model, we could monitor multiple cellular phenotypes and several cell division cycles across the microscopy image sequences to generate lineage tree structures of cells."
> — § RESULTS (Designing and training a cell segmentation and tracking model) · bears on: Claim 3, Axis B · lineage-tree reconstruction across division cycles.

> "This test uses the trained tracking model to track and label the target single-cell motion trajectories across the live-cell microscopy frame sequences from birth to division."
> — § RESULTS (DeepSea performance evaluation) · bears on: Claim 3, Axis B · same-cell trajectory from birth to division.

> "It shows that the higher sampling rate reduces the tracking model failures, especially for the cells that move and change quickly over time."
> — § RESULTS (DeepSea performance evaluation) · bears on: Axis B, Claim 10 · temporal sampling rate affects ability to follow fast-changing cells.

> "DeepSea was able to outperform existing state-of-the-art models such as CellPose, StarDist, and 2D-UNET in terms of latency and mean average precision (mAP) when trained on the same training sets and tested on the same test sets at all pre-defined IoU thresholds."
> — § RESULTS (DeepSea performance evaluation) · bears on: Claim 9, Claim 1 · same-data benchmark comparison across tools.

> "Together, our results show that DeepSea can be applied to accurately quantify cell biological features of cells, such as cell size or cell cycle duration."
> — § RESULTS (Cell cycle duration is adjusted based on birth size) · bears on: Axis A (imaging/morphology), Axis B · imaging yields quantitative morphological/temporal phenotypes.

> "Although phase-contrast microscopy is a non-invasive and widely used method for livecell imaging, developing automated segmentation and tracking algorithms remains challenging."
> — § DISCUSSION · bears on: Claim 3, Axis A · phase-contrast imaging is explicitly non-invasive (non-destructive).

> "The lack of a comprehensive, high-quality annotated dataset of cells prevents the full utilization of DL-based models for microscopy image analysis systems."
> — § DISCUSSION · bears on: Claim 1, Claim 9 · data (annotation) scarcity stated as the bottleneck for DL models.

> "We generated large manually annotated datasets of time-lapse microscopy images of three cell types, which are publicly available and can be used for new image analysis models."
> — § DISCUSSION · bears on: Claim 1, Claim 9, standard · curated open annotated dataset as a reusable resource.

> "We would like to note that our dataset and models are limited to the phase contrast 2D images of three cell types."
> — § Limitations of the study · bears on: Claim 1, Axis C · scope limited to 2D phase-contrast, three cell types (no 3D/tissue context).

> "A larger dataset of samples from different cell types and different imaging modalities would be useful for testing our proposed model's generalization, reliability, and robustness."
> — § Limitations of the study · bears on: Claim 1 · author-conceded limit on generalization across cell types/modalities.

> "Our DeepSea tracking model achieved a MOTA value of 0.94 ± 0.2 compared with the Trackmate model, which had a MOTA of 0.29 ± 0.7 ... In the evaluation process, we used 228 full ground-truth cell cycle trajectories, each including more than three consecutive frames."
> — § RESULTS (DeepSea performance evaluation) · bears on: Claim 3, Axis B, Claim 9 · quantitative full-cycle tracking accuracy vs prior tool.

> "Our segmentation model was trained on our generated dataset and achieved an IoU value of 0.90 ± 0.2 at the IoU matching threshold of 0.5."
> — § DISCUSSION · bears on: Axis A · quantitative segmentation accuracy.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 3 — destructive measurement can't pair-observe time; need trajectory/lineage | "Time-lapse microscopy is the only method that can directly capture…" / § Summary; "track and label the target single-cell motion trajectories … from birth to division" / § Results; "generate lineage tree structures of cells" / § Results | supports |
| Axis B — temporal (time course / trajectories per modality) | "single-cell-level analysis over time is essential…" / § Intro; "higher sampling rate reduces the tracking model failures…" / § Results | supports |
| Axis A — modality (imaging / morphology) | "label-free phasecontrast live microscopy allow for monitoring the dynamics of morphological features…" / § Intro; "DeepSea can be applied to accurately quantify cell biological features … cell size or cell cycle duration" / § Results | supports |
| Claim 3 — non-destructive measurement | "phase-contrast microscopy is a non-invasive and widely used method for livecell imaging" / § Discussion | supports |
| Claim 1 — data is the bottleneck; DL generalization | "The lack of a comprehensive, high-quality annotated dataset … prevents the full utilization of DL-based models" / § Discussion; "limited to the phase contrast 2D images of three cell types" / § Limitations | supports / nuances |
| Claim 9 — data silos, standards, cross-study comparability | "trained on the same training sets and tested on the same test sets" / § Results; "publicly available and can be used for new image analysis models" / § Discussion | nuances |
| Claim 10 — resolution × throughput × destructiveness trade-off | "multi-day experiment that produces several gigabytes of images collected from thousands of cells" / § Intro; non-invasive but morphology-only imaging | nuances |
| Axis C — spatial (subcellular → tissue) | only 2D in-frame localization; "limited to the phase contrast 2D images" / § Limitations (no tissue microenvironment) | — |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Figure 1 | Segmentation model evaluation: average precision vs IoU thresholds and per-image latency for DeepSea vs CellPose, StarDist, 2D-UNET; easy (sparse) vs hard (dense) images; per-cell-type performance. |
| Figure 4 | Tracking model evaluation on the test set (single-cell tracking AP and mitosis detection). |
| Figure 5 | Example full cell-cycle tracking from nine consecutive stem-cell frames (20-min sampling); daughter cells linked to mothers. |
| Figure 6 / 7 | Showcase: cell-size regulation in mouse embryonic stem cells; cell-cycle distribution, birth-size ratio histogram, cell-cycle duration vs birth size; G1 duration via Fucci sensor; cell area vs volume by confocal. |
| Tracking precision | Single-cell tracking precision 0.98 ± 0.2 (@0.5 IoU); mitosis detection precision ~0.89 ± 0.3 (@0.5 IoU). |
| Segmentation accuracy | IoU 0.90 ± 0.2 at 0.5 IoU matching threshold; reported to outperform CellPose, StarDist, 2D-UNET on same train/test sets. |
| Full-cycle tracking | MOTA 0.94 ± 0.2 (DeepSea) vs 0.29 ± 0.7 (TrackMate); evaluated on 228 full ground-truth cell-cycle trajectories (each >3 consecutive frames). |
| Temporal sampling | Sub-sampling intervals of 5, 10, and 15 min tested; precision sensitive to frame time distance; higher sampling rate reduces failures. |
| Dataset scale | Three cell types: mouse embryonic stem cells (31 sets, 1074 images), bronchial epithelial cells (7 sets, 2010 images), C2C12 muscle progenitor cells (7 sets, 540 images); publicly released. |
| Cell-biology showcase | mESC cell cycle ~10 h with ultrafast G1 ~2 h; 42% of divisions yield daughter cells of different sizes; smaller-born cells extend cell-cycle duration by ~2 h vs larger sisters. |

---

## Primary Sources Behind Key Quotes
- "single-cell-level analysis over time is essential for revealing dynamics and heterogeneity" → Bogdan, P. et al. (2014), Sci. Rep. 4:4826 (ref 2); Semrau, S. et al. (2017), Nat. Commun. 8:1096 (ref 3).
- "live microscopy can directly capture dynamics/heterogeneity by continuous long-term measurements" → Skylaki, S., Hilsenbeck, O., Schroeder, T. (2016), Nat. Biotechnol. 34:1137–1144 (ref 4); Chessel, A., Carazo Salas, R.E. (2019), Essays Biochem. 63:197–208 (ref 5).
- Cell heterogeneity under identical conditions / single-cell fate decisions → Fiorentino, J., Torres-Padilla, M.-E., Scialdone, A. (2020), Annu. Rev. Genet. 54:167–187 (ref 1).
- Cell-size control in the G1 phase (showcase context) → Zatulovskiy, E., Skotheim, J.M. (2020), Trends Genet. 36:360–372 (ref 33).

---

## Flags
- [ ] Metadata verified from source text: title, full author list (§ Authors), venue Cell Reports Methods 3(6):100500, ISSN 2667-2375, DOI 10.1016/j.crmeth.2023.100500, and dates (Received July 11, 2022; Revised Feb 1, 2023; Accepted May 17, 2023; Published June 12, 2023) are all printed in the cleaned MD — no reconstruction needed.
- [ ] OCR artifacts in source: the cleaned MD joins some words ("phasecontrast", "livecell") and encodes numeric results in broken LaTeX (e.g. "$0 . 9 8 \pm \ : 0 . 2$"); inline citation markers appear as superscripts. Excerpts above reproduce the authors' wording with these artifacts normalized to plain numbers/spelling; nothing substantive altered.
- [ ] Scope note (per context file boundary "do not write modeling methods"): the paper's model-architecture content (scaled-down UNET, residual connections, progressive learning, auxiliary edge layer, loss functions Eq.1–5, parameter counts 1.9M/2.1M, augmentation scheme) was deliberately NOT captured as off-roadmap; available in § Results / STAR★METHODS if needed.
- [ ] Read at source: for the "imaging directly observes single cells over time" claim, refs 4 (Skylaki 2016, Nat. Biotechnol., challenges in long-term single-cell imaging) and 2/3 are worth citing first-hand rather than via this methods paper.
