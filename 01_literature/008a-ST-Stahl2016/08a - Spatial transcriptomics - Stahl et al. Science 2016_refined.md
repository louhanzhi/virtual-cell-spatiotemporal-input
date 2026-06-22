# Visualization and analysis of gene expression in tissue sections by spatial transcriptomics — Source Index

**Authors:** Patrik L. Ståhl, Fredrik Salmén, Sanja Vickovic, Anna Lundmark, José Fernández Navarro, Jens Magnusson, Stefania Giacomello, Michaela Asp, Jakub O. Westholm, Mikael Huss, Annelie Mollbrink, Sten Linnarsson, Simone Codeluppi, Åke Borg, Fredrik Pontén, Paul Igor Costea, Pelin Sahlén, Jan Mulder, Olaf Bergmann, Joakim Lundeberg, Jonas Frisén
**Journal / Venue:** Science, 2016, 353(6294):78–82
**DOI:** doi:10.1126/science.aaf2403
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/08a - Spatial transcriptomics - Stahl et al. Science 2016_cleaned.md

---

## In One Sentence
The authors introduce "spatial transcriptomics," a method that places intact histological tissue sections onto a glass surface arrayed with positionally barcoded reverse-transcription primers, so that genome-wide RNA-seq can be performed while preserving the two-dimensional position of each transcript; they demonstrate it on mouse olfactory bulb and human breast cancer tissue.

## Orientation (non-binding)
This is the founding spatial-transcriptomics method paper and sits squarely on the context file's **spatial axis (Axis C)** and **Claim 2** (dissociation/homogenization destroys spatial information → spatial-omics methods). It explicitly states that standard tissue RNA-seq of homogenized biopsies "results in an averaged transcriptome and loss of spatial information," and offers a remedy — making it usable as the canonical example of the spatial gap our thesis builds on. It also touches **Claim 7** (spatial heterogeneity in cancer that bulk cannot see), **Claim 10** (explicit resolution/sensitivity trade-off numbers vs. smFISH, scRNA-seq, LCM, ISH), and **Claim 9** (in-section processing removes technical variation; whole-section permanent resource). Note the scope limits: this method is **RNA/transcriptome only** and contains **no protein modality and no temporal/time-course dimension**, so it does not feed Axis A's protein argument or Axis B directly.

---

## Load-Bearing Excerpts

> "Analysis of the pattern of proteins or messenger RNAs (mRNAs) in histological tissue sections is a cornerstone in biomedical research and diagnostics. This typically involves the visualization of a few proteins or expressed genes at a time."
> — Abstract · bears on: Axis C (spatial), Claim 2 · states the pre-existing spatial readouts were limited to a few targets at a time.

> "We have devised a strategy, which we call "spatial transcriptomics," that allows visualization and quantitative analysis of the transcriptome with spatial resolution in individual tissue sections."
> — Abstract · bears on: Claim 2, Axis C · defines the method: transcriptome-wide measurement with spatial resolution.

> "By positioning histological sections on arrayed reverse transcription primers with unique positional barcodes, we demonstrate high-quality RNA-sequencing data with maintained two-dimensional positional information from the mouse brain and human breast cancer."
> — Abstract · bears on: Claim 2, Axis C · describes the barcoding mechanism that retains 2D position.

> "Tissue transcriptomes are typically studied by RNA-sequencing (RNA-seq) of ho-mogenized biopsies, which results in an averaged transcriptome and loss of spatial information."
> — Introduction · bears on: Claim 2, Axis C, Claim 1 · the core fact our thesis builds on — homogenized/dissociated RNA-seq averages out and loses spatial information.

> "The positional context of gene expression is of key importance to understanding tissue functionality and pathological changes."
> — Introduction · bears on: Axis C, Claim 7 · asserts that spatial/positional context is essential to tissue function and pathology.

> "Several strategies have recently been developed with this aim, but they have limitations in the number of transcripts that can be analyzed, rely on rich preexisting data sets, and/or are costly and labor-intensive, and none of them are operational in the standard research and diagnostic setting of regular histological tissue sections."
> — Introduction · bears on: Claim 10, Claim 2 · names the trade-offs/limitations of prior spatial methods (transcript count, prior-data dependence, cost, non-standard).

> "By comparing the hematoxylin-and-eosin and fluorescent signals, we could measure the average distance of diffusion outside the border of a cell to 1.7 ± 2 m (mean ± SD) (fig. S1, E to H)."
> — Results (cDNA localization) · bears on: Axis C, Claim 10 · quantifies lateral diffusion / spatial fidelity of captured cDNA (~1.7 µm; OCR dropped the µ).

