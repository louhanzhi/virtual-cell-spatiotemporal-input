# Fundamental behaviors emerge from simulations of a living minimal cell — Source Index

**Authors:** Zane R. Thornburg, David M. Bianchi, Troy A. Brier, Benjamin R. Gilbert, Marcelo C.R. Melo, Emmy E. Earnest, Nataliya Safronova, James P. Sáenz, András T. Cook, Kim S. Wise, Clyde A. Hutchison III, Hamilton O. Smith, John I. Glass, Zaida Luthey-Schulten
**Journal / Venue:** Cell, 2022, 185(2):345-360
**DOI:** doi:10.1016/j.cell.2021.12.025
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/09 Fundamental Behaviors Emerge from Simulations of a Living Minimal Cell (Thornburg 2022)_cleaned.md
**Schema:** 精练-4.0 · citationKey `09`

---

## In One Sentence
The authors build a whole-cell, fully dynamical kinetic model of the minimal bacterium JCVI-syn3A (493 genes) that integrates cryo-electron tomography geometry, proteomics, lipidomics, metabolomics, and literature kinetic parameters into 3D-spatial and well-stirred stochastic-deterministic simulations, producing time-dependent concentrations, fluxes, and emergent behaviors over a complete cell cycle.

## Orientation (non-binding)
A mechanistic whole-cell modeling paper, not a measurement-paradigm paper, but highly relevant as a concrete worked example of the data inputs a cell-scale dynamical model demands: it explicitly assembles 3D spatial architecture (Axis C), time-course trajectories over a cell cycle (Axis B), and multiple integrated -omics modalities (Claim 4/8), and openly concedes that no single bacterium has a complete parameter+omics set and that key modalities (metabolomics, regulation) are missing or only relative. It can feed Claim 1 (data is the bottleneck / integration is critical), Axis B, Axis C, Claim 4/8 as support, and supplies foil/limitation lines on missing modalities and reliance on borrowed data.

---

## Load-Bearing Excerpts

> "A complete description of the state of the cell requires knowledge of its size, shape, components, intracellular reactions, and interactions with its environment, all of these as a function of time and cell growth. Adding to this list is the need for theoretical models and simulations that interpret and integrate this daunting amount of experimental data."
> — INTRODUCTION · bears on: Claim 1 (supports); Axis B (supports); Axis C (supports)
> · States that a complete cell description requires size, shape, components, reactions, and environment, all as a function of time and growth, plus models to integrate the experimental data.

> "Common challenges are establishing the reaction networks and the availability of kinetic parameters and -omics data such as metabolomics and proteomics to use as initial conditions. No one bacterium has a complete set of parameters and -omics data, so the development of a WCM relies upon synthesizing information from other well-studied organisms."
> — INTRODUCTION · bears on: Claim 1 (supports); Claim 8 (supports); Standard (supports)
> · Concedes that no single bacterium has a complete set of kinetic parameters and -omics data, forcing models to synthesize information across organisms.

> "In addition to biochemical reactions, whole-cell, 3D spatial models require cellular architecture, including spatial distributions of ribosomes and configurations of the circular chromosome. The cellular architectures (Figure 1) are reconstructed at the single-cell level directly from cryo-electron tomograms (cryo-ET) that reveal a near-random distribution of ribosomes throughout the cell with a few present in polysomes (Gilbert et al., 2021)."
> — INTRODUCTION · bears on: Axis C (supports); Claim 7 (supports)
> · States that 3D whole-cell models require cellular architecture (spatial distribution of ribosomes, chromosome configuration) reconstructed at single-cell level from cryo-ET.

> "At the moment, only relative metabolomics data on Syn3A is available, so the metabolite concentrations used to initialize the simulations of the Syn3A WCM were estimated from a scaling of the comprehensive study done on E. coli (Park et al., 2016) and a limited list from M. pneumoniae (Yus et al., 2009)."
> — INTRODUCTION · bears on: Claim 4 (supports); Claim 1 (supports)
> · Concedes that only relative metabolomics data exist for Syn3A, so absolute metabolite initial conditions had to be borrowed/scaled from E. coli and M. pneumoniae.

> "Unlike the previous WCMs, the simulations we present here are based on fully dynamical kinetic models where subsystem networks and chemical species are interconnected continuously over time on a single-cell basis."
> — INTRODUCTION · bears on: Axis B (supports)
> · Positions the model as fully dynamical, with subsystems interconnected continuously over time on a single-cell basis.

> "In our simulations, we record time-dependent particle counts of each molecule and intermediate, fluxes of all metabolic reactions, and in the spatial model, the position of each macromolecule within the cell."
> — INTRODUCTION · bears on: Axis B (supports); Axis C (supports)
> · Describes the simulation output as time-dependent counts and fluxes plus, in the spatial model, the position of each macromolecule, i.e. explicit temporal and spatial resolution.

