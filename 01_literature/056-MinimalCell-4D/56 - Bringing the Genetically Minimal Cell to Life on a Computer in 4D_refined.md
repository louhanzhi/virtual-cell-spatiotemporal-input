# Bringing the genetically minimal cell to life on a computer in 4D — Source Index

**Authors:** Z.R. Thornburg, A. Melo, T.A. Brier, B.R. Gilbert, T. Wu, W. Pezeshkian, H. Liu, E. Fischer, T. Lai, J. Kim, Y.-L. Gao, L. Sun, J. Qian, D.M. de Castro Bittencourt, J.I. Glass, T. Hwang, A.P. Mosalaganti, Z. Luthey-Schulten, et al. (author initials/order reconstructed from Author Contributions; see flags)
**Journal / Venue:** Cell, 2026; volume/issue/pages unverified; see flags
**DOI:** doi:10.1016/j.cell.2026.02.009
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/11 Bringing the Genetically Minimal Cell to Life on a Computer in 4D (Cell 2026)_cleaned.md
**Schema:** 精练-4.0 · citationKey `11`

---

## In One Sentence
The authors build a 4D (3D space + time) whole-cell spatial-kinetic model (4DWCM) of the entire ~105 min cell cycle of the genetically minimal bacterium JCVI-syn3A, simulating all 493 genes, metabolism, ribosome/RNAP/degradosome assembly, chromosome replication and dynamics, growth, and division, and validating it against doubling time, ori:ter ratio, mRNA half-lives, protein counts, and fluorescence imaging.

## Orientation (non-binding)
A mechanistic, physics-based whole-cell model that explicitly encodes time AND 3D space and is constrained by a wide array of experiments (proteomics, DNA-seq, fluorescence imaging, cryo-ET, metabolomics) - it directly exemplifies Axis B (temporal/4D) and Axis C (spatial), and its limitations sections list precisely the spatiotemporal/multimodal datasets that are still missing. It positions itself as COMPLEMENTARY to ML/AI virtual cells (Claim 1), conceding that no single experiment captures a whole cell and that data assimilation across many experiments is required (Claim 8). Can serve both as support (a worked case of why time+space+multimodal data are needed) and as a contrast point (a mechanistic alternative to data-driven AIVC).

---

## Load-Bearing Excerpts

> "To develop a full understanding of the rules governing cellular life, we must know the complete quantitative characteristics of cells as a function of time and space (4D) and how the underlying chemical and physical processes act in unison to drive changes in cell state. Determining the molecular composition and architecture of an entire cell simultaneously is not currently possible with any single experiment, but there have been significant strides in computational modeling of cell states, as well as emerging efforts to concatenate the growing number of large biological datasets to form snapshots of cell states using machine learning (ML) and artificial intelligence (AI)."
> — INTRODUCTION · bears on: Axis B (supports); Axis C (supports); Claim 1 (supports)
> · States that understanding cellular life requires complete quantitative characteristics as a function of time AND space (4D), and that no single experiment can determine whole-cell composition and architecture at once.

> "However, predicting snapshots of a cell state using ML or AI methods, both in molecular composition and physical characteristics, is a product of sampling possible outcomes and will not tell us about the underlying biological, chemical, and physical processes that caused the temporal progression of the cell’s state."
> — INTRODUCTION · bears on: Claim 1 (nuances); Axis B (supports)
> · Argues ML/AI snapshot prediction samples outcomes but does not reveal the processes driving the temporal progression of cell state - a distinction between mechanistic and data-driven cell modeling.

> "FBA has proven to be a useful tool for predicting average behavior and even making claims about gene essentiality, but it lacks dynamics and cell-to-cell heterogeneity."
> — INTRODUCTION · bears on: Axis B (supports)
> · Concedes that steady-state flux balance analysis lacks temporal dynamics and cell-to-cell heterogeneity.

> "Although the kinetic models include reaction dynamics to dictate temporal progression of the cell state, they treat cells or cell compartments primarily as well-stirred systems lacking heterogeneous spatial organization. These well-stirred models have proven themselves as predictive tools, but they cannot probe the dependence of stochastic processes on the spatial localization of molecular participants (e.g., RNA polymerase [RNAP] must diffuse and bind to promoters on the DNA)."
> — INTRODUCTION · bears on: Axis C (supports)
> · Identifies that prior well-stirred kinetic whole-cell models lack spatial organization and cannot capture how stochastic reactions depend on spatial localization of molecules.

