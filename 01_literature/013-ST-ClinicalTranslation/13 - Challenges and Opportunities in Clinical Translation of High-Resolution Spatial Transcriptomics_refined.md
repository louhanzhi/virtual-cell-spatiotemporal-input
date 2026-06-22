# Challenges and Opportunities in the Clinical Translation of High-Resolution Spatial Transcriptomics — Source Index

**Authors:** Tancredi Massimo Pentimalli, Nikos Karaiskos, and Nikolaus Rajewsky
**Journal / Venue:** Annual Review of Pathology: Mechanisms of Disease, 2025, 20:405–432 (first published as a Review in Advance, October 30, 2024)
**DOI:** doi:10.1146/annurev-pathmechdis-111523-023417
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/13 - Challenges and Opportunities in Clinical Translation of High-Resolution Spatial Transcriptomics_cleaned.md

---

## In One Sentence
A review explaining how high-resolution (subcellular) spatial transcriptomics (ST) technologies work, surveying preclinical applications that map cell–cell communication and disease mechanisms in clinical samples, and laying out study-design considerations and remaining barriers to their clinical translation in pathology.

## Orientation (non-binding)
Although framed around clinical pathology rather than virtual cells, this paper is dense routing fuel for our **Spatial axis** — it states repeatedly that tissue dissociation destroys spatial information and that computational spatial reconstruction from dissociated data is unreliable — and for our **Standard axis** — it documents the absence of unified ecosystems, best practices, and benchmarks. It concedes our **Temporal** point directly (ST yields "a single snapshot") and supports our **Multimodal/integration** argument (it argues a holistic view needs genomic/epigenomic/transcriptomic/proteomic/metabolic layers integrated). It can serve BOTH as support (spatial omics as the corrective to dissociation) AND as a foil/nuance (the field it champions is still RNA-centric, snapshot-only, and unstandardized). The downstream agent decides which.

---

## Load-Bearing Excerpts

> "However, current applications mostly rely on bulk readouts, which average gene expression across millions of cells from different cell types and are unable to distinguish clinically relevant disease heterogeneity."
> — Background · bears on: Claim 10 (bulk vs single-cell trade-off), Claim 1 (data limits) · the paper states bulk averaging masks cellular heterogeneity.

> "Despite the power of single-cell technologies, the need for tissue dissociation and the lack of standardized protocols for isolating living cells have so far limited their clinical translation on a broader scale (8)."
> — Background · bears on: Claim 2 (scRNA-seq limits), Standard · dissociation and missing protocols hold single-cell back clinically.

> "Furthermore, tissue dissociation can alter both cellular (e.g., depletion of specific cell types) and molecular readouts [e.g., activation of stress responses (9)], hindering the development of robust and reproducible protocols needed for clinical applications."
> — Background · bears on: Claim 2, Claim 10 (destructiveness) · dissociation itself distorts both which cells and what molecules are measured.

> "While single-nucleus extraction from fresh-frozen (FF) (10, 11) and, recently, formalin-fixed paraffin-embedded (FFPE) (12) clinical samples represents a promising alternative to living cell isolation, tissue dissociation inevitably leads to the loss of spatial information."
> — Background · bears on: Claim 2, Axis C (spatial) · dissociation inevitably loses spatial information.

> "However, the spatial organization of cells in complex tissues is central to understanding how molecular phenotypes emerge, are regulated, and affect tissue function (13)."
> — Background · bears on: Claim 7, Axis C · spatial organization is central to how molecular phenotypes arise and act.

> "While computational tools for the spatial reconstruction of single-cell data with little or no prior knowledge exist (14–16), they rely on the assumption that transcriptomic profiles in neighboring cells are more similar than those that are farther apart, which does not always hold true when tissue organization is disrupted by diseases."
> — Background · bears on: Claim 2, Axis C · in-silico spatial reconstruction from dissociated data rests on an assumption that breaks down in disease.

> "Finally, local interactions in cellular neighborhoods drive coordinated cellular processes, and the loss of spatial positions following tissue dissociation prevents their mapping, limiting our mechanistic understanding of disease processes."
> — Background · bears on: Claim 2, Claim 7, Axis C · losing spatial position prevents mapping cell–cell interactions.

> "In particular, high-resolution spatial transcriptomics (ST) technologies, which profile billions of individual transcripts at subcellular resolution (18), enable the systematic mapping of cell–cell interactions in clinical samples and hold great potential to advance biomedical research and patient care (19)."
> — Background · bears on: Axis C, Claim 7 · definitional: subcellular ST maps cell–cell interactions in tissue.

