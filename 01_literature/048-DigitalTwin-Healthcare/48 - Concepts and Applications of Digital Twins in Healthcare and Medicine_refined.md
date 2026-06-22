# Concepts and applications of digital twins in healthcare and medicine — Source Index

**Authors:** Kang Zhang, Hong-Yu Zhou, Daniel T. Baptista-Hon, Yuanxu Gao, Xiaohong Liu, Eric Oermann, Sheng Xu, Shengwei Jin, Jian Zhang, Zhuo Sun, Yun Yin, Ronald M. Razmi, Alexandre Loupy, Stephan Beck, Jia Qu, Joseph Wu, and International Consortium of Digital Twins in Medicine
**Journal / Venue:** Patterns, 2024
**DOI:** doi:10.1016/j.patter.2024.101028
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/03 Concepts and Applications of Digital Twins in Healthcare and Medicine (Patterns 2024)_cleaned.md
**Schema:** 精练-4.0 · citationKey `03`

---

## In One Sentence
A perspective from the International Consortium of Digital Twins in Medicine reviewing the concept, implementation requirements, and current/potential healthcare applications of digital twins, and proposing five hallmarks and a four-stage development roadmap for a medical DT platform.

## Orientation (non-binding)
Operates at the patient/clinical scale (not the cell scale our thesis targets), so most of its content (metaverse, ethics, surgery, hospital administration, LLM agents) is off-roadmap. It is still useful as an adjacent-domain witness on the SAME structural data problems we raise: it concedes data acquisition is the major bottleneck, demands multi-modal integration and interoperability, names data standardization and data silos explicitly, stresses continuous-in-time (temporal) modeling, and flags generalization failure of data-driven models. These map to Claim 1, Claim 8, Claim 9, the Standard axis, and Axis B. A downstream writer can deploy it either as supporting testimony from the medical-DT community or as a foil whose remedies stay at the population/clinical level rather than the cell-level spatiotemporal standard we argue for.

---

## Load-Bearing Excerpts

> "One of the major challenges of a medical DT is the acquisition of sufficient data to make meaningful predictions about the physical entity (the patient)."
> — Challenges and opportunities to DT implementation in medicine — Data acquisition · bears on: Claim 1 (supports)
> · States that data acquisition, not modeling, is the major challenge for a working digital twin.

> "To construct a medical DT with high performance in making efficient and inclusive decisions, integrating large-scale AI models into healthcare is necessary. In addition, high-quality datasets are required to train these integrated AI modules."
> — Challenges and opportunities — Building with AI and metaverse / Opportunities · bears on: Claim 1 (supports)
> · Asserts that high-quality datasets are a prerequisite for training the AI models, framing input data quality as the gating factor.

> "In addition, to handle large amounts of data, the medical DT should be able to ensure real-time data collection, integration, and interoperability among different platforms and systems. The maintenance of data fidelity is also very important."
> — Challenges and opportunities — Data acquisition · bears on: Standard (supports); Claim 9 (supports)
> · Calls for integration and interoperability across platforms plus data-fidelity maintenance as requirements for a DT.

> "There is also a need for health data standardization to enable data integration and interoperability among different DT providers."
> — Challenges and opportunities — Data acquisition · bears on: Standard (supports); Claim 9 (supports)
> · Explicitly names the absence of data standardization as a barrier to integration and interoperability across data providers.

> "Therefore, continuous monitoring of static multi-modal health data, including clinical phenotypes and multi-omics such as genomics, metabolism, physiology, and lifestyle parameters, is required."
> — Challenges and opportunities — Data acquisition · bears on: Claim 8 (supports)
> · States that multi-modal data spanning genomics, metabolism, physiology and phenotype must be monitored together, treating modalities as jointly required.

> "The ultimate application of a medical DT is, therefore, an integration of these multiscale data to observe and predict deviations from the normal state of each individual."
> — Challenges and opportunities — Data acquisition · bears on: Claim 8 (supports)
> · Frames multiscale data integration as the defining goal of a medical DT.

> "Multi-modal LLMs, which encompass diverse input modes in addition to textual inputs within a unified framework, set the stage for a comprehensive approach to healthcare. Addressing these challenges wil require a foundation AI system that is capable of integration and interpretation of multi-modal data and will output with both holistic and specialist modes."
> — Challenges and opportunities — Building with AI and metaverse / Opportunities · bears on: Claim 8 (supports)
> · Argues a foundation AI system must integrate and interpret multi-modal data within a unified framework (OCR quirk: 'wil').

> "Although deep learning models have played a key role in solving important problems in computational biology, they are faced with challenges such as interpretability and generalization."
> — Challenges and opportunities — Challenges · bears on: Claim 1 (supports)
> · Concedes that deep-learning models in biology face generalization (and interpretability) limitations.

> "The degradations in the performance of a model when evaluated on previously unseen data compared with data it has already seen is known as generalization."
> — Challenges and opportunities — Challenges · bears on: Claim 1 (supports)
> · Defines the generalization gap as performance degradation on unseen data, framing it as a core obstacle for DT models.

> "New rules and regulations prohibit institutions from exchanging medical data without patients’ approval, resulting in the occurrence of data silos. Therefore, creative methods are required to coordinate data retrieval while protecting privacy."
> — Challenges and opportunities — Accessibility to data · bears on: Claim 9 (supports)
> · Names data silos as an explicit obstacle, here attributed to privacy regulation rather than to a lack of standards.

