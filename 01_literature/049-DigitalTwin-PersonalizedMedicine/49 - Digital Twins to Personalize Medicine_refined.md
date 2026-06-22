# Digital twins to personalize medicine — Source Index

**Authors:** Bergthor Björnsson, Carl Borrebaeck, Nils Elander, Thomas Gasslander, Danuta R. Gawel, Mika Gustafsson, Rebecka Jörnsten, Eun Jung Lee, Xinxiu Li, Sandra Lilja, David Martínez-Enguita, Andreas Matussek, Per Sandström, Samuel Schäfer, Margaretha Stenmarker, X. F. Sun, Oleg Sysoev, Huan Zhang, Mikael Benson, on behalf of the Swedish Digital Twin Consortium
**Journal / Venue:** unverified; see flags, 2019
**DOI:** unverified (see Flags)
**Read on:** 2026-06-18
**Source file:** /Users/jialindele/Desktop/v2补充论文 md CLEANED/04 Digital Twins to Personalize Medicine (Bjornsson 2019)_cleaned.md
**Schema:** 精练-4.0 · citationKey `04`

---

## In One Sentence
A Comment proposing Digital Twins for personalized medicine: high-resolution network models of all molecular, phenotypic, and environmental factors of an individual patient, computationally treated with thousands of drugs to select the optimal one, integrating multi-omics, imaging, EMR, and multi-cell-type data across tissues and time.

## Orientation (non-binding)
Sits as a clinically framed parallel to our virtual-cell thesis: it argues that personalized models require integrating vast multi-type data (molecular, phenotypic, environmental, multi-tissue, temporal), which feeds our multimodal-integration claim (Claim 8) and temporal/spatial axes (Axis B/C, Claim 7). It can serve as support for 'integration of heterogeneous data is the unresolved challenge' but is also a partial foil: it leans heavily on scRNA-seq + PPI networks (RNA-centric, dissociated) and explicitly concedes the data-integration bottleneck, so its admissions are deployable both ways.

---

## Load-Bearing Excerpts

> "Digital and genomic medicine may bridge this gap by monitoring, processing, and integrating vast amounts of data from wearable digital devices, omics, imaging, and electronic medical records [2]. However, the integration and clinical exploitation of such complex data are unresolved challenges."
> — Background · bears on: Claim 8 (supports); Standard (supports); Claim 1 (supports)
> · States that integrating heterogeneous multimodal data (omics, imaging, devices, EMR) is the unresolved challenge for data-driven personalized medicine.

> "diagnostics often relies on a small number of biomarkers of limited sensitivity or specificity."
> — Background · bears on: Claim 4 (supports)
> · Argues that a small number of biomarkers is insufficient to capture disease complexity, motivating richer multi-variable data.

> "constructing unlimited copies of network models of all molecular, phenotypic, and environmental factors relevant to disease mechanisms in individual patients (i.e., digital twins); (ii) computationally treating those digital twins with thousands of drugs in order to identify the best performing drug; and (iii) treating the patient with this drug"
> — Application of the digital twin concept to personalize medicine · bears on: Claim 8 (supports)
> · Defines the digital twin as a model integrating all molecular, phenotypic, and environmental factors of a patient, used for in silico drug screening.

> "If we start with the molecular changes, these are dispersed across an unknown number of cell types in the body. A recent study indicated that 50% of 45 analyzed cell types were involved in each of more than 100 diseases [4]."
> — Application of the digital twin concept to personalize medicine · bears on: Claim 7 (supports); Axis C (supports)
> · Quantifies that disease mechanisms are dispersed across many cell types and tissues (50% of 45 cell types in each of >100 diseases), motivating multi-cell-type, multi-tissue resolution.

> "many of the cell types are located in tissues that are difficult to obtain from patients, such as the liver or lungs. However, it is possible to perform multi-omics analyses of individual cells from even small quantities of any fluid or tissue that can be obtained from the body."
> — Application of the digital twin concept to personalize medicine · bears on: Claim 10 (supports)
> · Concedes a sampling/accessibility constraint: causal cell types reside in tissues hard to sample, an in-vivo data-acquisition trade-off.

> "single-cell RNA-sequencing (scRNA-seq) has been used to profile the mRNA in thousands of cells in many diseases. This has already resulted in the identification of novel mechanisms that can potentially be exploited for personalized medicine [5, 6]."
> — Application of the digital twin concept to personalize medicine · bears on: Claim 4 (challenges)
> · Centers scRNA-seq (mRNA only) as the workhorse data modality for building digital twins, an RNA-centric stance our thesis critiques.

> "the complexity of those mechanisms makes drug prioritization a formidable challenge. For example, scRNA-seq analysis of inflammatory and malignant diseases implicated hundreds of drugs, many of which targeted mechanisms that did not overlap [4]. Thus, targeting one mechanism may not be effective. How can we integrate and analyze all the data derived from scRNAseq to prioritize mechanisms for drug treatment?"
> — Application of the digital twin concept to personalize medicine · bears on: Claim 1 (supports)
> · Concedes that scRNA-seq alone yields non-overlapping, hard-to-prioritize mechanisms, framing integration/analysis of the data as the open bottleneck.