> "Syn3A’s minimal genome and annotated gene essentialities, proteomics, transcriptomic and DNA sequencing data, essential metabolic map, cryo-electron tomograms (cryo-ET), chromosome contact maps, predicted structural proteome, and now imaging of the symmetric division and additional DNA sequencing make it a strong candidate for whole-cell modeling over its entire cell cycle."
> — INTRODUCTION · bears on: Claim 4 (supports); Claim 8 (supports); Axis C (supports)
> · Enumerates the heterogeneous multimodal datasets (genome, proteomics, transcriptomics, DNA-seq, metabolic map, cryo-ET, chromosome contact maps, structural proteome, fluorescence imaging) that the whole-cell model integrates.

> "To fully understand and characterize the spatial dynamics that dictate life for Syn3A, we need to simulate the entire cell cycle, including DNA replication and dynamics, ribosome movement, and division in 4D. Here, we present a 4D whole-cell model (4DWCM) that simulates the entire cell cycle of Syn3A, including expression of all 493 genes, kinetics of the entire metabolic network, ribosome biogenesis, chromosome dynamics (including DNA replication), and morphological changes during growth and division."
> — INTRODUCTION · bears on: Axis B (supports); Axis C (supports)
> · Defines the 4D whole-cell model spanning an entire cell cycle with spatial dynamics, all 493 genes, full metabolism, chromosome dynamics, and morphology.

> "By creating a model that imposes spatial heterogeneity and its inherent stochasticity on reactions such as DNA replication initiation, transcription, translation, and mRNA degradation, we uncover the dependence, sensitivity, and variations of cell cycle progression on key rates in the 4D dynamics. Overall, we analyzed the cell cycle dynamics of 50 unique replicate cells."
> — INTRODUCTION · bears on: Axis C (supports); Axis B (supports)
> · States that spatial heterogeneity and stochasticity were imposed on core reactions and 50 replicate cell cycles were analyzed, capturing cell-to-cell variation.

> "Cells are not well-stirred reactor systems. Their intracellular environment is spatially heterogeneous and consists of many slowmoving, low-population components that need to encounter each other in 3D space for these components to react and perform their biological functions."
> — DISCUSSION · bears on: Axis C (supports)
> · Central spatial argument: the intracellular environment is spatially heterogeneous and reactions depend on components encountering each other in 3D space.

> "The spatial heterogeneity of the intracellular environment can strongly affect biochemical reactions that control phenotypes."
> — In brief · bears on: Axis C (supports); Claim 7 (supports)
> · Asserts that spatial heterogeneity of the intracellular environment strongly affects the biochemical reactions controlling phenotype.

> "Unfortunately, no one organism has a complete set of experimentally determined kinetic parameters, chemical composition, and physical characteristics, so the model we present here, as well as other whole-cell models, has depended on the transferability of quantities among related organisms."
> — DISCUSSION · bears on: Claim 1 (supports); Claim 8 (supports)
> · Author-conceded data limitation: no organism has a complete experimentally determined parameter/composition set, forcing reliance on borrowing parameters from related organisms.

> "Individual datasets alone may not be enough to validate the individual cell states predicted by our 4DWCM. The variations that we predict in the macromolecular composition of daughter cells highlight the need for compiled predictions of complete cell states using experimental measurements at different points in the cell cycle."
> — DISCUSSION · bears on: Claim 8 (supports); Axis B (supports)
> · Concedes that single datasets cannot validate predicted cell states and calls for compiled measurements at different time points across the cell cycle.

> "Assimilation of the data to construct these snapshots of cells at different points in time draws attention to the significant value in the growing interest of using ML and AI to build virtual cells from quantitative measurements from a wide array of experiments. We see virtual cells and the 4DWCM as complementary methods to assemble cell states and then predict how the chemical and physical processes drive the changes between the predicted states."
> — DISCUSSION · bears on: Claim 1 (nuances); Claim 8 (supports); Axis B (supports)
> · Frames AI virtual cells (assembling snapshots from a wide array of experiments) and the mechanistic 4DWCM as complementary, with the model predicting transitions between states.