> "High-resolution spatial transcriptomics (ST) technologies: methods that provide readouts at cellular or even subcellular resolution (i.e., at approximately or less than 10 µm)"
> — Definition box / Technologies · bears on: Axis C, Claim 10 (resolution) · operational resolution threshold (≤~10 µm).

> "the clinical translation of high-resolution ST methods is accelerated by their compatibility with FFPE samples, enabling the retrospective analysis of large archived clinical cohorts and the personalized reconstruction of therapeutic responses from longitudinal samples."
> — Background · bears on: Axis B (temporal via longitudinal sampling), Standard · FFPE compatibility enables archival and longitudinal (over-time) reconstruction.

> "it is worth mentioning that sequencing-based methods, capturing potentially all polyadenylated transcripts, are better poised for hypothesis generation, while probe-based methods, which feature a higher detection efficiency but are restricted to the targeted genes, are more suitable for hypothesis testing."
> — Quantifying Transcripts in Space at High Resolution · bears on: Claim 10 (throughput vs targeting trade-off) · unbiased breadth vs targeted sensitivity is a built-in method trade-off.

> "Nevertheless, ST datasets carry their intrinsic biases (e.g., due to inaccuracies in cell segmentation or transcript displacement during sectioning or capture) (40), requiring the development of ad hoc computational frameworks to address these challenges [e.g., Voyager (41)]."
> — From Transcripts to Cellular Phenotypes · bears on: Claim 9, Standard · ST data carry intrinsic technical biases needing dedicated handling.

> "Although infrastructure (e.g., scalable file formats and structures) and ST-specific databases exist [e.g., STOmicsDB (42)], a unified ecosystem and a set of best practices are still lacking."
> — From Transcripts to Cellular Phenotypes · bears on: Claim 9, Standard · explicit statement that a unified ecosystem and best practices are still missing.

> "Knowledge of cellular coordinates in high-resolution ST datasets enables ad hoc analyses that have not been possible with scRNA-seq data alone."
> — From Single Cells to Virtual Tissue Blocks · bears on: Claim 2, Axis C · spatial coordinates unlock analyses impossible from scRNA-seq alone.

> "While a discussion of specific computational tools is beyond the scope of this review, we would like to point out how best practices still have to be established at this stage. For example, more than 100 different tools exist to map cell–cell interactions (43), and the field still has to converge on standardized approaches, which are urgently needed for clinical applications of ST methods."
> — From Single Cells to Virtual Tissue Blocks · bears on: Claim 9, Standard · >100 competing cell–cell-interaction tools, no convergence on a standard.

> "While spatial analyses are possible in individual 2D sections, cells live and communicate in 3D. Therefore, reconstructing tissue three dimensionally can improve our understanding of disease mechanisms."
> — From Single Cells to Virtual Tissue Blocks · bears on: Axis C (spatial, 3D) · 2D sections miss the 3D reality of cellular communication.

> "it is possible to computationally align the 2D digital imaging and molecular data from consecutive sections using dedicated software [e.g., STIM (44) and PASTE (45)] to create a 3D virtual tissue block."
> — From Single Cells to Virtual Tissue Blocks · bears on: Axis C, Claim 8 (integration) · consecutive 2D sections can be aligned into a 3D "virtual tissue block."

> "As roughly 37 trillion cells compose the human body, mapping their molecular heterogeneity and spatial relationship represents a formidable challenge that the international research community is starting to tackle thanks to the systematic application of high-throughput single-cell and spatial technologies."
> — Building Cellular and Molecular Atlases · bears on: Axis C, Claim 9 (atlas/reference scale) · scale of the spatial-mapping problem (37 trillion cells).

> "High-resolution spatial technologies are already revolutionizing our ability to characterize disease processes at unprecedented resolution, enabling the precise spatiotemporal dissection of disease progression."
> — Unveiling Coordinated Cellular Responses · bears on: Axis B, Axis C, Claim 7 · claims "spatiotemporal dissection" of disease (note: from cross-sectional samples).

> "we leveraged the concept of pseudotime to reconstruct tumor transcriptomic evolution in a non–small cell lung cancer (NSCLC) patient (46). Spatial mapping of pseudotime scores revealed a region of the tumor bed where tumor cells acquired proinvasive properties."
> — Beyond Protein-Coding Genes · bears on: Claim 3, Axis B · temporal trajectory is *inferred* (pseudotime) from a static spatial snapshot, not measured over time.

