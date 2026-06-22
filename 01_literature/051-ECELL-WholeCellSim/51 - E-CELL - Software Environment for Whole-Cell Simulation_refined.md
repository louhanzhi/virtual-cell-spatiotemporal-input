# E-CELL: software environment for whole-cell simulation — Source Index

**Authors:** unverified; see flags
**Journal / Venue:** unverified; see flags, 1999
**DOI:** unverified (see Flags)
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/06 E-CELL - Software Environment for Whole-Cell Simulation (Tomita 1999)_cleaned.md
**Schema:** 精练-4.0 · citationKey `06`

---

## In One Sentence
The paper presents E-CELL, an object-oriented, rule-based simulation environment that numerically integrates the differential equations of user-defined reaction rules to model an integrative whole cell, and uses it to build a hypothetical minimal cell of 127 genes (mostly from Mycoplasma genitalium) covering transcription, translation, energy production and phospholipid synthesis.

## Orientation (non-binding)
An early mechanistic whole-cell model. It is a useful foil-and-support for Claim 1: it shows that even a non-data-driven, equation-based virtual cell is fundamentally bottlenecked by the lack of high-quality quantitative input data (kinetic parameters are largely unknown and estimated). It also bears on the multimodal axis (it explicitly integrates proteins, complexes, protein-DNA/RNA species and metabolites, not RNA alone), the spatial axis (substances are tracked per spatial compartment/location), the temporal axis (it produces true single-cell time-course trajectories in silico), and the standard/integration axis (knowledge integrated from EcoCyc and KEGG). Routing hint, non-binding.

---

## Load-Bearing Excerpts

> "Previous work in biochemical and genetic simulation has isolated well-characterized pathways for detailed analysis, but methods for building integrative models of the cell that incorporate gene regulation, metabolism and signaling have not been established."
> — Abstract · bears on: Claim 4 (supports); Axis A (supports)
> · States that integrative cell models must span multiple molecular processes (gene regulation, metabolism, signaling), not a single pathway/modality.

> "The E-CELL system allows a user to define functions of proteins, protein–protein interactions, protein–DNA interactions, regulation of gene expression and other features of cellular metabolism, as a set of reaction rules."
> — Abstract · bears on: Claim 4 (supports)
> · A cell model is built from proteins, protein-protein and protein-DNA interactions, gene regulation and metabolism together.

> "Most of them have utilized qualitative models to deal with the general lack of quantitative data in molecular biology."
> — Previous work in simulations of cellular processes · bears on: Claim 1 (supports)
> · Concedes a general lack of quantitative data in molecular biology, which forced prior models to remain qualitative.

> "Previous studies in biochemical and genetic simulations have usually limited their models to focus on only one of the several levels of the time-scale hierarchy in cellular processes. Linking the gaps between the various levels of this hierarchy is an extremely challenging problem that has yet to be adequately addressed."
> — Previous work in simulations of cellular processes · bears on: Claim 8 (supports); Axis B (nuances)
> · Identifies the integration challenge of linking multiple time-scale levels of cellular processes within one model.

> "The substance list defines all objects which make up the cell and the culture medium. The rule list defines all of the reactions which can take place within the cell, and the system list defines spatial and/or functional structure of the cell and its environment."
> — Implementation of the E-CELL system · bears on: Axis C (supports)
> · The model explicitly encodes spatial and/or functional structure of the cell and its environment as a first-class component.

> "Furthermore, E-CELL allows the assignment of any numerical integration algorithm for each compartment of the cell model, facilitating the optimization of the simulation for the user’s purpose (e.g. simulation accuracy or speed). Different time intervals (∆t) can also be defined for each spatial or functional compartment and they can be redefined through the control panel at runtime by the user."
> — Implementation of the E-CELL system · bears on: Axis C (supports); Axis B (nuances)
> · Model is partitioned into spatial/functional compartments, each with its own integration scheme and time step.

> "Besides quantitative information for each substance, information concerning the location of a substance is often important. We have defined the same molecular species at two different locations as two different objects."
> — Reaction rules · bears on: Axis C (supports)
> · Subcellular location of a molecular species is treated as essential information; the same molecule at different locations is a distinct object.

> "The same molecule in different states (e.g. phosphorylation) is defined as separate molecular species, and each spatial compartment of the model retains a list of all of the substance objects it may contain."
> — Modeling the cell — Substances · bears on: Claim 4 (supports); Axis C (supports)
> · Protein modification states (e.g. phosphorylation) are modeled as distinct species, held per spatial compartment.

> "Multi-protein complexes, protein–DNA complexes, protein–RNA complexes and other multi-molecule complexes are also defined as Substances, although they are not listed in the table."
> — Modeling the cell — Substances · bears on: Claim 4 (supports)
> · Molecular complexes (protein-protein, protein-DNA, protein-RNA) are explicit model entities beyond single molecules.