> "Finally, there are still several organism-specific datasets required for a full-confidence validation of our 4DWCM, as discussed above. The most significant datasets are quantitative metabolomics, genome-wide mRNA half-lives, proteome-wide protein half-lives, a survey of DNA-associated proteins, and long-read transcriptomics to tell us about operonal structures."
> — Limitations of the study · bears on: Claim 4 (supports); Claim 8 (supports); Axis B (supports)
> · Lists the missing organism-specific multimodal/temporal datasets (quantitative metabolomics, genome-wide mRNA half-lives, proteome-wide protein half-lives, DNA-associated protein survey, long-read transcriptomics) needed to fully validate the model.

> "The model captures the origin-to-terminus ratio measured in our DNA sequencing and recovers other experimental measurements, such as doubling time, mRNA half-lives, protein distributions, and ribosome counts. Because of stochasticity, each replicate cell is unique. We predict not only the average behavior of partitioning to daughter cells but also the heterogeneity among them."
> — SUMMARY · bears on: Claim 1 (supports); Axis B (supports)
> · States the model recovers multiple independent experimental measurements (ori:ter, doubling time, mRNA half-lives, protein distributions, ribosome counts) and predicts cell-to-cell heterogeneity in daughter partitioning.

> "The predicted doubling time is in very close agreement with the experimental doubling time of 105 min. We made a similar prediction in our previous wellstirred model, but the predicted doubling time was 97 min."
> — 4D whole-cell modeling reflects experiment · bears on: Claim 1 (supports)
> · Quantitative validation: predicted doubling time (105 min) matches the experimental doubling time of 105 min.

> "By uniformly sampling time points throughout the average simulated cell cycle, our simulations exhibit an ori:ter ratio of 1.28. In whole-genome sequencing (WGS), we calculate an average ori:ter ratio of 1.21 for both late- and mid-exponential phase cells and 1.0 for stationary phase cells (Figures 4B and S2)."
> — 4D whole-cell modeling reflects experiment · bears on: Claim 1 (supports); Axis B (supports)
> · Quantitative validation against the paper's own DNA sequencing: simulated ori:ter 1.28 vs measured 1.21 (exponential) / 1.0 (stationary).

> "The distribution of morphologies for 1,319 analyzed cells (Figure S2) is shown in Figure 4D. Spherical cells appear larger than previous cryo-ET, but this discrepancy is consistent with observations for similar organisms, where cell sizes can vary by hundreds of nanometers depending on the imaging method and sample preparation."
> — 4D whole-cell modeling reflects experiment · bears on: Axis C (supports); Claim 9 (nuances)
> · Fluorescence imaging of 1,319 cells constrains morphology; notes cell-size discrepancies of hundreds of nm between imaging methods and sample preparations.

> "We combine the new fluorescence imaging and previous cryo-ET observations into two constraints on the morphology during our simulations, such that the cell (1) grows spherically from 200 to 250 nm in radius (∼98% increase in cell volume), given our coarse-grained resolution of 10 nm lattice cubes, and then (2) maintains a constant volume as the surface area grows during symmetric division until the end of the cell cycle."
> — 4D whole-cell modeling reflects experiment · bears on: Axis C (supports); Claim 8 (supports)
> · Combines new fluorescence imaging and prior cryo-ET as spatial morphology constraints (200 to 250 nm radius growth) on the simulation.

> "Through fluorescence imaging of JCVI-syn3B, a variant of Syn3A with a ‘‘landing pad’’ system to mediate genetic modification, we observe that the minimal cell undergoes roughly symmetric division. Dividing cell shapes most frequently exhibit prolate (early cell division state) and dumbbell-like (late cell division state) morphologies."
> — 4D whole-cell modeling reflects experiment · bears on: Axis C (supports); Axis B (supports)
> · Live-cell fluorescence imaging captures spatial division morphology and its temporal stages (prolate early, dumbbell-like late).

> "Because we track every transcription, translation, and mRNA degradation event, we can calculate the average translation efficiency and mRNA half-life for every type of mRNA in Syn3A, as shown in Figures 5G and 5H, respectively."
> — Activity of gene expression complexes and competition for mRNA · bears on: Axis B (supports)
> · Because the model tracks every molecular event in time, it yields per-mRNA temporal quantities (translation efficiency, mRNA half-life) not directly measurable in a single destructive experiment.