> "A digital twin should ideally integrate all of the types of variable that are relevant to pathogenesis. If the variables are different types of molecules, these can be mapped on the PPI network in order to form multilayer modules [8]. Consider, for example, one module formed by mRNAs and another formed by genes harboring disease-associated variants. If the mRNAs and genes map to the same proteins, the two modules can be linked. The same principle can be applied to integrate many other types of molecules, such as mRNAs or proteins."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Claim 8 (supports)
> · Proposes PPI-network multilayer modules as the mechanism for integrating multiple molecular types (mRNA, variants, proteins) into one model.

> "diagnostic and therapeutic decisions generally need to consider multiple types of data other than molecules, such as symptoms or environmental factors, which means that the digital twin concept cannot be restricted to molecular profiles."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Claim 8 (supports); Claim 4 (nuances)
> · Argues the model cannot be restricted to molecular profiles and must integrate phenotypic and environmental data types.

> "Network tools can also be used to link interactions between cell types in different tissues. For example, cells in an arthritic joint may interact with cells in adjacent lymph nodes through different mediators [4]. Thus, multicellular network models from different tissues may be linked into a meta-network of interacting models, thereby generating comprehensive digital twins."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Claim 7 (supports); Axis C (supports)
> · Argues cell-cell interactions across tissues and microenvironments must be modeled as a spatial meta-network of interacting cell types.

> "This is important because causal mechanisms may reside in tissues other than those that cause symptoms. For example, in rheumatoid arthritis, the lungs have been proposed to have such a role and might be more suitable for therapeutic targeting than joints."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Axis C (supports)
> · Stresses that causal mechanisms reside in spatially distinct tissues from where symptoms appear, underscoring the need for spatial/tissue-location resolution.

> "The same principles can be applied to link tissues and cells over time [9]. This is important because many diseases evolve over many years before symptoms and diagnosis occur, by which time treatment may be unsuccessful because of irreversible tissue damage. Therefore, early diagnosis and treatment are important."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Axis B (supports)
> · Argues cells/tissues must be linked over time because disease evolves over years, requiring temporal/longitudinal data and trajectories.

> "With increasing availability of multi-omics, phenotypic, and environmental data, network tools may allow the construction of disease models of unprecedented resolution."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Claim 8 (supports)
> · Ties higher model resolution directly to growing availability of integrated multi-omics, phenotypic, and environmental data.

> "other methods, such as machine learning and artificial intelligence, can be used complementarily to construct and analyze digital twins. Examples include modeling the development of the networks over time or predicting the optimal treatments from the network structures."
> — Expanding digital twins by integrating variables of multiple types, locations, and time points · bears on: Axis B (nuances)
> · Notes ML/AI can model network development over time as a complement to mechanistic network tools.

---

## Figures / Key Numbers

- **FDA report [1]:** Medication is deemed ineffective for 38-75% of patients with common diseases.
- **Cell-type/disease statistic [4]:** 50% of 45 analyzed cell types were involved in each of more than 100 diseases.
- **DigiTwin consortium:** Academic, clinical and industrial partners from 32 countries.
- **Fig. 1:** The digital twin concept: (a) patient with local sign of disease; (b) unlimited digital-twin copies built from network models of thousands of disease-relevant variables; (c) each twin computationally treated with thousands of drugs; (d) best-performing drug selected for the patient.

---

## Primary Sources (citation provenance)

- **50% of 45 cell types involved in each of >100 diseases; scRNA-seq implicating hundreds of non-overlapping drug mechanisms; cross-tissue cell interactions**
  - Gawel DR, et al. A validated single-cell-based strategy to identify diagnostic and therapeutic targets in complex diseases. Genome Med. 2019;11:47  (4)
- **PPI networks and multilayer modules as templates for mapping disease-associated genes / network medicine**
  - Barabási AL, Gulbahce N, Loscalzo J. Network medicine: a network-based approach to human disease. Nat Rev Genet. 2011;1:56-68  (8)
- **Linking tissues and cells over time; gene regulatory network of T cell-associated diseases**
  - Gustafsson M, et al. A validated gene regulatory network and GWAS identifies early regulators of T cell-associated diseases. Sci Transl Med. 2015;7:313ra178  (9)
- **Integrating wearable, omics, imaging, and EMR data for digital medicine**
  - Topol EJ. A decade of digital medicine innovation. Sci Transl Med. 2019;11 (doi:10.1126/scitranslmed.aaw7610)  (2)
- **ML/AI computational modelling techniques (Bayesian networks, deep learning, etc.)**
  - Eraslan G, Avsec Z, Gagneur J, Theis FJ. Deep learning: new computational modelling techniques for genomics. Nat Rev Genet. 2019;20:389-403  (10)

---

## Flags / Caveats

- Metadata unverified: the paper's own DOI and venue are not stated in the cleaned body. Likely a Comment in Genome Medicine 2019 (inferred from companion ref #4 Genome Med 2019;11:47, the 'this Comment' self-description, and 'Published online: 31 December 2019'); not asserted in venue/doi pending confirmation.
- Dates from text: Received 28 November 2019; Accepted 28 November 2019; Published online 31 December 2019.
- Genre: this is a short Comment / opinion piece, not primary data; all quantitative figures are cited from other works (refs #1, #4), not generated here. Resolve via primarySources for first-hand citation.
- Scope note: drug-prioritization / in silico treatment-selection content (the digital-twin clinical workflow) is largely off-roadmap for our data-standard thesis and was captured only where it doubles as an integration/multimodality/temporal/spatial line.
- Read at source: ref #4 (Gawel 2019, Genome Med) is the primary source behind the most citable numbers (50% of 45 cell types; non-overlapping drug mechanisms) and is worth first-hand reading.
