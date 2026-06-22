# How to Build the Virtual Cell with Artificial Intelligence: Priorities and Opportunities — Source Index

**Authors:** Charlotte Bunne, Yusuf Roohani, Yanay Rosen, Ankit Gupta, Xikun Zhang, Marcel Roed, Theo Alexandrov, Mohammed AlQuraishi, Patricia Brennan, Daniel B. Burkhardt, Andrea Califano, Jonah Cool, Abby F. Dernburg, Kirsty Ewing, Emily B. Fox, Matthias Haury, Amy E. Herr, Eric Horvitz, Patrick D. Hsu, Viren Jain, Gregory R. Johnson, Thomas Kalil, David R. Kelley, Shana O. Kelley, Anna Kreshuk, Tim Mitchison, Stephani Otte, Jay Shendure, Nicholas J. Sofroniew, Fabian Theis, Christina V. Theodoris, Srigokul Upadhyayula, Marc Valer, Bo Wang, Eric Xing, Serena Yeung-Levy, Marinka Zitnik, Theofanis Karaletsos, Aviv Regev, Emma Lundberg, Jure Leskovec, Stephen R. Quake
**Journal / Venue:** unverified; see flags, 2024
**DOI:** unverified (see Flags)
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/10 How to Build the Virtual Cell with Artificial Intelligence (Bunne 2024)_cleaned.md
**Schema:** 精练-4.0 · citationKey `10`

---

## In One Sentence
A community Perspective (catalyzed by a Chan Zuckerberg Initiative workshop) that proposes the AI Virtual Cell (AIVC): a multi-scale, multi-modal, neural-network foundation-model framework of Universal Representations plus Virtual Instruments, learned directly from biological data, to simulate and predict cell behavior across molecular, cellular and multicellular scales.

## Orientation (non-binding)
This is the flagship AI-Virtual-Cell vision paper and serves as both a named opponent and a supplier of conceded facts. It openly advocates the fully data-driven, transcriptome-anchored foundation-model paradigm our thesis critiques (Claim 1), making its agenda statements deployable as the foil. At the same time it concedes the very gaps we build on: spatial data is limited (Axis C), temporal/dynamic data over short scales is missing and hard to build (Axis B), multi-modal datasets bridging modalities/scales must still be developed (Claim 4/Claim 8), data are biased and need diversity, and open data standards/benchmarks/comparability are lacking (Claim 9). Route both ways; do not sanitize into agreement.

---

## Load-Bearing Excerpts

> "By building on these properties, we argue that we now have the methods to develop a fully data-driven neural network-based representation of an AI Virtual Cell that can accelerate research in biomedicine by enabling fast-paced in silico studies, as well as powerful bridges between computational methods and confirmatory wet-lab experimentation (Fig. 1)."
> — Main · bears on: Claim 1 (challenges)
> · Core agenda statement: the authors assert that methods now exist for a fully data-driven neural-network AIVC; this is the data-driven foundation-model paradigm our thesis critiques.

> "These parallel revolutions provide an unprecedented opportunity for an ambitious vision of an AI Virtual Cell (AIVC), a multi-scale, multi-modal, large neural network-based model that can represent and simulate the behavior of molecules, cells and tissues across diverse states (Fig. 1)."
> — Main · bears on: Claim 1 (challenges)
> · Defines the AIVC as a large multi-scale multi-modal neural network model; the central vision statement positioning the model-centric paradigm.

> "We envision an AI Virtual Cell as a comprehensive AI framework composed of several interconnected foundation models that represent dynamic biological systems at increasingly complex levels of organization—from molecules to cells, tissues, and beyond."
> — Building the AIVC · bears on: Claim 1 (challenges)
> · States the AIVC is built from interconnected foundation models; foregrounds foundation-model architecture as the path forward.

> "Given their prevalence, the cellular UR will initially rely on transcriptomics measurements, while imaging modalities will be key for continued modeling of cellular spatial organization and dynamics."
> — Cellular scale · bears on: Claim 1 (supports); Axis A (supports)
> · Concedes that the cellular representation will initially rely on transcriptomics; admits the RNA-anchored, transcriptome-centric starting point our thesis flags as over-reliance.

> "Multicellular interactions can be analyzed after tissue dissociation (such as in scRNA-seq) or in situ in a 2D section or 3D volume, where the tissue structure is preserved. Building the AIVC will require integration across available modalities that provide spatial insights, i.e., both spatial molecular profiling as well as non-molecular tissue imaging data."
> — Multicellular scale · bears on: Axis C (supports); Claim 2 (supports)
> · Contrasts dissociation-based scRNA-seq with in situ spatial profiling that preserves tissue structure; concedes spatial insight requires integrating spatial molecular profiling and tissue imaging.