> "We deposited 200 million oligonucleotides in each of 1007 features, with a diameter of 100 m and a center-to-center distance of 200 m, over an area of 6.2 mm by 6.6 mm (fig. S2)."
> — Results (array design) · bears on: Axis C, Claim 10 · array geometry — 1007 features, 100 µm feature diameter, 200 µm pitch (i.e. multi-cell-resolution, not single-cell; OCR dropped the µ).

> "Comparison with data from RNA extracted and fragmented in solution revealed that 95% of the genes found with one of the methods was also found with the other (fig. S3C). The correlation between the surface and in-solution libraries was = 0.94... Replicates of surface-based experiments of adjacent tissue sections showed a correlation of = r0.97 (fig. S3E)."
> — Results (library validation) · bears on: Claim 9, Claim 10 · quantitative reproducibility: 95% gene overlap, r=0.94 surface vs. in-solution, r=0.97 between adjacent-section replicates (OCR garbled the "r =" notation).

> "The number of genes and transcripts captured was at least twice as high as when using laser capture microdissection, and spatial transcriptomics detected almost twice as many genes as examination by in situ hybridization in the Allen Brain Atlas (fig. S5, C and D)."
> — Results (sensitivity comparison) · bears on: Claim 10, Claim 2 · ~2× more genes/transcripts than laser capture microdissection and ~2× more genes than in situ hybridization.

> "The sensitivity of spatial transcriptomics was 6.9 ± 1.5% of singlemolecule fluorescent in situ hybridization (fig. S6). By comparison, single-cell RNA sequencing has been reported to have about 5 to 40% sensitivity."
> — Results (sensitivity comparison) · bears on: Claim 10 · author-conceded sensitivity figure — 6.9 ± 1.5% of smFISH, set against scRNA-seq's reported 5–40% (OCR joined "singlemolecule").

> "When placing back the clustered features on the tissue images, it was apparent that each cluster of features largely corresponded to well-defined morphological layers (Fig. 4B)."
> — Results (clustering) · bears on: Axis C, Claim 7 · unsupervised molecular clusters map onto known spatial/morphological tissue layers.

> "Analysis of the ductal cancer in situ areas revealed a surprisingly high degree of heterogeneity in gene expression between these regions, probably reflecting different subclones, with varying expression of several genes implicated in cancer progression (Fig. 4E and fig. S11C)."
> — Results (breast cancer) · bears on: Claim 7, Axis C · spatially resolved intratumor heterogeneity / subclones revealed within a single biopsy.

> "Thus, spatial transcriptomics revealed unexpected heterogeneity within a biopsy, which would not be possible to detect with regular transcriptome analysis and which may give more detailed prognostic information."
> — Results (breast cancer) · bears on: Claim 7, Claim 2, Axis C · explicit statement that spatial resolution surfaces heterogeneity that bulk/regular transcriptome analysis cannot detect.

> "In contrast to standard methods, different domains of the tissue are processed in the same reaction in spatial transcriptomics, which removes technical variation between samples."
> — Discussion · bears on: Claim 9, Axis C (standard/integration) · in-section, single-reaction processing eliminates between-sample technical variation.

> "A unique feature of spatial transcriptomics is that any gene expression profile can be selected to specify a molecularly defined domain for further analysis."
> — Discussion · bears on: Axis C, Claim 7 · domains can be defined by molecular profile rather than by physical dissection or marker labeling.

> "Finally, in contrast to when different regions of a tissue are dissected for analysis, the information for the whole section is maintained; hence, the analysis is not limited to the initially selected regions. An individual spatial transcriptomics experiment thus serves as a permanent resource to investigate gene expression patterns for future research questions."
> — Discussion · bears on: Claim 9, Axis C · whole-section information is preserved, making each experiment a re-queryable permanent resource.