> "Concentrations of 1–10 mM GTP and 8 mM UTP have been estimated for E. coli, but no measurement has been performed yet in Syn3A."
> — Genetic information reactions and metabolism are codependent · bears on: Claim 4 (supports); Claim 8 (supports)
> · Author-conceded data gap: metabolite (NTP) concentrations were borrowed from E. coli because no measurement exists for Syn3A.

> "The pools of metabolites, with initial conditions based on measurements in E. coli, dictate the synthesis rate of macromolecules such as DNA and RNA, and the uptake rates of lipids determine the rate of growth for the membrane."
> — Genetic information reactions and metabolism are codependent · bears on: Claim 4 (supports)
> · Metabolite pools (a non-transcriptomic modality) causally drive DNA/RNA synthesis rates and membrane growth - illustrating that metabolism carries information not in RNA counts.

> "Although our doubling time is in close agreement with experimental data, the protein abundances obtained from our wellstirred model, which included polysomes for a fixed cell geometry, are in better agreement with experimental proteomics. The proteomics comparison suggests that polysomes are important for doubling the proteome in a cell cycle, especially for large proteins."
> — Limitations of the study · bears on: Claim 4 (supports)
> · Uses experimental proteomics as ground truth to evaluate protein production; concedes protein-level (not RNA-level) effects (polysomes) are needed to match proteome doubling.

> "Our current and previous models have all parameterized the promoter strengths based on the quantitative proteomics data, limiting the transferability of the transcription model to other organisms. A model based on quantitative transcriptomics to help connect expression levels to sequence predictions of promoter sites and transcription termination sites should be more transferable to other bacteria."
> — Limitations of the study · bears on: Claim 4 (supports); Claim 8 (nuances)
> · Notes the model parameterizes transcription from proteomics counts; argues quantitative transcriptomics would improve transferability - a statement on complementary multimodal data needs.

> "Among the most significant limitations of our 4DWCM is the required computational time and resources to achieve statistically significant sampling. Our simulations require 4–6 days of computational time on two high-performance computing GPUs per cell cycle. To obtain the 50 replicate cell cycles presented here required roughly 15,000 GPU h (625 GPU days) on NVIDIA A100 GPUs. This limits the sampling that can be performed to small populations of cells."
> — Limitations of the study · bears on: Claim 10 (nuances)
> · Author-conceded trade-off: high spatial/temporal resolution (4D) is computationally costly (4-6 days/cell, 15,000 GPU h for 50 cells), limiting population size - a resolution vs throughput tension.

> "Although we cannot simulate large numbers of cells with 4D models, and well-stirred models lack the predictive power of 4D models, we can build the crossroads between the two levels of complexity to accelerate the development of more predictive wholecell models."
> — Limitations of the study · bears on: Claim 10 (nuances); Axis C (supports)
> · Frames a resolution/throughput trade-off: 4D models are more predictive but cannot scale to many cells; well-stirred models scale but lack predictive power.

> "We previously hypothesized that the lifetime of a mRNA depends on the spatial proximity of the gene to the membrane where the degradosomes are located. ... Gene-membrane proximity was averaged over the entire cell cycle, and we tried to correlate the proximity with bulk properties, including mRNA degradation rate, mRNA halflife, and protein production rate. We found no statistically significant correlations."
> — Limitations of the study · bears on: Axis C (nuances)
> · Tests but does not confirm a spatial hypothesis: gene-to-membrane proximity showed no statistically significant correlation with mRNA half-life or protein production in these small cells.

> "The artificial 12 pN force to partition chromosomes to daughter cells draws into question the predictive power of the physica model of chromosome dynamics. We found that the physical locations of genes within these small cells do not appear to correlate with bulk properties such as mRNA lifetimes, so the overal outcomes and predictions of our spatial reaction model should still hold even with a more biologically informed model of chromosome partitioning."
> — Limitations of the study · bears on: Axis C (nuances)
> · Author-conceded limitation: an artificial 12 pN force was needed to partition chromosomes (keep OCR quirks 'physica', 'overal'), questioning the predictive power of the spatial chromosome model.

> "Although our model has made many predictions, it is still incomplete, and there are some important ingredients yet to be included: transcription of polycistronic RNA from operonal structures, coupled genetic information processing reactions, a kinetic model of FtsZ to drive cell division, and assembly reactions for all macromolecular complexes."
> — Limitations of the study · bears on: Claim 8 (nuances)
> · Lists model components still missing (polycistronic transcription, coupled processes, FtsZ kinetics, complex assembly), each requiring further specific data.