> "Spatial molecular biology is currently a very active area of research and method development. While publicly available data are still limited, we foresee a rapid development in this domain providing multi-omic 2D and 3D datasets. A more generalized data generation efort together with open frameworks for spatial data could greatly accelerate modeling at the multicellular scale."
> — Multicellular scale · bears on: Axis C (supports); Claim 2 (supports)
> · Explicit admission that publicly available spatial data are still limited and that generalized spatial data generation plus open frameworks are needed.

> "The AIVC should also have the capability to simulate the temporal evolution of alterations in cell states in response to both intrinsic or extrinsic factors, along with the resulting multicellular spatial arrangements. By modeling the transient nature of the overall cell state and the continuous flux in cellular conditions, the AIVC could uncover previously unstudied trajectories in diverse dynamic processes like development, maintenance of homeostasis, pathogenesis and disease progression."
> — Predicting cell behavior and understanding mechanisms · bears on: Axis B (nuances)
> · Frames temporal/dynamic trajectories as a desired AIVC capability; positions dynamics and trajectories as currently unstudied and to be inferred by the model.

> "Data generation will require simultaneous exploration of temporal and physical scales, while allowing for system perturbations."
> — Data needs and requirements · bears on: Axis B (supports); Axis C (supports)
> · States data must simultaneously span temporal and physical (spatial) scales plus perturbations; concedes the joint time-plus-space data requirement.

> "Furthermore, biological processes span a vast range of timescales, from the fastest reactions happening in picoseconds, to a cell division happening in a day, tumor development occurring over years, and neurodegeneration over decades. The recent construction of universal cell atlases may serve as a powerful resource for modeling cellular behavior over longer time scales, such as tissue formation. New approaches will be needed to build comparable data sets which capture the behavior of cells on shorter times scales, e.g., through methods such as live-cell imaging."
> — Data needs and requirements · bears on: Axis B (supports)
> · Concedes a temporal-data gap: new approaches are needed to build comparable datasets capturing cell behavior on shorter timescales, citing live-cell imaging.

> "Another important driver for the development of AI Virtual Cells will be multi-modal datasets. For example, datasets which bridge molecular and spatial scales, such as single cell transcriptomics data combined with histology to understand how cells interact and what molecular signatures underpin the formation of specialized spatial niches. Further technological development is needed to collect multi-modal data that better captures the relationship between molecular signatures, cell behavior, cellular regulation and organization."
> — Data needs and requirements · bears on: Claim 8 (supports); Claim 4 (supports); Axis C (supports)
> · Concedes that multi-modal datasets bridging molecular and spatial scales are still lacking and that further technological development is needed to collect them.

> "In addition to data size, data diversity is critical to ensure model quality. Data from humans and model organisms like mice and E. coli are unequally represented in sequence and literature databases, which when used for training, encode strong species biases. Other biases, for example towards specific diseases or human ancestral populations could also reduce the impact of AIVC models."
> — Data needs and requirements · bears on: Claim 1 (supports)
> · Concedes data diversity and bias problems that degrade model quality and generalization, supporting the argument that data limitations cap model performance.

> "While a core interest of virtual cell modeling will focus on human datasets for the purpose of understanding disease and aiding the development of novel therapeutics, human datasets are limited in our ability to perform controlled experimentation and perturbations in vivo. Here, the field of 3D tissue biology, including culture systems such as organoids, is emerging as a tool to study the complexities of tissue architecture and function in a 3D environment while allowing perturbations of the system."
> — Data needs and requirements · bears on: Claim 10 (supports)
> · Concedes a trade-off: human datasets are limited for controlled in vivo perturbation, motivating 3D organoid systems; bears on in vitro vs in vivo / controllability trade-offs.

> "These eforts would greatly benefit from open data resources and data standards, a collaborative platform for cell modeling, and especially open benchmark datasets and common validation strategies to ensure their biological fidelity and real-world utility."
> — An open collaborative approach · bears on: Claim 9 (supports); Standard (supports)
> · Calls for open data standards, common benchmark datasets and shared validation strategies, conceding that these are currently lacking.