> "Spatial transcriptomics offers an alternative approach that circumvents multiplex labeling and cell isolation. Any combination of presence or absence of expression for a set of genes can be used to define a marker profile of interest for further analysis."
> — Results (marker-defined domains) · bears on: Claim 2, Axis C · the method avoids cell isolation/dissociation while still allowing marker-based population definition.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 2 — scRNA-seq / homogenization loses spatial info → spatial-omics methods | "Tissue transcriptomes are typically studied by RNA-sequencing… loss of spatial information" / Introduction | supports |
| Axis C — spatial (subcellular → cell → tissue microenvironment) | "spatial transcriptomics… transcriptome with spatial resolution in individual tissue sections" / Abstract | supports |
| Claim 7 — spatial organization / microenvironment changes cell state & is invisible to bulk | "spatial transcriptomics revealed unexpected heterogeneity within a biopsy… not possible to detect with regular transcriptome analysis" / Breast cancer | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "sensitivity of spatial transcriptomics was 6.9 ± 1.5% of singlemolecule fluorescent in situ hybridization… scRNA-seq… 5 to 40%" / Sensitivity; "diameter of 100 m… 200 m" / Array design | nuances |
| Claim 9 — data islands / cross-experiment comparability / standards | "different domains… processed in the same reaction… removes technical variation"; "information for the whole section is maintained… permanent resource" / Discussion | supports |
| Claim 1 — data is the bottleneck / input quality caps modeling | "averaged transcriptome and loss of spatial information" / Introduction | nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Fig. 1 | Spatially localized cDNA synthesis workflow; H&E vs. Cy3-labeled fluorescent cDNA after tissue removal; cDNA localizes directly under individual cells (mouse olfactory bulb). |
| Fig. 2 | Array feature design (cleavage site, T7 handle, spatial barcode, UMI, oligo(dT) VN capture); spatial expression vs. in situ hybridization (Penk, Doc2g, Kctd12); genes-per-feature distribution; genes vs. sequencing depth by layer; lateral-diffusion test in MCL/GCL. |
| Fig. 3 | Tissue domains defined by morphology or expression profile; homologous regions = no differentially expressed genes; different domains differ (170 DEGs); interneuron markers Camk4/Th/Vip define transcriptomes (196 and 328 DEGs in the two comparisons). |
| Fig. 4 | t-SNE + hierarchical clustering of 551 features → 5 clusters mapped back onto tissue; breast cancer biopsy: invasive ductal cancer + 6 ductal-cancer-in-situ areas; ECM-gene heat map; EMT-implicated genes high only in areas 1 and 5. |
| Key numbers | Feature diameter 100 µm, pitch 200 µm, 1007 features, area 6.2 × 6.6 mm; 200 million oligos/feature; diffusion 1.7 ± 2 µm; surface vs. in-solution 95% gene overlap, r = 0.94; adjacent-section replicate r = 0.97; sensitivity 6.9 ± 1.5% of smFISH; scRNA-seq reported 5–40% sensitivity; ~2× genes/transcripts vs. LCM; ~2× genes vs. ISH (Allen Brain Atlas). |

---

## Primary Sources Behind Key Quotes
- scRNA-seq "about 5 to 40% sensitivity" → D. Grün, A. van Oudenaarden, Cell 163:799–810 (2015), ref #12.
- Homogenized-biopsy / bulk RNA-seq baseline → Z. Wang, M. Gerstein, M. Snyder, Nat. Rev. Genet. 10:57–63 (2009), ref #1.
- Prior spatial strategies "with limitations" → N. Crosetto, M. Bienko, A. van Oudenaarden, Nat. Rev. Genet. 16:57–66 (2015), ref #2; R. Satija et al., Nat. Biotechnol. 33:495–502 (2015), ref #3; P. A. Combs, M. B. Eisen, PLOS ONE 8:e71820 (2013), ref #4; K. Achim et al., Nat. Biotechnol. 33:503–509 (2015), ref #5.
- Laser-capture-microdissection comparison → S. Zechel, P. Zajac, P. Lönnerberg, C. F. Ibáñez, S. Linnarsson, Genome Biol. 15:486 (2014), ref #11.
- t-SNE algorithm used for dimensionality reduction → L. J. P. van der Maaten, G. E. Hinton, J. Mach. Learn. Res. 9:2579–2605 (2008), ref #15.

---

## Flags
- [ ] OCR artifacts in the cleaned source: the micro sign (µ) was dropped throughout, so feature size reads "100 m / 200 m" and diffusion "1.7 ± 2 m" (true units are µm); "singlemolecule" and "ho-mogenized" are word-join/hyphen artifacts; the "r =" correlation notation is garbled to "= 0.94 / = r0.97". Excerpts are quoted as they appear in the cleaned file — verify exact glyphs against the original Science PDF if quoting in print.
- [ ] Reference-number gaps: several in-text citation markers were stripped during cleaning (empty parentheses). The primary-source mappings above are inferred from citation order and the reference list; reconfirm ref #12 (scRNA-seq sensitivity) and refs #2–5 (prior strategies) against the original before first-hand citation.
- [ ] Scope note (not a defect): this paper is transcriptome/RNA-only and has no protein modality and no temporal/time-course data — so it does not bear on Axis A's protein argument or Axis B (temporal); resolution is multi-cell (100 µm features), not single-cell.
- [ ] Metadata is fully confirmed from the text (title, all 21 authors, Science 353(6294):78–82, DOI 10.1126/science.aaf2403, received 12 Jan 2016 / accepted 31 May 2016 / published 30 June 2016) — no metadata reconstruction needed.
