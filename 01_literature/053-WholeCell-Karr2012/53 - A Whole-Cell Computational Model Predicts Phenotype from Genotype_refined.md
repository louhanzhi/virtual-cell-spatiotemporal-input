# A Whole-Cell Computational Model Predicts Phenotype from Genotype — Source Index

**Authors:** Karr JR et al. (author list not printed in this supplementary document; cleaned source contains only the supplementary methods)
**Journal / Venue:** unverified; see flags, 2012
**DOI:** unverified (see Flags)
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/08 A Whole-Cell Computational Model Predicts Phenotype from Genotype (Karr 2012)_cleaned.md
**Schema:** 精练-4.0 · citationKey `08`

---

## In One Sentence
This document is the supplementary methods of the M. genitalium whole-cell model, which integrates 28 process sub-models and 16 cell-state variables, reconstructed from over 900 sources and heterogeneous experimental datasets, to simulate single-cell dynamics and predict phenotype (e.g. gene essentiality, growth rates, metabolite concentrations) from genotype.

## Orientation (non-binding)
A landmark mechanistic whole-cell model that depends on integrating many heterogeneous data types and submodels; it most directly feeds Claim 1 (mechanistic models also need high-quality input data and are bottlenecked by it), Claim 4/8 (multimodal, orthogonal data integration and the friction of combining datasets), and the Standard axis (heterogeneous, non-comparable, cross-organism datasets requiring curation/refinement to be made mutually consistent). It can serve both as support (a built example proving multimodal integration is necessary and possible) and as a foil (it concedes how sparse, heterogeneous, and largely cross-organism/homology-derived the underlying data are). Non-binding routing hint.

---

## Load-Bearing Excerpts

> "The primary challenges to building a unified whole-cell model of a single cell are threefold: (1) complexity, processes relevant to cellular behavior are diverse and span a wide range of length and time scales, (2) heterogeneity, cellular networks have heterogeneous mathematical structures and are typically investigated using heterogeneous experimental methods, and (3) sparsity, little quantitative data rigorously describing single cell physiology is available."
> — Chapter 1, Computational Methods (intro) · bears on: Claim 1 (supports); Standard (supports); Claim 8 (supports)
> · The authors name the three core obstacles to a whole-cell model: complexity, heterogeneity of data/methods, and sparsity of quantitative single-cell data.

> "Third, because the 28 cellular processes were trained using diferent experimental data obtained by diferent investigators under diferent conditions using diferent techniques and diferent model organisms, we refined the values of the sub-model parameters to make the processes mutually consistent. This was necessary for example, because amino acid production by the Metabolism process, which was trained using the observed amino acid composition of M. gallisepticum reported by Morowitz et al., conflicted with the amino acid requirements of the Translation process, which was trained using the observed Mycoplasma genetic code, the reported M. pneumoniae mRNA expression, and the N-end rule."
> — Section 1.3 Cellular Process Integration / Process Alignment & Parameter Fitting · bears on: Claim 9 (supports); Claim 8 (supports); Standard (supports)
> · Submodels trained on data from different investigators, conditions, techniques, and organisms were mutually inconsistent and had to be computationally refined; gives a concrete example of two datasets conflicting.

> "Second, we computationally identified a set of parameter values which (1) satisfy all of these constraints and (2) deviate minimally from their experimentally observed values. Initially, we attempted to rigorously formulate this problem as a non-linear constrained optimization problem, and identify the parameter values which minimize the sum of squared diferences between the adjusted and observed parameter values among all sets of parameters which satisfy the constraints. However, we were unable to find a feasible solution, much less the globally optimal solution, to this optimization problem. Instead, we focused on identifying a mutually consistent set of parameter values, and developed a heuristic procedure that uses the constraints to calculate a consistent set of parameter values from a subset of the parameters."
> — Section 1.3 / Process Alignment & Parameter Fitting · bears on: Claim 9 (supports); Standard (nuances)
> · Reconciling heterogeneous datasets into a consistent parameter set could not be solved rigorously; the authors fell back on a heuristic, conceding the difficulty of integrating non-comparable data.