> "It must account for dynamic distributions that evolve due to environmental changes, infections, genetic variants and other such factors causing distribution shifts."
> — Model evaluation · bears on: Claim 1 (supports)
> · Concedes that AIVC models face distribution shift and must demonstrate generalizability across contexts, bearing on data-driven model generalization concerns.

> "Establishing such cross-modal benchmarks to link scales and modalities in cell biology is of imminent priority to the research community, as these tasks are both biologically useful and well-defined."
> — Model evaluation · bears on: Claim 9 (supports); Standard (supports)
> · States cross-modal benchmarks linking scales and modalities are an imminent priority, conceding their current absence; bears on comparability/standards.

> "The same entity, profiled with diferent technologies, should have the same internal representation in an AIVC."
> — Box 1: Grand challenges for building the AI Virtual Cell (Establishing self-consistency across varying contexts) · bears on: Standard (nuances); Claim 9 (nuances)
> · Sets a self-consistency requirement that the same entity profiled by different technologies map to the same representation; an aspiration that presupposes cross-platform comparability not yet achieved.

> "A fundamental question for the collaborative development of AIVCs is which data and modalities should be collected to enable generalization across biological contexts and scales. These data will need to encompass the breadth of biology in diferent species, domains and modalities, representing the heterogeneity of life, while maintaining depth suficient to distinguish true signals from noise. A key aspect of data generation will be the simultaneous measurement of temporal and physical scales, while also allowing perturbations of the system."
> — Box 1: Grand challenges for building the AI Virtual Cell (Understanding the value of diferent data types) · bears on: Claim 1 (supports); Axis B (supports); Axis C (supports)
> · Frames 'which data and modalities to collect' as a fundamental open question and reiterates the need for simultaneous temporal and spatial measurement with perturbations.

> "While the AIVC would already accurately qualify the change in the expression of genes, tumor sequencing data would allow it to model the change of function of those genes, for example through loss of function, change in post-translational modifications, or rewiring of protein-protein interactions and signaling networks."
> — Unlocking the power of spatial biology to fight cancer · bears on: Claim 4 (supports)
> · Acknowledges that gene-expression change alone does not capture functional change, which is carried by PTMs and protein-protein interaction rewiring; bears on modality non-substitutability.

> "Complementing imaging approaches, mass spectrometry and proximity-dependent labeling can unveil proteinprotein associations and provide deeper insights into cell structure and signaling network rewiring"
> — Cellular scale · bears on: Axis A (supports); Claim 5 (supports)
> · Notes that mass spectrometry and proximity labeling reveal protein-protein associations and signaling rewiring, indicating proteomic measurements carry information beyond imaging/transcriptomics.

> "Spatial structures in cancer, specifically within the tumor microenvironment (TME) are critical drivers of cancer progression, and can drive resistance to the immune system and limit drug eficacy. ... Thus, immune resistance must be understood in the spatial context of the cellular neighborhood in order to identify the specific cell states and gene signatures involved."
> — Unlocking the power of spatial biology to fight cancer · bears on: Claim 7 (supports)
> · States that spatial structure of the tumor microenvironment / cellular neighborhood drives cancer progression and must be understood in spatial context; supports spatial neighborhood effects on cell state.

> "There are multiple methods to profile the spatial location of RNA, and proteins in cells, along with various imaging methods for select molecular species (e.g., immunohistochemistry), or with stains for tissue strucutre alone (e.g., haematoxylin and eosin (H&E))."
> — Multicellular scale · bears on: Claim 2 (nuances)
> · Lists existing methods for spatial profiling of RNA and protein; neutral inventory of spatial-omics methods relevant to the spatial-data axis.

> "Existing cell models are often rule-based and combine assumptions about the underlying biological mechanisms with parameters fit from observational data. ... approaches to date fall short of capturing many aspects of the operations of both bacteria and more complex systems, such as human cells"
> — Main · bears on: Claim 1 (nuances)
> · Characterizes prior rule-based/mechanistic cell models as falling short, motivating the shift to data-driven models; frames both mechanistic and data-driven approaches as currently limited.

---

## Figures / Key Numbers

- **First whole-cell model (2012):** Represented all 482 genes and molecular functions known for the bacterium Mycobacterium genitalium.
- **Data growth rate:** Reference datasets with data doubling every six months for the past several years (ref 31).
- **Short Read Archive scale:** Holds over 14 petabytes of biological sequence data, more than one thousand times larger than the dataset used to train ChatGPT (refs 142, 143).
- **Timescales of biological processes:** Span picoseconds (fastest reactions) to a day (cell division) to years (tumor development) to decades (neurodegeneration).
- **Fig. 1:** Capabilities of the AI Virtual Cell: Universal Representation across species/conditions/modalities/scales (molecular, cellular, multicellular); representation/prediction, dynamics, in silico experimentation; human interaction layers.
- **Fig. 2:** Overview of the AIVC across three physical scales (molecular, cellular, multicellular) built from Universal Representations and operated on by Virtual Instruments (Manipulators and Decoders).