> "Progressive twins integrate temporal or progressive information to construct a dynamic statistical machine learning model, which reflects the evolution of the physical entity and reliably forecasts future state transitions. Progressive twins are, therefore, in silico representations that dynamically reflect molecular, physiological, and disease states across time (e.g., aging)."
> — A medical DT: requirements — Development of a medical DT platform — Stage 2: Progressive twins · bears on: Axis B (supports)
> · Defines the temporal stage of DTs as requiring data that reflects molecular/physiological state evolution across time.

> "The classification of experimentally or clinically defined normal or healthy states differs slightly in each individual and cannot be extrapolated to large populations. Currently, treatment personalization relies on low-resolution data and a limited picture of the clinical history of a particular person."
> — Potential implementations — Health and disease management — Individualized homeostasis monitoring · bears on: Claim 1 (supports)
> · Concedes that current personalization is built on low-resolution, partial data, framing data resolution as the limiting input.

> "A medical DT platform can also play an essential role in autoimmune disorders and infectious diseases. This will require multimodal, granular, and integrated information at the molecular, cellular, tissue, organ, and body levels."
> — Potential implementations — Immune responses · bears on: Claim 8 (supports); Axis C (nuances)
> · States that meaningful DTs require integrated multi-modal information across molecular, cellular, tissue, organ and body scales (a multiscale/spatial hierarchy, here at the clinical rather than subcellular level).

> "By combining highthroughput genetic and molecular approaches, single-cell and whole-genome sequencing, big data, cloud-based electronic medical records, and AI, DTs can deliver modern healthcare."
> — Conclusions · bears on: Claim 8 (nuances)
> · Lists the data sources expected to power DTs, centering single-cell and genome sequencing alongside records and AI without naming proteomic, spatial, or temporal trajectory data.

---

## Figures / Key Numbers

- **All of Us program (ref 17):** U.S. NIH program launched in 2018 seeking data from at least 1 million individuals to create one of the largest and most diverse health and genomics datasets.
- **Re-identification (ref 113):** Cited systematic review reportedly found re-identification rates from deidentified data are high.
- **Figure 5 / four-stage roadmap:** DT development stages: Stage 1 Static twins (hypothesis-driven mathematical modeling); Stage 2 Progressive twins (temporal/progressive dynamic modeling); Stage 3 Operational twins (real-time closed-loop physical-virtual interaction); Stage 4 Autonomous twins (merged digital-physical, metaverse).

---

## Primary Sources (citation provenance)

- **All of Us research program (1 million individuals, diverse health/genomics dataset)**
  - All of Us Research Program Investigators, Denny J.C., Rutter J.L., et al. 2019, N. Engl. J. Med. 381:668-676  (17)
- **High-throughput multi-omics profiling of transcriptome, methylome, proteome, histone PTMs, microbiome**
  - Subramanian I., Verma S., Kumar S., Jere A., Anamika K. 2020, Bioinf. Biol. Insights 14:1177932219899051  (18)
- **Multi-modal data integration to advance precision oncology**
  - Boehm K.M., Khosravi P., Vanguri R., Gao J., Shah S.P. 2022, Nat. Rev. Cancer 22:114-126  (27)
- **Transformer-based representation learning with unified processing of multi-modal input for clinical diagnostics**
  - Zhou H.Y., Yu Y., Wang C., et al. 2023, Nat. Biomed. Eng. 7:743-755  (28)
- **Multimodal biomedical AI (multi-modal integration review)**
  - Acosta J.N., Falcone G.J., Rajpurkar P., Topol E.J. 2022, Nat. Med. 28:1773-1784  (39)
- **Reconstructing training data from trained neural networks (re-identification risk)**
  - Haim N., Vardi G., Yehudai G., Shamir O., Irani M. 2022, Preprint at arXiv 2206.07758  (112)
- **Deidentification of wearable data gives false sense of security; re-identification rates high**
  - Chikwetu L., Miao Y., Woldetensae M.K., Bell D., Goldenholz D.M., Dunn J. 2023, Lancet Digit. Health 5:e239-e247  (113)

---

## Flags / Caveats

- Metadata verified from text: DOI 10.1016/j.patter.2024.101028 printed at end of author block (line 486); venue is Patterns, year 2024 (article number 101028, inferred from DOI and filename). No received/accepted/published dates present in the cleaned MD; volume/issue/pages not stated, so venue recorded as 'Patterns, 2024' only.
- Scope note: this is a patient/clinical-scale digital-twin perspective; the large majority of the paper (metaverse, embodied AI agents, LLMs, quantum computing, ethics, surgery, medical devices, hospital administration, synthetic biology) is off-roadmap for our cell-level spatiotemporal data thesis and was not captured. Only lines bearing on data-as-bottleneck, multi-modal integration, standardization/silos, generalization, and temporal modeling were extracted.
- Routing caution: 'multi-modal' and 'multiscale' in this paper denote clinical/omics/lifestyle data integration at the patient level (genomics + physiology + EHR + wearables), NOT the intra-cell modality orthogonality (RNA vs protein vs metabolite) of Claim 4/Claim 8. Excerpts e5/e6/e7/e13/e14 support the general need for integration but do not assert modality non-substitutability; a downstream writer should not over-read them as evidence for Claim 4.
- Counter/foil angle: the paper's proposed remedies (standardization, interoperability, federated learning, larger cohorts such as All of Us) target population/clinical data, leaving the spatial-disaggregation and destructive-measurement constraints our thesis centers on unaddressed at the cell scale. Can be deployed as a same-problem-different-scale foil.
- OCR quirks preserved verbatim in excerpts: 'wil require' (e7); also present elsewhere in source (e.g. 'medica image', 'diabete s').