> "The M. genitalium whole-cell model was based on a detailed reconstruction of M. genitalium physiology developed from over 900 primary sources, reviews, books, and databases."
> — Section 1.5 Reconstruction · bears on: Claim 1 (supports); Claim 8 (supports)
> · Quantifies the data burden: a single whole-cell mechanistic model required curation from over 900 sources.

> "To fill gaps in the reconstructed organism, such as observed reactions without reported enzyme catalysts, and to maximize the scope of the model, we also expanded and refined each gene’s annotation using primary research articles and reviews identified by systematically searching PubMed and Google Scholar for each gene and homologs of each gene."
> — Section 1.5 Reconstruction · bears on: Claim 1 (supports); Axis A (nuances)
> · Concedes there were gaps (e.g. reactions without known enzymes) that had to be filled by manual literature search and homology rather than direct measurement.

> "Table S3T-S3BK describe the how the reconstructed organism was developed, including detailed notes on how the value of each reconstructed property was derived by consensus of all available experimental observations and computational predictions."
> — Section 1.5 Reconstruction · bears on: Claim 9 (supports); Standard (nuances)
> · Each parameter was set by manual consensus across heterogeneous observations and predictions, underscoring the absence of a single comparable dataset.

> "Because M. genitalium is not well-studied, the M. genitalium reconstruction was primarily based on studie of M. genitalium homologs identified by bi-directional best BLAST. Where possible, the M. genitalium reconstruction was based on closely related organisms."
> — Section 1.5 Reconstruction · bears on: Claim 1 (challenges); Standard (challenges)
> · Admits the model of the target organism was largely built from homologs and related organisms because direct data on M. genitalium were unavailable.

> "The M. genitalium whole-cell model was validated by comparing the model’s predictions to three experimental datasets: (1) the essentiality of each M. genitalium gene reported by Glass et al., (2) the measured growth rates of 12 non-essential M. genitalium single-gene disruption strains, and (3) the cytosolic concentrations of 39 E. coli metabolites reported by Bennett et al. and curated by Sundararaj et al."
> — Section 1.6 Experimental Validation · bears on: Claim 1 (supports); Axis A (supports)
> · Validation rested on a small number of heterogeneous experimental datasets, including metabolite concentrations measured in a different organism (E. coli).

> "Figure 2E of the accompanying manuscript and Table S2E compare the predicted and measured concentrations of 39 cytosolic metabolites, illustrating that 70% of the model’s predictions are statistically consistent with the Sundararaj et al. dataset. The model doesn’t reproduce the Bennett et al. dataset, and interestingly, there is significant disagreement between the Bennett et al. and Sundararaj et al. datasets."
> — Section 1.6 Experimental Validation · bears on: Claim 9 (supports); Standard (supports)
> · Two independent metabolomics datasets significantly disagree with each other, a concrete instance of cross-study non-comparability undermining validation.

> "We mapped the inputs and outputs of each sub-model onto 16 state variables which together represent the complete configuration of the modeled cell: (1) metabolite, RNA, and protein copy numbers, (2) metabolic reaction fluxes, (3) nascent DNA, RNA, and protein polymers, (4) molecular machines, (5) cell mass, volume, and shape, (6) the external environment including the host urogenital epithelium, and (7) time."
> — Section 1.3 / Cell States · bears on: Claim 4 (supports); Axis A (supports); Axis B (supports); Axis C (supports)
> · Enumerates the multimodal cell-state representation a whole-cell model requires: metabolites, RNA, protein, fluxes, polymers, machines, geometry, environment, and time, spanning modality, spatial, and temporal axes.