---

## Primary Sources (citation provenance)

- **First whole-cell computational model (M. genitalium, 482 genes)**
  - Karr, J. R. et al. A whole-cell computational model predicts phenotype from genotype. Cell 150 (2012)  (9)
- **Data doubling every six months / scalable querying of cell atlases**
  - Heimberg, G. et al. Scalable querying of human cell atlases via a foundational model reveals commonalities across fibrosis-associated macrophages. bioRxiv (2023)  (31)
- **Subcellular location of the human proteome via fluorescence imaging**
  - Thul, P. J. et al. A subcellular map of the human proteome. Science 356 (2017)  (79)
- **Spatiotemporal single-cell proteogenomics (proteome at single-cell level)**
  - Mahdessian, D. et al. Spatiotemporal dissection of the cell cycle with single-cell proteogenomics. Nature 590 (2021)  (75)
- **Mass spectrometry / multiscale proteomic organization of phenotypes**
  - Cesnik, A. et al. Mapping the Multiscale Proteomic Organization of Cellular and Disease Phenotypes. Annual Review of Biomedical Data Science 7 (2024)  (86)
- **Number of human proteoforms (proteome complexity beyond genes)**
  - Aebersold, R. et al. How many human proteoforms are there? Nature Chemical Biology 14 (2018)  (171)
- **Multi-scale map of cell structure fusing protein images and interactions**
  - Qin, Y. et al. A multi-scale map of cell structure fusing protein images and interactions. Nature 600 (2021)  (87)
- **Graph deep learning of tumour microenvironment from spatial protein profiles**
  - Wu, Z. et al. Graph deep learning for the characterization of tumour microenvironments from spatial protein profiles in tissue specimens. Nature Biomedical Engineering 6 (2022)  (187)
- **Cancer cell states recur across tumor types and interact with TME**
  - Barkley, D. et al. Cancer cell states recur across tumor types and form specific interactions with the tumor microenvironment. Nature Genetics 54 (2022)  (169)

---

## Flags / Caveats

- Metadata unverified: the cleaned MD contains no DOI and no venue/received/accepted/published line; the references list has no entry for this paper itself. venue set to 'unverified; see flags' and doi set to null. Filename attributes it to Bunne 2024; widely circulated as a Chan Zuckerberg Initiative community Perspective / preprint (arXiv:2409.11654), but this could not be confirmed from the source text.
- Year '2024' inferred from the filename and from in-text references dated 2024 (e.g., refs 49, 66, 67, 86); not printed as a publication date in the body.
- Authors transcribed verbatim from the 'Authors' section; superscript affiliation/contribution markers were stripped. Corresponding authors (marked with double-dagger): Theofanis Karaletsos, Aviv Regev, Emma Lundberg, Jure Leskovec, Stephen R. Quake. Co-first authors (asterisk): Charlotte Bunne, Yusuf Roohani, Yanay Rosen.
- OCR quirks preserved verbatim in excerpts (e.g., 'diferent', 'eforts', 'efects', 'efort', 'difusion', 'strucutre', 'proteinprotein', 'lab-in-theloop', 'nearatomic'); not corrected.
- Scope note: large portions of this Perspective (Virtual Instruments architecture, model evaluation specifics, interpretability, AI technique boxes on transformers/CNNs/diffusion/GNNs, drug-discovery/diagnostics application vignettes) are about modeling methods, which are out of scope per the context file; only lines bearing on the data-foundation roadmap claims were captured.
- This paper is the primary advocacy source for the data-driven AIVC paradigm; its agenda statements (e1-e3) are routed as 'challenges' to Claim 1 because they embody the model-centric paradigm our thesis critiques, while its data-gap admissions (e4-e17) are routed as 'supports'. Downstream agent should decide deployment as foil vs conceded-fact.
- Read at source: ref #75 (Mahdessian, Nature 590, 2021, single-cell proteogenomics) and ref #86 (Cesnik, Annu Rev Biomed Data Sci 7, 2024, multiscale proteomic organization) are worth first-hand reading for the spatiotemporal-proteomics capability argument (Claim 6).