> "While these methods have proven powerful to identify the spatial architecture and heterogeneity of complex tissues, they were limited in either resolution or gene coverage and often required combination with scRNA-seq data (20, 21)."
> — Unveiling Coordinated Cellular Responses · bears on: Claim 10, Claim 2 · prior spatial methods traded off resolution vs coverage and leaned on scRNA-seq.

> "developments in spatial proteomics methods, such as imaging mass cytometry (75) and multiplexed ion beam imaging (MIBI) (76), enabled the measurement of 30–40 genes at single-cell resolution in large FFPE clinical cohorts."
> — Unveiling Coordinated Cellular Responses · bears on: Claim 6 (spatial proteomics feasible), Claim 10, Axis A (protein) · spatial proteomics works at single-cell resolution but is capped at ~30–40 targets.

> "Anti-tumoral immunity is a highly coordinated response across different components of the TME, which may be only partially captured by the detection of one immune checkpoint molecule. By capturing such multicellular cross talk, high-resolution ST holds great promise for predictive pathology."
> — Leveraging Multicellular Niches as Personalized Biomarkers · bears on: Claim 7, Claim 8 · single-marker readouts under-capture a multicellular, spatially coordinated phenotype.

> "While gene expression is highly informative for identifying cellular types, states, and molecular functions, a holistic understanding of disease processes would benefit from the integrative analysis of cellular genomic, epigenomic, transcriptomic, proteomic, and metabolic layers."
> — Beyond Gene Expression: Multimodal Spatial Omics · bears on: Claim 4, Claim 5, Claim 8, Axis A · explicit case that transcriptome alone is insufficient; multiple molecular layers must be integrated.

> "Rather than analyzing adjacent cells in consecutive sections, true multimodal profiling of the same cells would be desirable to directly relate features across modalities."
> — Beyond Gene Expression: Multimodal Spatial Omics · bears on: Claim 8, Axis A · paired same-cell multimodal measurement (not adjacent sections) is what's actually needed.

> "ST capture of polyadenylated antibody-derived tags [developed for surface epitope profiling in single cells (127)] has been leveraged for the simultaneous profiling of the whole transcriptome and dozens of proteins in space (128, 129)."
> — Beyond Gene Expression: Multimodal Spatial Omics · bears on: Claim 8, Axis A (RNA+protein) · simultaneous spatial transcriptome + dozens of proteins demonstrated.

> "Similarly, a combination of ST with mass spectrometry–based proteomics and metabolomics (MALDI-MSI) has been applied to correlate neurotransmitter levels with gene expression in Parkinson's disease (130) and to study tumor metabolic heterogeneity and immunometabolic rewiring at the invasion margin in gastric cancer (131)."
> — Beyond Gene Expression: Multimodal Spatial Omics · bears on: Claim 8, Axis A (metabolome) · spatial transcriptome paired with MS proteomics/metabolomics.

> "cellular morphology can be integrated with gene expression to resolve cellular subpopulations missed by either modality alone, as demonstrated by Bao and colleagues (132)."
> — Beyond Gene Expression: Multimodal Spatial Omics · bears on: Claim 4, Claim 8, Axis A (imaging/morphology) · one modality misses subpopulations another resolves — non-substitutability.

> "However, the bulk nature of these gene expression measurements, which average across millions of cells in the TME, limited the prediction accuracy of these HE2RNA models. Furthermore, ... the spatial agnostic nature of bulk RNA-seq limited both the interpretability and the validation of such tools, both of which are central to their clinical application and the advancement of scientific knowledge."
> — Toward Affordable Molecular Digital Pathology · bears on: Claim 1, Claim 10, Axis C · spatially-agnostic bulk data caps the accuracy and interpretability of deep-learning models trained on it.

> "In this regard, ST methods provide the missing link between gene expression and H&E morphology and hold great potential for the training of the next generation of deep learning models in pathology."
> — Toward Affordable Molecular Digital Pathology · bears on: Claim 1, Axis C · spatial data positioned as the missing training input bridging molecules and morphology.

> "First, sample preservation strategy imposes a trade-off between sample availability and depth of the molecular readouts: Formalin fixation is well established in routine workflows but inevitably results in RNA fragmentation, while snap-freezing allows the study of intact RNA molecules but requires the implementation of novel sample procedures and prevents the study of archived samples."
> — Challenges Related to the Methods Themselves · bears on: Claim 10, Standard · preservation forces a trade-off between availability and molecular depth.