> "The sub-models were modeled using diferent mathematics and trained using diferent experimental data. Each of the 28 functional processes, or cellular processes, represents a group of chemical reactions which transform chemical substrates into products using enzyme catalysts. Computationally, the inputs and outputs of each sub-model are the copy numbers of metabolites and macromolecules; the configurations of RNA, protein and DNA polymers; and the catalytic capacity and configurations of the enzymes which participate in each sub-model."
> — Chapter 3, Cellular Process Methods (intro) · bears on: Claim 4 (supports); Claim 8 (supports)
> · Each submodel consumes a different data modality (copy numbers, polymer configurations, enzyme kinetics/capacity), illustrating that orthogonal modalities are jointly required.

> "The Metabolism process was reconstructed primarily based on DNA sequence homology of M. genitalium to E. coli and a comprehensive metabolic model of E. coli. The Metabolism process was modeled using FBA and trained using the observed growth rate of M. genitalium and the observed chemical compositions of M. gallisepticum and E. coli."
> — Chapter 3 / Metabolism · bears on: Claim 1 (challenges); Axis A (nuances)
> · The metabolism submodel was built largely from cross-organism data (E. coli model and chemical compositions of E. coli and M. gallisepticum) rather than direct M. genitalium metabolomics.

> "Because transcription termination is not well-characterized, termination was modeled as a deterministic process which proceeds to completion within the 1 s simulation time step if there is least one copy of each of the characterized transcription termination factors."
> — Chapter 3 / RNA Synthesis & Degradation · bears on: Claim 1 (challenges)
> · A representative admission that, where mechanistic data are missing, the model resorts to a simplifying assumption rather than data-grounded mechanism.

> "Half-lives of all the RNA species are largely based on experimental measurements of homologous E. coli genes. The E. coli genes are mapped to the M. genitalium genes by homology."
> — Chapter 3 / RNA Decay process class · bears on: Claim 3 (challenges); Axis B (nuances)
> · RNA temporal parameters (half-lives) for the target organism were imported from E. coli by homology, not measured in M. genitalium itself.

> "We obtained mRNA half-lives from measurements in E. coli performed at $3 0 ^ { \circ } \mathrm { C }$ in M9 minimal media. Additional sets of E. coli half-life data are available, but we chose the set with the most comprehensive list of genes mapping to homologous M. genitalium genes, and the set whose average half-life was closest to the reported bulk E. coli mRNA half-life. ... This have us a half-life estimate for 274 M. genitalium genes. For the remaining genes, we assigned the average half-life, 4.425 minutes."
> — Chapter 3 / Transcription (RNA half-life determination) · bears on: Claim 3 (challenges); Claim 9 (supports)
> · Temporal dynamics data were sparse and incompatible: half-lives came from a chosen E. coli dataset (one of several conflicting ones) and missing genes were filled with a single average value.

> "The exact mechanism of replication initiation in M. genitalium is unknown. M. genitalium does not include a DnaC homolog, which in other species is an essential cue for the binding of the replication machinery to the oriC. Here, the binding of 29 DnaA-ATP molecules to the oriC is the cue for replication initiation."
> — Chapter 3 / Replication · bears on: Claim 1 (challenges)
> · An explicit 'mechanism is unknown' admission where the model substitutes an assumed cue, illustrating sparsity of mechanistic data.

> "M. genitalium cytokinesis is thus a cycle of filament binding, bending, and dissociation. ... M. genitalium has the tubulin homologue, FtsZ (MG224), but does not contain the accessory proteins required for cell division in other bacterial species. Therefore, cytokinesis in M. genitalium is not fully understood."
> — Chapter 3 / Cytokinesis · bears on: Claim 1 (challenges)
> · Another conceded knowledge gap: a core process (cell division) is not fully understood and is modeled from a proposed mechanism.

---

## Figures / Key Numbers