> "The fraction of ribosomes involved in polysomes has been measured or experimentally estimated in several bacteria, including 20%–40% in Syn3A, 26.2% in Mycoplasma pneumoniae, and up to 70% in E. coli."
> — Activity of gene expression complexes and competition for mRNA · bears on: Claim 1 (nuances)
> · Cites organism-to-organism variation in polysome fractions (20-40% Syn3A, 26.2% M. pneumoniae, up to 70% E. coli), illustrating non-transferability of measured parameters across organisms.

> "Such datasets include high-resolution structural data for Syn3A’s morphology and lipidomics studies that quantified the effects of controlled lipid diets on the growth rate and morphology of Syn3A."
> — Limitations of the study · bears on: Claim 4 (supports); Axis C (supports)
> · Points to lipidomics and high-resolution structural (morphology) datasets as foundations for future model components - additional non-transcriptomic modalities.

---

## Figures / Key Numbers

- **Doubling time:** Predicted membrane doubling 105 min and chromosome doubling 51 min on average; matches experimental doubling time of 105 min; previous well-stirred model predicted 97 min.
- **B/C/D periods (Figure 4A):** Average B period ~5 min (ori:ter 1:1), C period 46 min (2:1), D period 54 min (2:2).
- **ori:ter ratio (Figures 4B, S2):** Simulated 1.28; WGS measured 1.21 (mid/late-exponential), 1.0 (stationary); prior evolution study 1.0-1.2.
- **DNA replication elongation rate:** Model uses 100 bp/s (M. capricolum); using 600 bp/s (E. coli) would give ori:ter ~1.05.
- **Lattice resolution:** RDME cubic lattice with 10 nm edge length; chromosome as circular homopolymer of 10 bp monomers; cell grows from 200 to 250 nm radius (~98% volume increase).
- **Complex counts (Figures 5A-5D):** RNAP increases 0 to 93, degradosomes 0 to 120; RNAP total reduced from 187 to 93 by proteomics-informed stoichiometry; ~100 SSU/LSU intermediates await ribosomal proteins.
- **Active fractions (Figure 5E):** ~55% ribosomes, ~70% RNAP, ~10% degradosomes active on average; E. coli ribosome active fraction estimated up to 85%.
- **mRNA half-lives (Figure 5H):** Previous simplified 4D average/median 1.97/1.48 min; distribution fits B. subtilis observed range <1 to 20 min; mRNA-to-ribosome binding rate x1.3, mRNA-to-degradosome binding x0.3 vs prior model.
- **Transcription (Figure 5K):** Average dnaA transcription ~55% of max elongation rate (~11 nt/s), range ~30-80%; limited by UTP and GTP pools (~0.3 mM, sometimes depleted); E. coli estimates 1-10 mM GTP, 8 mM UTP.
- **Untranscribed genes (Figure 5I):** 81 genes untranscribed in 1-3 of 50 simulated cells; all low proteomics value (<60), mostly unknown function.
- **Cell morphology imaging (Figure 4D, S2):** 1,319 cells analyzed; ~15% of late-exponential cells contained cell-in-cell structures.
- **Replication initiation (Figure 5J):** DnaA on/off rates 100 mM-1 s-1 / 0.55 s-1 failed to initiate; revised 140 mM-1 s-1 / 0.42 s-1 initiates within first 15 min in nearly all cells; filament length 20-23 DnaA at initiation.
- **Partitioning force:** Repulsive 12 pN force (5 kBT / 1.7 nm) applied between daughter chromosomes to achieve segregation.
- **Computational cost:** 4-6 days per cell cycle on two HPC GPUs; ~15,000 GPU h (625 GPU days) on NVIDIA A100 for 50 replicate cells; hook frequency 250 RDME steps = 12.5 ms biological time.
- **Genome scale:** JCVI-syn3A: 543 kbp single circular chromosome, 493 genes, doubling time 105 min.
- **Scope:** 50 unique replicate cells simulated and analyzed over the entire ~100 min cell cycle in 4D.

---

## Primary Sources (citation provenance)

- **AI virtual cell vision (data assimilation from many experiments)**
  - Bunne C, et al. 2024, Cell 187:7045-7063  (5)