> "Second, there is currently a trade-off between the number of genes studied and their detection efficiency. On the one hand, imaging-based approaches feature higher sensitivity but are limited to predefined targeted genes, and detection efficiency decreases with increasing panel size. On the other hand, sequencing-based methods can—in principle—capture the whole polyadenylated transcriptome; however, they are biased toward the detection of highly expressed genes."
> — Challenges Related to the Methods Themselves · bears on: Claim 10 · breadth-vs-sensitivity trade-off, with sequencing biased toward highly expressed genes.

> "Furthermore, scalability represents another limit to the implementation of current methods in diagnostic routines. On the one hand, imaging-based methods are largely automated, but they are limited to two to four slides per run and feature long acquisition times, especially when large tissue areas or numerous targets are imaged simultaneously."
> — Challenges Related to the Methods Themselves · bears on: Claim 10 (throughput) · imaging-based ST is throughput-limited (2–4 slides/run, long acquisition).

> "Finally, best practices for accurate cell segmentation, data normalization, clustering, and downstream computational data analyses are still areas of active research."
> — Challenges Related to the Methods Themselves · bears on: Claim 9, Standard · core analysis steps still lack established best practices.

> "To accurately interpret and generate actionable insights from ST data, large-scale healthy and disease references are required. Investigating disease states will be feasible only after the interindividual variability in healthy states has been clearly described (147)."
> — Challenges Related to Result Interpretation and Actionability · bears on: Claim 9, Standard · interpretation requires large standardized healthy/disease reference datasets.

> "It is imperative to expand and integrate these studies into a single, unified database, as has been done, for instance, in the Allen Mouse Brain Atlas (148)."
> — Challenges Related to Result Interpretation and Actionability · bears on: Claim 9, Standard · call to integrate siloed studies into a single unified database.

> "Amassing data from patient cohorts bears substantial benefits, including (a) more accurate characterization of the disease states ... (d) identification of persistently modified molecular readouts, which could potentially serve as disease biomarkers ..."
> — Challenges Related to Result Interpretation and Actionability · bears on: Claim 9 · value of pooled, comparably-processed cohort data.

> "This will require standardized operating procedures controlling all steps from tissue extraction inside the operating room to the generation of the ST datasets and subsequent evaluation of the spatial biomarkers to ensure robust and reproducible readouts for clinical decision-making."
> — Challenges Related to Clinical Implementation · bears on: Claim 9, Standard · end-to-end SOPs needed for robust, reproducible readouts.

> "Even if the current challenges are overcome, ST methods will still be limited to a single snapshot, highlighting the continued need for experimental models to link clinical trials with perturbation studies to move from hypotheses generated by these high-dimensional assays to mechanistic insights."
> — Outlook · bears on: Claim 3, Axis B · KEY concession — ST is intrinsically a single snapshot and cannot supply temporal/perturbation causality on its own.

> "In this regard, the ability to combine organoids with optogenetic perturbations of tissues in time and space, as recently showcased in human brain organoids (149), represents an attractive avenue to link cause and effect in patient-derived models (150)."
> — Outlook · bears on: Claim 3, Axis B, Axis C · perturbation-in-time-and-space (organoids) proposed to recover the cause-and-effect ST cannot capture.

> "Ultimately, the integration of ST and proteomic readouts with emerging spatial genomics, epigenomics, and metabolomics technologies will provide a holistic representation of complex tissues in 2D and 3D (151)."
> — Outlook · bears on: Claim 4, Claim 8, Axis A, Axis C · a holistic tissue representation requires integrating spatial transcriptomic + proteomic + genomic + epigenomic + metabolomic layers.

> "Recently, the availability of extensive digital imaging and transcriptomic datasets enabled the self-supervised training of large-scale AI models, such as Virchow (152) and RudolfV (153), which were trained on billions of histological images, and scGPT, which was trained on more than 33 million single-cell profiles."
> — Outlook · bears on: Claim 1 · foundation-model scale numbers (billions of images; scGPT on >33M single-cell profiles).

> "Fine-tuning these foundation models for several downstream applications can then improve the robustness and generalizability of deep learning predictions when limited training data are available."
> — Outlook · bears on: Claim 1 · foundation models proposed as the remedy for poor generalizability under limited data.

---