- **Model scope:** 28 cellular process sub-models and 16 cellular state variables, spanning six areas of cell biology.
- **Reconstruction sources:** Over 900 primary sources, reviews, books, and databases.
- **Simulation scale:** 192 wild type cells and 3,011 single-gene deletants simulated; MATLAB R2010b on a 128-core Linux cluster.
- **Gene essentiality validation:** Model reproduces observed gene essentiality with 79% accuracy.
- **Growth-rate validation:** Correctly predicts measured growth rates of 67% of 12 non-essential single-gene disruption strains.
- **Metabolite validation (Fig. 2E / Table S2E):** 70% of predicted concentrations of 39 cytosolic metabolites statistically consistent with the Sundararaj et al. dataset; model does not reproduce the Bennett et al. dataset, which itself significantly disagrees with Sundararaj et al.
- **Parameter refinement (Fig. S1A):** Computationally adjusted gene expression correlated with that observed by Weiner et al. at R^2 = 0.68.
- **Genome organization:** In silico chromosome organized into 335 transcription units containing 525 genes.
- **RNA half-life coverage:** Half-life estimates obtained for 274 M. genitalium genes by E. coli homology; remaining genes assigned the average 4.425 minutes; tRNA 45 min, rRNA 150 min, sRNA 89 min.
- **Transcriptional regulation:** Reconstructed network of five regulators regulating 54 genes through 29 regulatory interactions.

---

## Primary Sources (citation provenance)

- **Gene essentiality data used for validation**
  - Glass et al. 2006  (193)
- **E. coli cytosolic metabolite concentrations (validation dataset)**
  - Bennett et al.  (392)
- **Curated metabolite concentrations (validation dataset)**
  - Sundararaj et al.  (394)
- **M. gallisepticum cell chemical/amino acid composition**
  - Morowitz et al. 1962  (870)
- **M. pneumoniae mRNA expression / promoters**
  - Weiner et al. 2003 (expression); Weiner et al. 2000 (promoters)  (569)
- **E. coli mRNA half-lives**
  - Bernstein et al. 2002  (602)
- **Transcription unit / suboperon organization of M. pneumoniae**
  - Güell et al. 2009  (418)
- **E. coli comprehensive metabolic model (basis of Metabolism submodel)**
  - Feist et al. 2007  (558)
- **M. genitalium FBA metabolic model**
  - Suthers et al. 2009  (610)
- **E. coli cell chemical composition**
  - Neidhardt et al. 1990  (393)

---

## Flags / Caveats

- Metadata unverified: the cleaned source contains ONLY the supplementary methods (Chapters 1-4, Appendix A/B); it has no title page, abstract, author list, journal name, or DOI. Title/year taken from the filename ('Karr 2012'). venue set to 'unverified; see flags' and doi set to null.
- Known from filename only: author surname 'Karr' and year '2012'; full author list and initials not present in the cleaned text, so authors field is partial/reconstructed and labeled as such.
- DOI scan negative: grep for '10.[0-9]{4,}/' over the source returned no DOI.
- OCR quirks preserved verbatim in excerpts (e.g. 'diferent', 'studie', 'This have us', '$3 0 ^ { \circ }$', 'afinity'); not corrected.
- Scope note: the bulk of the document (Chapters 2-3 per-process modeling detail) is mechanistic/biology-implementation detail that is off-roadmap (the context file explicitly does NOT cover specific modeling methods); only data-sourcing, heterogeneity, sparsity, multimodal-integration, and validation statements were captured.
- Scope note: this paper is bacterial (M. genitalium); per context-file boundaries, specific organism is treated as example only, not as subject matter.
- Read at source: refs #193 (Glass essentiality), #392/#394 (Bennett/Sundararaj metabolomics), #569 (Weiner mRNA expression), #602 (Bernstein E. coli mRNA half-lives), and #558 (Feist E. coli metabolic model) are the worth-citing first-hand primary datasets underpinning the cross-organism / heterogeneous-data points; resolve full citations from the original paper's reference list before citing.
- Figure numbers cited as 'accompanying manuscript' (e.g. Fig. 2E, Fig. 6B, Fig. 7A) refer to the main paper, not present in this supplementary source.
