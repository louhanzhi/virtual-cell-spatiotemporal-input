# Digital Twins of Biological Systems: A Narrative Review — Source Index

**Authors:** Ghufran A. Alsalloum, Nour M. Al Sawaftah, Kelly M. Percival, Ghaleb A. Husseini
**Journal / Venue:** IEEE Open Journal of Engineering in Medicine and Biology, 2024
**DOI:** doi:10.1109/OJEMB.2024.3426916
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/05 Digital Twins of Biological Systems - A Narrative Review (2024)_cleaned.md
**Schema:** 精练-4.0 · citationKey `05`

---

## In One Sentence
A narrative review of digital twin (DT) technology in biomedicine, surveying DT definitions, construction stages, enabling technologies, socio-ethical benefits/risks, and a catalog of DTs of biological systems spanning whole body, organs, tissues, and cells.

## Orientation (non-binding)
Adjacent-domain framing paper rather than a cell-data paper: it conceives of the 'digital twin of a biological system' as requiring continuously updating, multi-source, real-time data, which thematically prefigures our virtual-cell data-standard argument. Most useful for the standard/integration axis (data interoperability, lack of standardized models) and as a foil showing that even a cell-level DT (DeepLife) is built almost entirely on single-cell omics; one quote where a heart DT's accuracy is challenged by 'absence of biochemical data' is a clean, citable concession that single-modality models miss orthogonal information. Can serve as both support (data-bottleneck, integration) and foil (omics-centric cell modeling).

---

## Load-Bearing Excerpts

> "Addressing various challenges in DT applications is crucial – the need for accurate and interoperable data from various sources, a lack of standardized models and protocols, the complexity of representing physiological processes and achieving physical realism and accurate future projections, time-consuming model validation, the cost of infrastructure, data management concerns, continuous model updates, transparency and interpretability, and large-scale computation [13], [24]."
> — Sec. III Benefits, Risks, and Challenges of DTs · bears on: Claim 9 (supports); Standard (supports)
> · Lists accurate/interoperable data and lack of standardized models/protocols as central unmet challenges for DTs.

> "To address these challenges, collaboration between healthcare professionals, data scientists, policymakers, and regulatory bodies is essential. Investments in research, standardization, and governance frameworks are needed to fully leverage the potential of DTs in healthcare while overcoming these obstacles."
> — Sec. III Benefits, Risks, and Challenges of DTs · bears on: Standard (supports)
> · Calls for standardization and governance frameworks as a prerequisite for realizing DT potential.

> "A comprehensive data dimension for storage and analysis, usually in the form of Big Data. Information on the three elements of the DT model to allow for the efficient integration of multi-level data and the extraction of valuable insights."
> — Sec. II Definition, History, and Construction of DTs (planning stage, dimension 4) · bears on: Claim 8 (supports)
> · States that a DT requires efficient integration of multi-level data as a core construction dimension.

> "The real entity, be it a physical product, system, or concept, built from multi-level, multi-scale data – crucial for real-time data collection and feedback from and to the real space."
> — Sec. II Definition, History, and Construction of DTs (planning stage, dimension 1) · bears on: Axis B (supports); Claim 8 (supports)
> · Frames the modeled entity as built from multi-level, multi-scale data with real-time collection and feedback.

> "DTs are distinguished from simulation-only models because they provide a continuous, bidirectional exchange of data between the physical and virtual twins. This closed-loop optimization allows for not only ‘what-if’ simulations, but also for active monitoring, analysis, defect prediction, and forecasting. The data stream within the DT system is dynamic, high-dimensional, decentralized, exponentially growing, and context-aware, offering significant advantages over traditional, static, and fragmented data collection and processing methods."
> — Sec. II Definition, History, and Construction of DTs · bears on: Axis B (supports); Claim 9 (supports)
> · Contrasts the DT's continuous, dynamic, context-aware data stream against static and fragmented traditional data collection.

> "Significant progress has been made in the modeling of cells and cellular structures, with one recent development being the introduction of DeepLife – a platform designed for generating DTs of human cells. DeepLife utilizes omics data to simulate DTs of cells in silico. Shifting from in vitro to in silico analysis for single-cell studies carries significant implications for drug discovery."
> — Sec. IV DTs of Biological Systems · bears on: Claim 1 (nuances); Axis A (challenges)
> · Describes a cell-level DT platform (DeepLife) built on omics data for in silico single-cell modeling and drug discovery.

> "Single-cell omics data is utilized to model cell behavior."
> — Table III (Cells / DeepLife, ref [45]) · bears on: Axis A (challenges)
> · States that the cell DT models cell behavior from single-cell omics data.

> "The GPU-accelerated model utilizes a vast number of spatial degrees of freedom and time steps, capturing the complexity of heart dynamics with impeccable accuracy. However, the absence of biochemical data in building this DT compromises the authors’ claim of accuracy."
> — Sec. IV DTs of Biological Systems · bears on: Claim 4 (supports); Claim 8 (supports)
> · Reviewers concede that the absence of biochemical (molecular) data limits a physics-only heart DT's accuracy claim.