- **Prior well-stirred whole-cell kinetic model of the minimal cell (parameters, polysomes, doubling)**
  - Thornburg ZR, et al. 2022, Cell 185:345-360.e28  (1)
- **First whole-cell computational model predicting phenotype from genotype (M. genitalium)**
  - Karr JR, et al. 2012, Cell 150:389-401  (3)
- **Whole-cell model of E. coli via mechanistic simulation across heterogeneous datasets**
  - Macklin DN, et al. 2020, Science 369:eaav3751  (4)
- **Essential metabolism and metabolic map / doubling time of the minimal cell**
  - Breuer M, et al. 2019, eLife 8:e36842  (18)
- **Genetic requirements for division; Syn3A regular division/morphology**
  - Pelletier JF, et al. 2021, Cell 184:2430-2440.e16  (19)
- **Cryo-ET and chromosome contact maps of the minimal cell (spatial constraints)**
  - Gilbert BR, et al. 2021, Front. Mol. Biosci. 8:644133  (21)
- **SMC condensin loop-extrusion rate measurements (kinetic parameters)**
  - Ganji M, et al. 2018, Science 360:102-105  (26)
- **DnaA filament on/off binding rates (single-molecule, used for replication initiation)**
  - Cheng H-M, et al. 2014, Nucleic Acids Res. 43:396-405  (50)
- **E. coli metabolite concentrations used as initial conditions**
  - Park JO, et al. 2016, Nat. Chem. Biol. 12:482-489  (52)
- **Adaptive evolution of the minimal cell; ori:ter coverage and tetM mutations**
  - Sandberg TE, et al. 2023, iScience 26:107500  (20)
- **Lattice Microbes RDME simulation software**
  - Roberts E, Stone JE, Luthey-Schulten Z 2012, J. Comput. Chem. 34:245-255  (28)
- **Quantitative metabolomics / metabolite damage in the minimal genome (needed dataset)**
  - Haas D, et al. 2022, mBio 13:e0163022  (62)
- **Controlled lipid-diet effects on Syn3A growth and morphology (lipidomics)**
  - Justice I, et al. 2024, Nat. Commun. 15:9679  (63)

---

## Flags / Caveats

- Metadata: DOI confirmed from text supplemental link (10.1016/j.cell.2026.02.009); journal Cell confirmed from self-citations and supplemental DOI prefix; volume/issue/pages NOT printed in cleaned MD - left unverified.
- Dates from text: Received June 10, 2025; Revised December 9, 2025; Accepted February 9, 2026; Published March 9, 2026.
- Authors: full author list with given names is NOT printed in the cleaned MD body; the authors string was reconstructed from initials in the Author Contributions and Acknowledgments sections (e.g., Z.R.T.=Z.R. Thornburg, Z.L.-S.=Z. Luthey-Schulten, A.M.=A. Melo inferred, J.I.G.=J.I. Glass, D.M.d.C.B.=D.M. de Castro Bittencourt). Several initials (A.P.M., T.H., T.A.B., B.R.G., E.F., T.W., W.P., H.L., T.L., J.K., Y.-L.G., L.S., J.Q.) could not be fully expanded from the text - treat author full names as unverified.
- Lead contact confirmed: Zaida Luthey-Schulten (zan@illinois.edu).
- OCR quirks preserved verbatim in excerpts (e.g., 'physica model', 'overal outcomes' in e28; 'wellstirred', 'halflives' elsewhere) and not corrected.
- Scope note: This is a mechanistic physics/kinetics whole-cell simulation, not an experimental data-production paper; its strongest relevance to our thesis is (a) as a concrete demonstration that 4D = explicit time + 3D space is required, and (b) its candid limitations enumerating missing spatiotemporal/multimodal datasets (metabolomics, mRNA/protein half-lives, DNA-associated proteins, long-read transcriptomics, lipidomics).
- Scope note: STAR Methods (growth media, primers, RDME equations, BD/LAMMPS implementation details) are largely off-roadmap and were not captured except where they state data sources or constraints.
- Read at source: ref #5 (Bunne et al. 2024, 'How to build the virtual cell with AI') is the AIVC reference this paper engages with directly - worth first-hand for our virtual-cell framing.
- Mendeley Data DOI for FtsZ plasmid: 10.17632/x59cx6ns2h.1; Zenodo code/data: 10.5281/zenodo.15579158; DNA-seq at NCBI SRA PRJNA1257452.