> "Starting from the coordinates of the 503 ribosomes and cell boundary of a small cell with 400-nm diameter from cryo-ET (Figure 1A), the DNA is folded around ribosomes as a circular self-avoiding polymer on a lattice in such a way that the sequence order and gene positions are maintained (Figures 1B and 1C) (Gilbert et al., 2021). Experimental 3C maps showed no significant features of persistent supercoiled domains or loops, so the chromosome is assumed to be in a relaxed state (Gilbert et al., 2021)."
> — RESULTS: 3D spatial whole-cell simulations · bears on: Axis C (supports)
> · Details how spatial initial conditions are built from cryo-ET ribosome coordinates and 3C chromosome-conformation maps, an explicitly spatial multimodal input.

> "Comparative proteomics analyses to Mesoplasma florum (Matteau et al., 2020; Lachance et al., 2021), B. subtilis (Wang et al., 2015), and E. coli (Taniguchi et al., 2010) were used to approximate missing or questionable information regarding a few of the Syn3A enzymes."
> — INTRODUCTION · bears on: Claim 8 (supports); Claim 1 (nuances)
> · States that proteomics from multiple other organisms was used to fill in missing/questionable enzyme information for Syn3A, illustrating cross-dataset stitching to cover data gaps.

> "Integration of experimental data is critical in building a kinetic model from which emerges a genome-wide distribution of mRNA half-lives, multiple DNA replication events that can be compared to qPCR results, and the experimentally observed doubling behavior."
> — SUMMARY · bears on: Claim 1 (supports); Claim 8 (supports)
> · Asserts that integration of experimental data is critical to building the kinetic model and to producing experimentally comparable emergent quantities.

> "Due to reduction in its minimal genome, Syn3A has few remaining transcription/ translation/transport regulatory proteins and must adjust the fluxes through the cellular subsystems to maintain stable growth."
> — RESULTS: Balance of genetic information processes and metabolism · bears on: Other (nuances)
> · Notes that the minimal cell retains few regulatory proteins, a property exploited to model behavior with little explicit regulation.

> "We have not included explicitly known regulatory proteins like PhoU (phoU/0428) and the riboswitches TPP and SAM, as the kinetic parameters and time-scales of conformational changes in the riboswitches are still being investigated (Scull et al., 2021)."
> — DISCUSSION · bears on: Other (nuances)
> · Concedes that known regulatory proteins and riboswitches were omitted because their kinetic parameters and timescales are still unknown.

> "In general, average metabolite concentrations generated from the model (Figure 6) show reasonable agreement to the values reported by Park et al. (2016) in E. coli, but the cell-to-cell variation in the kinetic models over a cell cycle is broader than the predicted range. This discrepancy certainly calls for regulation in some cases such as the uptake of (deoxy)nucleosides, uptake of inorganic phosphates, and formation of some metabolites that build up to large concentrations in some cells such as prpp and fdp."
> — DISCUSSION · bears on: Claim 4 (nuances)
> · Reports that simulated metabolite averages roughly match borrowed E. coli values but cell-to-cell variation is too broad, flagging a gap from missing regulation and absent native metabolomics.

> "Time-dependent behaviors of concentrations and reaction fluxes from stochastic-deterministic simulations over a cell cycle reveal how the cell balances demands of its metabolism, genetic information processes, and growth, and offer insight into the principles of life for this minimal cell."
> — SUMMARY · bears on: Axis B (supports)
> · Summarizes the modeling output as time-dependent concentrations and fluxes over a full cell cycle linking metabolism, gene expression, and growth.

> "By emergent, we specifically mean behaviors defining the state of the cell (time-dependent concentrations, patterns, reaction rates, and correlations) that arise from simulations of the kinetic models and are not imposed."
> — DISCUSSION · bears on: Claim 1 (supports)
> · Defines emergent behavior as time-dependent cell state arising from the kinetic model rather than imposed, underscoring that dynamics come from integrated mechanistic inputs.

> "Even though homeostasis can be observed for a population, there can be significant variation among individual cells due to stochastic fluctuations in gene expression."
> — RESULTS: Time-dependent concentrations show consistent average behavior and large population variability · bears on: Claim 3 (nuances)
> · Notes large single-cell variability hidden under population homeostasis, relevant to the distinction between population averages and true single-cell trajectories.

> "While the predicted distribution of half-lives is in agreement with genome-wide studies carried out on related organisms, it awaits confirmation from ongoing transcriptomics studies."
> — DISCUSSION · bears on: Claim 1 (nuances)
> · Concedes a model prediction is validated only against related-organism data and still awaits direct transcriptomics confirmation in Syn3A.