## Claim Touchpoints (router — keyed to context-file claim IDs and axes)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 1 — data is the bottleneck; data-driven models generalize poorly | "the bulk nature of these gene expression measurements…limited the prediction accuracy" / Affordable Digital Pathology; "Fine-tuning these foundation models…when limited training data are available" / Outlook | supports |
| Claim 2 — scRNA-seq loses spatial information | "tissue dissociation inevitably leads to the loss of spatial information" / Background; "computational tools for the spatial reconstruction…rely on the assumption…which does not always hold true" / Background | supports |
| Claim 3 — destructive measurement cannot pairwise-observe time | "ST methods will still be limited to a single snapshot" / Outlook; "we leveraged the concept of pseudotime to reconstruct tumor…evolution" / Beyond Protein-Coding Genes | supports / nuances |
| Claim 4 — modalities are orthogonal / mutually non-substitutable | "a holistic understanding…would benefit from the integrative analysis of cellular genomic, epigenomic, transcriptomic, proteomic, and metabolic layers" / Multimodal; "subpopulations missed by either modality alone" / Multimodal | supports |
| Claim 5 — protein/metabolism etc. indispensable for function & phenotype | "integration of ST and proteomic readouts with emerging spatial genomics, epigenomics, and metabolomics" / Outlook | supports |
| Claim 6 — high-throughput spatial proteomics is feasible | "spatial proteomics methods, such as imaging mass cytometry…MIBI…30–40 genes at single-cell resolution in large FFPE clinical cohorts" / Unveiling Coordinated Responses | supports (transcriptomics-centric; protein coverage capped) |
| Claim 7 — spatial organization / microenvironment shapes cell state | "local interactions in cellular neighborhoods drive coordinated cellular processes" / Background; "Anti-tumoral immunity is a highly coordinated response across…the TME" / Personalized Biomarkers | supports |
| Claim 8 — modalities need integration | "true multimodal profiling of the same cells would be desirable to directly relate features across modalities" / Multimodal | supports |
| Claim 9 — data silos / no standard / not comparable | "a unified ecosystem and a set of best practices are still lacking" / Cellular Phenotypes; "more than 100 different tools…the field still has to converge on standardized approaches" / Virtual Tissue Blocks | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "trade-off between sample availability and depth of the molecular readouts" / Methods Challenges; "trade-off between the number of genes studied and their detection efficiency" / Methods Challenges | supports |
| Axis B — temporal | "ST methods will still be limited to a single snapshot" / Outlook; "personalized reconstruction of therapeutic responses from longitudinal samples" / Background | supports / nuances |
| Axis C — spatial | "the spatial organization of cells…is central to understanding how molecular phenotypes emerge" / Background; "cells live and communicate in 3D" / Virtual Tissue Blocks | supports |
| Standard — QC / comparability / integration | "standardized operating procedures controlling all steps…to ensure robust and reproducible readouts" / Clinical Implementation | supports |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Table 1 (commercial methods) | Compares CosMx, Curio Seeker, MERSCOPE, Molecular Cartography, STOmics, Visium HD, Xenium In-Situ on spatial resolution, input material (FF/FFPE), gene-panel (targeted vs unbiased), cost, equipment. Resolutions: MERSCOPE 500 nm; STOmics 0.5 µm; Visium HD 2 µm (probe-based, ~18,000 genes); Curio Seeker 10 µm; CosMx / Molecular Cartography / Xenium single-molecule. |
| Table 2 (noncommercial methods) | DBiT-seq 10/20/50 µm; HDST 2 µm; Open-ST 0.6 µm; SeqFISH single-molecule; Seq-scope 0.6 µm; STARmap 1 µm — with input material, panel, cost, availability. |
| Number — human body scale | "roughly 37 trillion cells compose the human body" (Atlases). |
| Number — MERFISH brain | "more than 1 million cells in the mouse brain"; "70 different neuronal populations" mapped (Moffitt et al., ref 50). |
| Number — spatial proteomics depth | IMC / MIBI: "30–40 genes at single-cell resolution in large FFPE clinical cohorts." |
| Number — sequencing-based spot size | "0.6 µm in Open-ST to 10 µm in Curio Seeker" (Method Selection). |
| Number — imaging throughput | imaging-based methods "limited to two to four slides per run." |
| Number — FFPE section thickness | "5-µm-thick (and even thinner) sections" span part of a single cell along z. |
| Number — foundation-model scale | Virchow/RudolfV "trained on billions of histological images"; scGPT "trained on more than 33 million single-cell profiles." |
| Number — cell–cell-interaction tools | "more than 100 different tools exist to map cell–cell interactions." |
| Figure 4 | Classifies translational challenges into (1) methods themselves, (2) data and interpretation, (3) clinical implementation. |