> "Our current model does not utilize actual nucleotide or amino acid sequence information. Although the length of each gene, mRNA and protein is represented, we have made the assumption that each contains equal proportions of nucleotides and amino acids, respectively."
> — Transcription and translation · bears on: Claim 1 (supports)
> · Author-conceded abstraction: real sequence composition data is omitted and approximated, a simplification driven by data/scope limits.

> "Although some kinetic parameter values can be derived from information available in existing databases, many are unknown. We have assigned values for these parameters by estimations based on available information."
> — Reaction kinetics · bears on: Claim 1 (supports)
> · Key conceded limitation: many kinetic parameters are unknown and had to be estimated rather than measured.

> "Barkai and Leibler (1997) have recently argued that cellular processes are ‘robust’ in many of their properties, in the sense that considerable variation in kinetic parameters often does not affect the behavior of the system as a whole. Many of our simulation results are consistent with their argument; increasing or decreasing a particular parameter by one order of magnitude seldom changes the qualitative behavior of our model cell."
> — Reaction kinetics · bears on: Claim 1 (challenges)
> · Counter-line: argues qualitative model behavior is robust to order-of-magnitude parameter variation, downplaying the need for precise quantitative input.

> "The E-CELL interfaces provide a means of conducting ‘experiments in silico’. For example, we can ‘starve’ the cell by draining glucose from the culture medium. The cell would eventually ‘die’, running out of ATP."
> — Virtual experiments · bears on: Axis B (supports)
> · The model yields a continuous in silico time-course of one cell's response to a perturbation, observing the same cell over time.

> "Messenger RNA levels are usually close to steady state due to continuing transcription and degradation. When the cell runs out of ATP after starvation, transcription can no longer continue and mRNAs are rapidly lost by degradation."
> — Virtual experiments · bears on: Axis B (supports)
> · Demonstrates a temporal trajectory of mRNA levels in a single simulated cell across a perturbation, not a distribution snapshot.

> "In order to obtain efficiently the necessary information to implement the pathways in our cell model, we have been utilizing knowledgebases such as EcoCyc (Karp et al., 1996) and KEGG (Kanehisa, 1996). Both of these knowledgebases provide links between information on genes, enzymes and metabolic pathways which proved essential in our effort to construct a model cell."
> — Using biological knowledgebases for model construction · bears on: Standard (supports)
> · Model construction depended on integrating cross-linked knowledgebases (EcoCyc, KEGG) spanning genes, enzymes and pathways.

> "Although EcoCyc itself does not include kinetic information, its rich references to the literature enabled us to obtain much of the further information we required to build the model."
> — Using biological knowledgebases for model construction · bears on: Claim 1 (supports); Standard (supports)
> · Concedes existing structured databases lacked kinetic data, requiring manual literature mining to fill the input gap.

> "We would like to integrate E-CELL’s knowledge representation scheme with the schemes of knowledgebases such as EcoCyc and KEGG to facilitate and, where applicable, automate information retrieval, which has proven to be a largely time-consuming part of the modeling process."
> — Concluding remarks · bears on: Standard (supports)
> · Calls for interoperable knowledge-representation standards across databases to enable automated integration of model inputs.

> "The main difficulty in this approach is that identification of gene function solely on the basis of sequence is uncertain."
> — Application to genome engineering — Metabolic requirements · bears on: Claim 4 (supports)
> · Concedes sequence/genome data alone is insufficient to assign function, motivating other modalities of evidence.

> "Because of the small number of genes (470 proteins, 37 RNAs), M.genitalium is a prime candidate for exhaustive functional (proteome) analysis."
> — Application to genome engineering · bears on: Claim 4 (supports)
> · Points to exhaustive proteome-level functional analysis as the data needed to inform the model, beyond the genome sequence.

> "This is not surprising since our model lacks several important features present in all real living cells. The model cell does not proliferate; we are currently modeling cell growth, DNA replication, chromosome segregation and cell division."
> — Concluding remarks · bears on: Claim 1 (supports)
> · Author-conceded scope limitation: the model omits major cellular features (growth, replication, division) present in real cells.

> "Furthermore, the present cell model relies on unrealistically favorable environmental conditions. All of the amino acids and nucleotides must exist, and pH and osmolarity must be kept at physiologically stable levels at all times. The model also lacks cell structure proteins, which would be indispensable in any natural environment."
> — Concluding remarks · bears on: Claim 7 (nuances); Claim 1 (supports)
> · Concedes the model assumes an unrealistic environment and omits microenvironmental and structural constraints of real cells.

---

## Figures / Key Numbers