> "Without a detailed composition of the inner and outer leaflet relative to each other for each of the modeled lipid classes ... flippase activity is not included in the present model. In addition, we do not include potential activity of phospholipase A1 or A2 which allow for acyl chain scavenging from various phospholipid species because these enzymes have not yet been genetically identified in Syn3A."
> — STAR Methods: Lipidomics / Lipid metabolism · bears on: Claim 4 (nuances)
> · Concedes lipid processes were omitted for lack of spatially resolved leaflet composition and unidentified enzymes, an example of a missing modality detail limiting the model.

> "A crucial caveat to this data is that due to the heavy dependence on lipid incorporation for Syn3A that the lipidomic makeup observed is likely substantially dependent upon the growth medium that is used. However, this is the clearest picture of Syn3A lipid makeup to date, and it is therefore used to parameterize the lipid biomass and growth model used in our simulations."
> — STAR Methods: Lipid metabolism · bears on: Claim 4 (supports); Standard (nuances)
> · States that lipidomics data, though condition-dependent, is the best available and was used directly to parameterize the model, showing a non-RNA modality as a load-bearing input.

> "low counts are likely due to the fact that both are multiple domain membrane proteins, which are known to be underreported by proteomics when only a trypsin digest is used (D. Gonzalez, personal communication)."
> — RESULTS: The kinetic model is influenced by the defined medium composition and new genome annotations · bears on: Claim 6 (nuances); Standard (nuances)
> · Notes that membrane proteins are systematically underreported by trypsin-digest proteomics, a measurement-bias caveat affecting protein-count inputs.

> "The RDME-CME-ODE simulations are currently limited by having the degradosome, RNAP, and ribosome complexes all initialized in inactive states. ... In the absence of experimental knowledge of the average active complexes in Syn3A, the initial transience emphasizes importance of diffusion and how the ensemble-averaged results of the spatial model could be used to parameterize probabilistic factors in the well-stirred CME-ODE kinetic model, which account for diffusion."
> — Limitations of the study · bears on: Axis C (nuances)
> · Concedes the spatial model is limited by lacking experimental knowledge of active-complex states in Syn3A, and that spatial diffusion effects must be folded back into the well-stirred model.

> "Our spatial model includes a total of 7,765 unique molecules and intermediates and over 7,200 reactions including binding reactions such as RNAP binding to a gene start site."
> — RESULTS: 3D spatial whole-cell simulations · bears on: Axis C (supports)
> · Quantifies the spatial model scope: 7,765 unique molecules/intermediates and over 7,200 reactions including spatial binding events.

> "Simulations of a spatially resolved cell are computationally expensive and require GPU (Figure 1I) acceleration to make them possible on a human timescale (Hallock et al., 2014). ... took 10 h and 8 h to simulate 20 min of cell time, respectively. Because of this computational expense, we simulated the first 20 min of the cell cycle for only 8 cells"
> — RESULTS: 3D spatial whole-cell simulations · bears on: Claim 10 (supports); Axis C (nuances)
> · Reports the cost/coverage trade-off: spatial simulation is so expensive (10 h per 20 min of cell time) that only 8 cells over the first 20 min could be run, vs cheaper well-stirred runs over full cycles.

> "We present results of the well-stirred model over a complete cell cycle for 174 healthy replicate cells out of a total population of 207 cells."
> — INTRODUCTION · bears on: Claim 3 (supports)
> · States the ensemble: 174 healthy cells out of 207 simulated over a full cell cycle, giving single-cell trajectory statistics rather than a single average.

> "Being computationally less expensive, the well-stirred model runs on CPUs and provides a whole-cell model that can be easily complexified to allow addition of more pathways and testing. More importantly, it allows us to quantitatively understand the ‘‘principles of life’’ for a minimal cell growing with little regulation."
> — INTRODUCTION · bears on: Claim 10 (nuances)
> · Contrasts the cheaper well-stirred (CPU) model against the expensive spatial model, framing a resolution-vs-cost trade-off in choosing simulation modalities.

---

## Figures / Key Numbers