> "In an earlier study, Karr et al. [46] formulated a ’whole-cell’ model for the bacterium Mycoplasma genitalium, a human urogenital parasite with a genome housing 525 genes. The DT model provided insights into numerous previously unobserved cellular behaviors, including in vivo rates of protein-DNA association and an inverse relationship between the durations of DNA replication initiation and replication."
> — Sec. IV DTs of Biological Systems · bears on: Claim 4 (supports); Axis A (supports)
> · Cites the whole-cell Mycoplasma model that integrates genome-scale multi-process data to predict phenotype and molecular kinetics.

> "Du et al. [47] constructed DT models based on image analysis of stem cells, aiming to improve segmentation, detection, and tracking methods of stem cell images in the fields of regenerative medicine and tissue damage restoration."
> — Sec. IV DTs of Biological Systems · bears on: Axis C (supports); Axis B (supports)
> · Describes an imaging-based cell DT performing spatial segmentation/detection and temporal tracking of stem cells.

> "However, it is crucial to keep in mind that while HumMod is a digital representation of the human body, it is not a ‘DT’ as it lacks the bidirectional digital thread and the ongoing data exchange between the physical and the digital entities."
> — Sec. IV DTs of Biological Systems · bears on: Axis B (nuances)
> · Distinguishes a static physiological model from a true DT by the absence of ongoing (temporal) data exchange.

> "The proposed platform uses Big Data and AI to study Multiple Sclerosis patients’ behavioral changes... Highlights the importance of effective data sharing and standardized processing."
> — Table III (Multiple Sclerosis Patients, ref [66]) · bears on: Standard (supports)
> · A cataloged DT explicitly emphasizes effective data sharing and standardized processing.

---

## Figures / Key Numbers

- **Fig. 1:** Scopus query of annual manuscript count with 'Digital Twin' in title/abstract/keywords, showing a significant surge in interest in recent years.
- **Karr et al. whole-cell model:** Mycoplasma genitalium genome of 525 genes; first whole-cell computational model predicting phenotype from genotype.
- **HumMod:** Human physiological model comprising 5000 variables across cardiovascular, respiratory, renal, neural, endocrine, skeletal muscle, and metabolic physiology, with approximately 10000 interconnected algebraic and differential equations.
- **Table III:** Catalog of DTs of biological systems by level (cells, stem cells, brain/neurons, heart, colon, vertebra, ventricle, liver, joints, tumor tissue, nervous system, blood circulation, multiple patient-disease DTs) with references.

---

## Primary Sources (citation provenance)

- **DeepLife: DT of human cells from single-cell omics for drug discovery**
  - Nature feature, 'How digital twins of human cells are accelerating drug discovery', 2022 (online, d43747-022-00108-3)  (45)
- **Whole-cell computational model of Mycoplasma genitalium predicting phenotype from genotype**
  - Karr et al. 2012, Cell 150(2):389-401  (46)
- **GPU-accelerated digital twin of the human heart (physics-based, lacking biochemical data)**
  - Viola, Del Corso, De Paulis, Verzicco 2023, Sci. Rep. 13(1):8230  (40)
- **Image-based DT for segmentation/detection/tracking of stem cell images**
  - Du, Liu, Sun 2022, Comput. Intell. Neurosci. 2022:6003293  (47)
- **Dynamic single-cell-based DT framework to prioritize disease genes and drug targets (cellulome/genome-wide)**
  - Li et al. 2022, Genome Med. 14(1):48  (57)
- **Socio-ethical benefits and risks of DTs in healthcare (basis of Tables I/II)**
  - Popa, van Hilten, Oosterkamp, Bogaardt 2021, Life Sci. Soc. Policy 17(1):1-25  (27)
- **HumMod human physiology simulation environment**
  - Hester et al. 2011, Front. Physiol. 2:12  (48)

---

## Flags / Caveats

- Venue inferred from DOI prefix 10.1109/OJEMB (IEEE Open Journal of Engineering in Medicine and Biology); volume/issue/pages not stated in the cleaned text; recorded as 'IEEE Open Journal of Engineering in Medicine and Biology, 2024' — treat issue/pages as unverified.
- Author order: title-page footer lists 'Ghufran A. Alsalloum, Nour M. Al Sawaftah, Kelly M. Percival, and Ghaleb A. Husseini'; the Author Contributions section lists them in a different order (Alsalloum drafted; Husseini, Percival, Al Sawaftah reviewed). Used the title-page footer order.
- Scope note: This is a healthcare/biomedicine DT review, not a cell-data-acquisition paper; most of its content (organ/patient/disease DTs, IoT, blockchain, socio-ethical tables) is off-roadmap and was not captured. Only lines touching data integration, standardization, temporal/continuous data, modality completeness, and the cell-level DTs were extracted.
- Ref [45] (DeepLife) is a Nature news/feature web item, not a primary research article — the writer should trace to DeepLife's own primary publication if citing the platform first-hand.
- Read at source: ref [46] Karr et al. 2012 Cell (whole-cell model) and ref [40] Viola et al. 2023 Sci. Rep. (heart DT 'absence of biochemical data' concession) are worth citing first-hand.
- OCR quirks preserved verbatim in excerpts (e.g. curly quotes, '’whole-cell’').