- **Minimal model gene count:** Hypothetical cell genome consists of 127 genes including 20 tRNA genes and two rRNA genes; 120 of 127 identified in M. genitalium, 7 added from other sources; 105 protein-coding, 22 RNA-coding genes.
- **M. genitalium genome:** Smallest known chromosome; complete 580 kb genome sequence determined at TIGR in 1995 (Fraser et al., 1995); 470 proteins and 37 RNAs.
- **Table 1:** Genes per pathway: Glycolysis 9; Lactate fermentation 1; Phospholipid biosynthesis 8 (4 M.gen + 4 other); Phosphotransferase system 2; Glycerol uptake 1; RNA polymerase 8; Amino acid metabolism 2; Ribosomal L subunit 30; Ribosomal S subunit 19; rRNA 2; tRNA 20; tRNA ligase 20; Initiation factor 4; Elongation factor 1; Total 127.
- **Numerical integration:** Default ∆t = 1 ms; first-order Euler (error O(∆t^2)) for discrete stochastic reactions (e.g. DNA-protein binding); fourth-order Runge-Kutta (O(∆t^5)) for continuous deterministic reactions.
- **Simulation speed:** Whole-cell model runs at ~1/20 of real time on Pentium-II 200 MHz laptop, ~4x faster on DEC alpha 21264A 533 MHz (1 ms step, monolithic integration); a single pathway (glycolysis) runs ~30x faster.
- **Robustness observation:** Increasing or decreasing a particular kinetic parameter by one order of magnitude seldom changes the qualitative behavior of the model cell.
- **Figure 5:** Trace of ATP quantity in starving cell; glucose drained at 20 s; ATP temporarily increases then falls sharply; y-axis = number of ATP molecules (x1000) in cytoplasm, x-axis = elapsed time in seconds.
- **Figure 6:** Trace of mRNA levels; cell starved at 1000 s; mRNA near steady state before starvation, decreases rapidly after ATP loss stops transcription.

---

## Primary Sources (citation provenance)

- **Complete 580 kb M. genitalium genome sequence (smallest known chromosome) used as the gene set basis**
  - Fraser,C.M. et al. (1995) The minimal gene complement of Mycoplasma genitalium. Science, 270, 397–403  (Fraser et al., 1995)
- **Minimal gene set derived by genome comparison, contrasted with the 127-gene model**
  - Mushegian,A.R. and Koonin,E.V. (1996) A minimal gene set for cellular life derived by comparison of complete bacterial genomes. Proc. Natl Acad. Sci. USA, 93, 10268–10273  (Mushegian and Koonin, 1996)
- **Robustness of cellular processes to kinetic parameter variation**
  - Barkai,N. and Leibler,S. (1997) Robustness in simple biochemical networks. Nature, 387, 913–917  (Barkai and Leibler, 1997)
- **EcoCyc knowledgebase used for model construction**
  - Karp,P.D., Riley,M., Paley,S.M. and Pelligrini-Toole,A. (1996) EcoCyc: encyclopedia of E.coli genes and metabolism. Nucleic Acids Res., 24, 32–40  (Karp et al., 1996)
- **KEGG knowledgebase used for model construction**
  - Kanehisa,M. (1996) Toward pathway engineering: a new database of genetic and molecular pathways. Sci. Technol. Jpn, 59, 34–38  (Kanehisa, 1996)
- **Need for stepwise/detailed representation of protein signaling complex formation**
  - Bray,D. (1998) SIGNALING COMPLEXES: Biophysical constraints on intracellular communication. Annu. Rev. Biophys. Biomol. Struct., 27, 59–75  (Bray et al., 1997 (cited in text; reference list shows Bray 1998))

---

## Flags / Caveats

- Metadata unverified: the cleaned MD contains no DOI, no venue line, and no received/accepted/published dates. authors, venue, and doi are not asserted. Externally this is widely known as Tomita et al., Bioinformatics, 1999, 15(1):72-84, doi:10.1093/bioinformatics/15.1.72, but none of this is confirmable from the source text and is therefore not stated in the JSON.
- Authors not listed in cleaned text body; contact 'mt@sfc.keio.ac.jp' (likely M. Tomita) is the only author clue in-text. authors set to 'unverified; see flags' rather than reconstructed.
- Year '1999' inferred from the filename only, not from the source body; treat as approximate.
- Source inconsistency: text cites 'Bray et al., 1997' for stepwise signaling-complex representation, but the reference list contains 'Bray,D. (1998)' (Annu. Rev. Biophys. Biomol. Struct.) and 'Bray,D., Bourret,R.B. and Simon,M.I. (1993)' (Mol. Biol. Cell); the 1997 citation does not match a listed reference.
- OCR quirks preserved verbatim in excerpts and tables (e.g. '6-phosphofructasokinase', 'Musheginan' in text vs 'Mushegian' in references, 'glycose uptake', 'transltion initiation factor', spaced equation tokens).
- Scope note: this is a mechanistic ODE/rule-based whole-cell simulator, not a measurement or sequencing method. Its relevance to our thesis is that it demonstrates a non-data-driven virtual cell is still gated by the quality/availability of quantitative input data (kinetic parameters, function assignment), and that an integrative cell model inherently requires multimodal (protein, complex, metabolite, DNA, RNA), spatially-compartmentalized, time-resolved data.
- Read at source: Barkai and Leibler 1997 (Nature 387:913) worth first-hand for the parameter-robustness counter-argument relevant to Claim 1.