- **Genome / model scope:** JCVI-syn3A: 493 genes on a single 543-kbp circular chromosome, 452 protein-coding genes; ~one-tenth the genome and physical size of E. coli; 87/452 (20%) genes of unclear function vs E. coli 1780/4637 (38%) and M. pneumoniae 311/688 (45%).
- **Model contents (Discussion):** 148 known metabolites, 452 proteins and mRNAs, 29 tRNAs, 503 ribosomes, DNA, over 7,000 reactions; spatial model: 7,765 unique molecules/intermediates and over 7,200 reactions.
- **Spatial initial conditions (Fig. 1):** 503 ribosomes, 400-nm-diameter cell from cryo-ET; 120 degradosome complexes, 66 SecY proteins, 831 PtsG proteins; over 77,000 proteins, 200 mRNA, 5,800 tRNA randomly distributed.
- **Spatial simulation cost:** NVIDIA Titan V and Tesla Volta V100 GPUs took 10 h and 8 h respectively to simulate 20 min of cell time; only 8 cells simulated over first 20 min.
- **Active complex fractions (spatial model):** 63 of 187 RNAP active (34%); 220 of 503 ribosomes active (~45%); consistent with E. coli ranges (RNAP 15.5-36.2%; ribosomes 20-80% by growth rate).
- **mRNA half-lives (Fig. 1, Fig. 7):** Well-stirred average half-life 3.4 min; spatial model average 1.97 min; long tail out to 15 min; compared to 2-min average in M. gallisepticum and B. subtilis genome-wide distribution; genome-wide average ~4 translations per mRNA.
- **Cell cycle timing (Fig. 3):** Replication initiation 3-36 min (avg 10, mode 6); chromosome duplication avg ~70 min (56-90); avg chromosome number 2.8 (up to 3.8) at end; volume doubles 56-72 min (avg 64); surface area doubles 88-112 min (avg 97); experimental doubling time 105 min in rich medium; protein:lipid surface ratio ~55:45.
- **ATP economy (Fig. 5):** Max ~45,000 ATP/s (30,000 via PGK, 15,000 via PYK); ~35,000 ATP/s initially; glucose uptake ~15,000/s; active transport ~5,000 ATP/s vs tRNA charging ~2,500 ATP/s; ATP synthase ~10% of costs; PFK uses 75% of total metabolic cost.
- **Proteome homeostasis (Fig. 6):** 350/452 proteins (counts >=10, excluding ribosomal) analyzed; majority end cell cycle at 1.75-2.25x initial counts; population fraction failing (pep shortage) ~16% of 207 cells.

---

## Primary Sources (citation provenance)

- **Cryo-ET cell geometry, ribosome coordinates, 3C chromosome-conformation maps used as spatial inputs**
  - Gilbert et al. 2021 (cryo-ET / chromosome reconstruction of Syn3A); deposited cryo-ET data EMPIAR-10686, EMDB EMD-23661  (None)
- **Essential GSMM, genome-wide gene essentiality, and proteomics of Syn3A (initial conditions and protein counts)**
  - Breuer M. et al. 2019, eLife 8:e36842; proteomics ProteomeXchange PXD008159  (None)
- **Prior comprehensive whole-cell models cited as predecessors**
  - Karr J.R. et al. 2012 (M. genitalium WCM); Macklin D.N. et al. 2020, Science 369 (E. coli)  (None)
- **Borrowed/scaled metabolite concentrations for initialization (no native absolute metabolomics)**
  - Park J.O. et al. 2016 (E. coli metabolome); Yus E. et al. 2009, Science 326:1263-1268 (M. pneumoniae)  (None)
- **Prior kinetic model of genetic information processes (basis for GIP module)**
  - Thornburg Z.R. et al. 2019, Front. Mol. Biosci. 6:130  (None)
- **Single-molecule (smFRET) DnaA filament kinetics used as a measured parameter**
  - Cheng H.-M. et al. 2015, Nucleic Acids Res. 43:396-405  (None)

---

## Flags / Caveats

- Metadata: DOI confirmed in text (doi:10.1016/j.cell.2021.12.025); venue Cell confirmed via self-citation/supplemental URL; volume/issue/pages 185(2):345-360 inferred from the journal record and not printed verbatim in the cleaned source.
- Dates from text: Received Aug 9, 2021; Revised Nov 1, 2021; Accepted Dec 17, 2021; Published Jan 20, 2022.
- OCR quirks preserved verbatim in excerpts and figure descriptions (e.g. 'fbaA/0131' contexts, accented author names Saenz/Sa´ enz rendered as printed, doubled-quote characters).
- Scope note: This is a mechanistic whole-cell SIMULATION paper, not a measurement-paradigm critique; captured excerpts focus on the experimental DATA INPUTS it requires (cryo-ET spatial geometry, multi-omics, time-course) and on its conceded data gaps, which bear on Claim 1/4/8 and Axes B/C; STAR Methods algorithmic detail (RDME/CME/ODE equations, qPCR primers, medium recipes) left uncaptured as off-roadmap.
- primarySources refN left null: the cleaned MD reference list is alphabetical without numeric reference indices.
- Read at source worth first-hand: Gilbert et al. 2021 (cryo-ET spatial architecture) and Breuer et al. 2019 (proteomics + GSMM) are the actual multimodal data sources behind this model's spatial and modality claims.