---

## Primary Sources Behind Key Quotes
- Dissociation alters cellular/molecular readouts (stress responses) → van den Brink SC et al. 2017, Nat. Methods 14(10):935–36 (ref 9)
- Single-cell clinical translation limited by dissociation → Lim J et al. 2023, Nat. Rev. Genet. 24(8):573–84 (ref 8)
- Spatial organization central to molecular tissue biology → Palla G, Fischer DS, Regev A, Theis FJ. 2022, Nat. Biotechnol. 40(3):308–18 (ref 13)
- Spatial reconstruction tools rely on neighbor-similarity assumption → Satija R et al. 2015, Nat. Biotechnol. 33(5):495–502 (ref 14); Karaiskos N et al. 2017, Science 358(6360):194–99 (ref 15); Nitzan M et al. 2019, Nature 576:132–37 (ref 16)
- ">100 tools" to map cell–cell interactions → Armingol E, Baghdassarian HM, Lewis NE. 2024, Nat. Rev. Genet. 25(6):381–400 (ref 43)
- Single-cell & spatial multi-omics landscape → Vandereyken K, Sifrim A, Thienpont B, Voet T. 2023, Nat. Rev. Genet. 24(8):494–515 (ref 125); Baysoy A, Bai Z, Satija R, Fan R. 2023, Nat. Rev. Mol. Cell Biol. 24(10):695–713 (ref 5)
- Whole transcriptome + dozens of proteins in space → Ben-Chetrit N et al. 2023, Nat. Biotechnol. 41(6):788–93 (ref 128); Vickovic S et al. (SM-Omics) 2022, Nat. Commun. 13(1):795 (ref 129)
- ST + MS proteomics/metabolomics (MALDI-MSI) → Vicari M et al. 2023, Nat. Biotechnol. 42:1046–50 (ref 130); Sun C et al. 2023, Nat. Commun. 14(1):2692 (ref 131)
- Morphology + gene expression integration (MUSE) → Bao F et al. 2022, Nat. Biotechnol. 40(8):1200–9 (ref 132)
- "Single snapshot" / organoid optogenetic perturbation in time and space → Legnini I et al. 2023, Nat. Methods 20(10):1544–52 (ref 149); patient-derived organoids → Schutgens F, Clevers H. 2020, Annu. Rev. Pathol. Mech. Dis. 15:211–34 (ref 150)
- Holistic 2D/3D multimodal spatial omics → Bressan D, Battistoni G, Hannon GJ. 2023, Science 381(6657):eabq4964 (ref 151)
- Foundation models → Virchow: Vorontsov E et al. 2023, arXiv:2309.07778 (ref 152); RudolfV: Dippel J et al. 2024, arXiv:2401.04079 (ref 153)

---

## Flags
- [ ] Title note: the cleaned-MD header line concatenates the journal name with the title; the correct article title is "Challenges and Opportunities in the Clinical Translation of High-Resolution Spatial Transcriptomics." Authors, venue (Annu. Rev. Pathol. Mech. Dis. 2025, 20:405–432), and DOI (10.1146/annurev-pathmechdis-111523-023417) are all printed in-text and verified.
- [ ] This is a REVIEW, not a primary source. For every quoted empirical claim, prefer the primary references listed above for first-hand citation (e.g., dissociation-induced stress → ref 9; >100 interaction tools → ref 43).
- [ ] scGPT ("more than 33 million single-cell profiles") is named in the Outlook WITHOUT a numbered citation in this text — verify the scGPT primary source independently before citing it.
- [ ] Page numbers are not mapped per quote (the cleaned MD lacks page anchors); section names are used as jump-back anchors. The article spans pp. 405–432.
- [ ] Scope discipline: the many disease-specific application paragraphs (Alzheimer's, colitis, HCC/PDAC/HNSCC/NSCLC immunotherapy and drug-development case studies) are out-of-scope examples per the context file and were NOT captured individually; only their general conceptual statements (spatial context shapes phenotype, multicellular cross talk, etc.) are indexed above.
- [ ] "Spatiotemporal dissection of disease progression" (Unveiling Coordinated Cellular Responses) and pseudotime use refer to time *inferred* from static spatial snapshots across samples, NOT true paired over-time observation — relevant nuance for Claim 3 / Axis B.
