# Simultaneous quantification of mRNA and protein in single cells reveals posttranscriptional effects of genetic variation — Source Index

**Authors:** Christian Brion, Sheila M Lutz, Frank Wolfgang Albert
**Journal / Venue:** eLife, 2020; 9:e60645 (volume/article-number inferred — see Flags). Received 02 July 2020; Accepted 14 November 2020; Published 16 November 2020.
**DOI:** doi:10.7554/eLife.60645 (inferred from decision-letter DOI `.sa1` / author-response DOI `.sa2`; see Flags)
**Read on:** 2026-06-18
**Source file:** /Users/augustsirius/Desktop/已清洗_260617/33 - Simultaneous quantification of mRNA and protein in single cells reveals post-transcriptional effects_cleaned.md

---

## In One Sentence
The authors built a CRISPR-based dual fluorescent reporter that quantifies mRNA production (mCherry, gRNA-driven CRISPR activation) and protein abundance (GFP) of the *same* gene at the *same* time in single, live yeast cells, then used FACS bulk-segregant mapping across ten genes to find 86 trans-acting loci — and found that fewer than 20% had concordant effects on mRNA and protein, with most loci (52 protein-specific) affecting protein but not mRNA, demonstrating pervasive post-transcriptional genetic effects.

## Orientation (non-binding)
Yeast genetic-variation / QTL study, not a virtual-cell or spatial paper; off the perspective's primary topic but a high-value, first-hand quantitative demonstration that **mRNA abundance does not determine protein abundance** — the single strongest kind of ammunition for the roadmap's Claim 4 (modalities are orthogonal and mutually irreplaceable; RNA cannot stand in for protein). It is unusually clean evidence because the authors deliberately measured both layers in the *same cells, same environment* to remove confounders — which also makes it a touchpoint for Claim 9 / the standard axis (cross-study / cross-lab comparison inflates discrepancies; matched measurement is required). Secondary touchpoints: throughput/cost trade-offs of combined RNA-seq + mass spec (Claims 9–10), live-cell vs lysis-based measurement (Claim 3 / destructiveness), and a temporal-resolution limitation of fluorescent reporters (Axis B). It can serve as support OR be cited as a paper that itself concedes how hard and confounder-prone multi-layer measurement is.

---

## Load-Bearing Excerpts

> "Less than 20% of these loci had concordant effects on mRNA and protein of the same gene. Most loci influenced protein but not mRNA of a given gene."
> — Abstract · bears on: Claim 4 (modality orthogonality), Axis A (modality) · headline finding that mRNA and protein levels of the same gene are largely under separate genetic control.

> "These results demonstrate complex, posttranscriptional genetic effects on gene expression."
> — Abstract · bears on: Claim 4 · post-transcriptional layer carries information not present in mRNA.

> "Post-transcriptional mechanisms can shape protein levels independently of mRNA abundance (Buccitelli and Selbach, 2020; Csa´rdi et al., 2015; McCarthy, 1998), raising important questions about how DNA variation shapes protein levels compared to mRNA abundance."
> — Introduction · bears on: Claim 4 · protein levels can be set independently of mRNA.

> "It is unclear whether most eQTLs, which by definition affect mRNA, also affect the protein abundance of the same genes, such that they also result in a protein-QTL (pQTL) (Damerval et al., 1994). It is also unclear to what extent there are protein-specific pQTLs that influence protein abundance without affecting the mRNA of the same gene."
> — Introduction · bears on: Claim 4 · frames the open question of mRNA-protein decoupling.

> "Trans-acting QTLs were reported to show even greater differences between mRNA and protein. In mouse crosses and some yeast crosses, (Mirauta et al., 2020) trans-eQTLs and trans-pQTLs mapped for the same genes showed very little overlap, suggesting that while many trans-eQTLs are buffered at the protein level, there are also many trans-pQTLs that affect proteins via mechanisms that do not affect mRNA"
> — Introduction · bears on: Claim 4 · prior literature already shows mRNA and protein genetic determinants diverge strongly in trans.

> "In yeast and humans, genetic effects on translation as measured by ribosome profiling were similar to those on mRNA, suggesting that translation cannot account for protein-specific pQTLs (Albert et al., 2014a; Battle et al., 2015; Cenik et al., 2015). Instead, proteinspecific effects may arise from protein degradation, especially for proteins that are part of protein complexes (Chick et al., 2016; Großbach et al., 2019; He et al., 2020)."
> — Introduction · bears on: Claim 4, Axis A (PTM / complexes / interactome) · mechanism for protein-specific information: degradation, not translation.

> "Together, this literature suggests that genetic variants can independently affect the different layers of gene expression regulation."
> — Introduction · bears on: Claim 4, Claim 8 (orthogonal information across layers) · the layers (mRNA, protein) are separately regulable.

> "First, small sample sizes of dozens to a few hundred individuals were used in most studies to date. Most eQTLs and pQTLs change the expression of the gene they affect by 10% or less (Albert et al., 2018). … With limited sample size, real loci can be missed. … Thus, low statistical power can inflate discrepancies between eQTLs and pQTLs."
> — Introduction · bears on: Claim 9 (comparability / benchmarking), Claim 10 (trade-offs) · caveat — apparent mRNA-protein discrepancy can be a power artifact, so claims about decoupling need high-power matched designs.

> "Second, experimental differences between studies may also inflate discrepancies between eQTLs and pQTLs. In nearly all cases, eQTLs and pQTLs were compared between experiments conducted in different laboratories, sometimes using different experimental designs, and, in the case of some human studies, comparing eQTLs and pQTLs mapped in different tissues. These comparisons are likely to be confounded by environmental influences, which can drastically alter the effects of regulatory variants."
> — Introduction · bears on: Claim 9 (data islands / cross-paper incomparability / no standard) · cross-study, cross-lab, cross-tissue comparison is confounded — a direct statement of the comparability problem.

> "To date, no study of regulatory variation has measured mRNA and protein with high statistical power and in the same samples. This challenge is not easy to overcome, because combined application of RNA-sequencing (RNA-seq) and mass spectrometry in thousands of matched samples remains prohibitively expensive."
> — Introduction · bears on: Claim 9, Claim 10 (resolution × throughput × cost trilemma), Axis A (modality) · matched multi-modal measurement at scale is cost-prohibitive — why most data stays single-modality.

> "Here, we addressed this challenge by developing a system for quantifying mRNA and protein from the same gene simultaneously, in the same, live, single yeast cells using two fluorescent reporters. We reasoned that such an approach would equalize all environmental confounders and most of the technical biases that could obscure the relationship between eQTLs and pQTLs."
> — Introduction · bears on: Claim 9 (standard / matched measurement), Axis A · same-sample paired measurement removes the confounders that separate-study comparison introduces.

> "Although our approach was explicitly designed to maximize the chance of detecting similar genetic effects on mRNA and protein, the majority of the identified loci affected only mRNA or protein for a given gene, or had discordant effects on mRNA and protein. These results demonstrate considerable differences in the genetic basis of variation in mRNA vs protein abundance."
> — Introduction · bears on: Claim 4 · even a design biased *toward* concordance still finds mRNA and protein largely decoupled.

> "To study the relationship between mRNA and protein among single cells, we examined the cell-to-cell correlation between mCherry and GFP fluorescence … After correcting for cell size … mCherry and GFP were positively correlated for all tested genes … The strength of the correlation varied from gene to gene. Lower correlations between mCherry and GFP were observed for the genes with many differences between published eQTLs and pQTLs compared to those with more concordant eQTLs and pQTLs. Thus, different genes are influenced by mRNA-specific or protein-specific variation to different degrees."
> — Results (single-cell correlation) · bears on: Claim 4 · mRNA-protein coupling is gene-dependent and incomplete at the single-cell level.

> "Across the ten genes, we detected 78 protein-QTLs and 44 mRNA-QTLs … By design, all detected loci were trans-acting"
> — Results (Simultaneous mapping) · bears on: Claim 4 · core count; more loci shape protein than mRNA.

> "Of these 86 loci, 16 affected mRNA and protein of a given gene in the same direction. … A majority of the loci corresponded to protein-QTLs that did not overlap an mRNA-QTL. These 52 protein-specific QTLs may arise from variants that affect translation or protein degradation, without an effect on mRNA production."
> — Results (Differences between mRNA-QTLs and protein-QTLs) · bears on: Claim 4 · 52/86 loci are protein-specific — protein abundance carries genetic information absent from mRNA.

> "There were eleven mRNA-QTLs that did not overlap with a protein-QTL and seven loci where mRNA-QTLs and protein-QTLs overlapped but had discordant effects."
> — Results · bears on: Claim 4 · mRNA-specific (11) and discordant (7) loci — both layers carry non-redundant signal.

> "While more than 73% of loci were specific for mRNA or protein, this difference might be inflated by loci that are truly concordant, but at which either the mRNA-QTL or the protein-QTL narrowly failed to meet the significance threshold."
> — Results · bears on: Claim 4, Claim 9 · authors' own caveat on the specificity fraction (threshold effects).

> "When considering all loci, we observed a significant, positive correlation between mRNA and protein effect sizes (r = 0.41, p-value=8.4 - 10⁻⁵, Figure 5B). This overall correlation was almost exclusively driven by the concordant QTL pairs, whose effect sizes showed a strong correlation (r = 0.88 p-value=9×10⁻⁶). In sharp contrast, neither protein-specific QTLs (r = 0.2, p-value=0.23) nor mRNA-specific QTLs (r =  0.05, p-value=0.9) had correlated effects across the two data types, as expected if these loci specifically affected only mRNA or only protein."
> — Results · bears on: Claim 4 · quantitative: the mRNA-protein effect-size correlation collapses to ~0 once concordant pairs are removed.

> "Overall, only 64% of QTLs affected mRNA and protein in the same direction. While this was more than the 50% expected by chance (binomial test p-value=0.006), it left 36% of loci with discordant effects. … only 55% of mRNA-specific QTLs had an effect in the same direction in the protein data, which was not significantly different from chance (p-value=0.5)."
> — Results · bears on: Claim 4 · even the *direction* of effect agrees little better than chance for layer-specific loci.

> "Nevertheless, of the 86 trans-acting loci that contributed to variation in the expression of ten genes, 84% did not have concordant effects on mRNA production and protein abundance. This result demonstrates the importance of variants that act on specific layers of gene expression."
> — Discussion · bears on: Claim 4 · headline restatement — 84% non-concordant.

> "While half of the mRNA-QTLs we detected had concordant effects on protein (16 out of 34), most protein-QTLs had no effects on mRNA (52 out of 75) … That 70% of our protein-QTLs had protein-specific effects suggests that the causal variants underlying many of these loci affect posttranscriptional processes, i.e. mRNA stability, translation, or protein degradation."
> — Discussion · bears on: Claim 4, Axis A (PTM / protein state) · 70% of protein-QTLs are protein-specific → post-transcriptional control dominates protein variation.

> "A well-studied example of this phenomenon is the regulation of expression of genes that encode members of a protein complex, in which excess protein molecules that cannot be incorporated in the complex are rapidly degraded (Taggart et al., 2020). Among the genes we investigated, RPS10A encodes a part of the ribosome small subunit complex. RPS10A showed the highest number of mRNA-specific QTLs, possibly because Rps10a is subject to buffering mechanisms."
> — Discussion · bears on: Claim 4, Axis A (interactome / complexes) · protein-complex stoichiometry buffering decouples protein from mRNA — interactome-level information RNA cannot capture.

> "YAK1^Q578* changed protein abundance for many genes more strongly than mRNA abundance, but also affected mRNA but not protein for many other genes. Thus, the consequences of this mutation span mechanisms that affect mRNA as well as protein-specific processes."
> — Discussion (YAK1) · bears on: Claim 4 · a single causal variant produces both mRNA-specific and protein-specific genome-wide effects.

> "Among 5755 quantified mRNA transcripts, 262 were up-regulated and 310 down-regulated in the presence of YAK1^Q578* … The variant reduced the abundance of 82 of 2590 quantified proteins, and increased another 82 proteins … we classified genes as affected only at the mRNA level (58 genes up, and 118 genes down-regulated), only at the protein level (60 genes up, and 50 genes down-regulated), or at both mRNA and protein (15 genes up, and 27 genes down-regulated)."
> — Results (YAK1 genome-wide, RNA-seq + mass spec) · bears on: Claim 4, Claim 8 (multi-omics needed to see both layers) · genome-wide matched RNA-seq + mass spec: large mRNA-only and protein-only gene sets, small overlap.

> "Consistent with a protein-specific trans-effect on GPD1, deletion of YAK1 in a strain in which GPD1 was tagged with GFP-gRNA caused a reduction of green fluorescence but had no detectable effect on mCherry fluorescence … qPCR indicated no difference in the level of GPD1-GFP mRNA"
> — Results (YAK1) · bears on: Claim 4 · orthogonal validation that a variant moves protein without moving mRNA of the same gene.

> "Standard methods for mRNA quantification require lysis of cell cultures or tissues, constraining sample throughput and statistical power for mapping regulatory variation. Single-cell RNA-seq … and in situ fluorescent hybridization techniques … are improving rapidly … However, these approaches still have throughput that is orders of magnitude below that available using FACS. Further, they involve cell lysis or fixation, precluding bulk segregant approaches that rely on growing cells after sorting. By contrast, our reporter allows quantification of mRNA production of a given gene within millions of single, live cells by flow cytometry."
> — Discussion · bears on: Claim 3 (destructive measurement), Claim 10 (throughput trade-off) · standard mRNA/scRNA-seq measurement is destructive (lysis/fixation) and orders of magnitude lower throughput than a live-cell readout.

> "By contrast, standard methods usually used in eQTL mapping quantify mRNA at steady state, which may explain some of the differences we observed between our mRNA-QTLs and known eQTLs identified by RNA-seq."
> — Discussion · bears on: Claim 4, Axis B (temporal) · steady-state mRNA (RNA-seq) vs mRNA production are different quantities — measurement design changes what is captured.

> "The mCherry used here has a maturation time of about 40 min (Merzlyak et al., 2007), which limits the temporal resolution at which we can observe dynamic expression changes. Fluorescent proteins with faster maturation times and shorter half-lives, could enable precise investigation of rapid temporal change in mRNA production."
> — Discussion (limitations) · bears on: Axis B (temporal) · a conceded temporal-resolution limit — fluorescent-reporter dynamics blur fast temporal change.

> "Yet, fewer than 20% of the detected trans-acting loci we detected had concordant effects on mRNA and protein levels, providing strong support for the existence of discordant trans effects on mRNA vs proteins. … The fact that the majority of trans-QTLs identified here were protein-specific suggests that protein abundance is under more complex genetic control than mRNA abundance."
> — Discussion (closing) · bears on: Claim 4, Axis A (proteome) · final claim — protein abundance is more complexly controlled than mRNA, so RNA underdetermines protein.

---

## Claim Touchpoints (router — the downstream aggregation key)
| Roadmap Claim / Axis | Relevant Excerpt (lead words / section) | Direction |
|---|---|---|
| Claim 4 — modalities orthogonal / mutually irreplaceable (RNA ≠ protein) | "Less than 20% of these loci had concordant effects…" / Abstract; "84% did not have concordant effects…" / Discussion; "r = 0.88 … protein-specific QTLs (r = 0.2) nor mRNA-specific (r = 0.05)…" / Results | supports |
| Axis A — modality (proteome, PTM, interactome/complexes) | "52 protein-specific QTLs may arise from variants that affect translation or protein degradation…" / Results; "protein complex … rapidly degraded (Taggart et al., 2020)" / Discussion | supports |
| Claim 5 — protein/non-RNA modality indispensable for function/phenotype | "YAK1 and GPD1 are involved in osmotic stress resistance … strains with YAK1^Q578* and yak1D had a higher growth rate than wild-type" / Results | supports (indirect) |
| Claim 8 — multi-modalities give orthogonal info, need integration | "genetic variants can independently affect the different layers…" / Introduction; matched RNA-seq + mass spec classification of YAK1 targets / Results | supports |
| Claim 9 — data islands / cross-paper incomparable / no standard | "eQTLs and pQTLs were compared between experiments conducted in different laboratories … confounded by environmental influences" / Introduction; "equalize all environmental confounders…" / Introduction | supports |
| Claim 10 — resolution × throughput × destructiveness trilemma | "combined application of RNA-seq and mass spectrometry in thousands of matched samples remains prohibitively expensive" / Introduction; "orders of magnitude below … FACS … involve cell lysis or fixation" / Discussion | supports |
| Claim 3 — destructive measurement / no paired temporal observation | "Standard methods … require lysis … involve cell lysis or fixation … By contrast, our reporter … single, live cells" / Discussion | nuances |
| Axis B — temporal resolution | "mCherry … maturation time of about 40 min … limits the temporal resolution" / Discussion; "standard methods … quantify mRNA at steady state" / Discussion | nuances |

---

## Figures / Tables / Numbers
| Item | What it contains (factual) |
|---|---|
| Figure 1 | Dual reporter design: GFP-gRNA tag at 3' end of gene; self-cleaving ribozymes (Hh, HDV) release gRNA; dCas9-VP64 drives genomic mCherry. qPCR validation of gRNA/mRNA and ribozyme cleavage. |
| Figure 2 | Z3EV estradiol titration: mCherry is a monotonic, quantitative readout of mRNA; linear up to ~half of ACT1 mRNA abundance; 95% of S. cerevisiae genes fall below this threshold (quantifiable). |
| Figure 3 | BY×RM cross, FACS sorting of 3–5% high/low GFP and mCherry subpopulations (10,000 cells each); single-cell GFP–mCherry correlation. |
| Figure 4 | QTL maps; 78 protein-QTLs and 44 mRNA-QTLs across ten genes; cross-study effect correlations: protein-QTL/pQTL r = 0.73 (p<10⁻¹⁵), mRNA-QTL r = 0.44 (p=5×10⁻⁶); MKT1 (chr XIV ~450 kb) and HAP1 (chr XII ~650 kb) pleiotropic loci. LOD≥4.5 threshold, FDR ≈ 7%. |
| Figure 5 | Classification of 86 loci: 16 concordant, 52 protein-specific, 11 mRNA-specific, 7 discordant. Effect-size correlations (5B): all loci r = 0.41 (p=8.4×10⁻⁵); concordant pairs r = 0.88; protein-specific r = 0.2 (p=0.23); mRNA-specific r = 0.05 (p=0.9). 64% same direction overall. |
| Figure 6 | Fine-mapping of chr X ~155 kb locus to a single G→A variant at 148,659 bp → YAK1 Q578* premature stop; arose recently in the BY4741 ancestor of the GFP/TAP collections; reduces Gpd1-GFP protein with no mCherry/mRNA effect. |
| Figure 7 | Genome-wide YAK1^Q578* vs wildtype: 5755 mRNAs (262 up / 310 down), 2590 proteins (82 down / 82 up); mRNA-only, protein-only, and both categories; cytoplasmic-translation enrichment (q<10⁻¹⁰) among down-regulated mRNAs. |
| Counts (text) | 47,754 variants differ between BY and RM; 18,871 reliable polymorphic markers used; 125 sorted populations from 25 experiments; 5755 genes (RNA-seq) and 2590 proteins (mass spec) quantified; 2577 genes shared. |

---

## Primary Sources Behind Key Quotes
- Post-transcriptional mechanisms shape protein independently of mRNA → Buccitelli C, Selbach M, 2020, *Nature Reviews Genetics* 21:630–644 (doi:10.1038/s41576-020-0258-4); Csárdi G et al., 2015, *PLOS Genetics* 11:e1005206.
- mRNA levels, amplified post-transcriptionally, largely determine steady-state protein levels in yeast → Csárdi G et al., 2015, *PLOS Genetics* 11:e1005206 (doi:10.1371/journal.pgen.1005206).
- Trans-eQTLs / trans-pQTLs show little overlap; mouse + human iPSC proteome variation → Chick JM et al., 2016, *Nature* 534:500–505 (doi:10.1038/nature18270); Mirauta BA et al., 2020, *eLife* 9:e57390 (doi:10.7554/eLife.57390).
- Genetic effects on translation (ribosome profiling) similar to mRNA → Albert FW et al., 2014a, *PLOS Genetics* 10:e1004692; Battle A et al., 2015, *Science* 347:664–667 (doi:10.1126/science.1260793); Cenik C et al., 2015, *Genome Research* 25:1610–1621.
- Prior single-cell protein-QTL mapping (same FACS bulk-segregant strategy) → Albert FW et al., 2014b, *Nature* 506:494–497 (doi:10.1038/nature12904).
- RNA-seq eQTLs in 1012 segregants (trans-regulatory variation) → Albert FW et al., 2018, *eLife* 7:e35471 (doi:10.7554/eLife.35471).
- mRNA buffering / protein-complex degradation example → Taggart et al., 2020 (cited in Discussion; full entry not located on the references page read — see Flags).
- Median yeast mRNA half-life 3.6 min → Chan LY et al., 2018, *eLife* 7:e32536 (doi:10.7554/eLife.32536).

---

## Flags
- [ ] Metadata inferred (not printed verbatim as the article's own DOI): the main-article DOI **10.7554/eLife.60645** and article number **e60645** are derived from the printed decision-letter DOI `https://doi.org/10.7554/eLife.60645.sa1` and author-response DOI `…60645.sa2` (lines 275, 277). Volume **9** is inferred from eLife's 2020 numbering (corroborated by a 2020 eLife reference printed as "eLife 9:e57390"). Reliable but not a verbatim header field.
- [ ] OCR artifacts in source: several statistics/symbols are garbled in the cleaned MD (e.g. "p-value=8.4 - 10⁻⁵", "r =  0.05", italic-broken author citations like "et $a \mathbf{l.}$", the YAK1 variant repeatedly mis-rendered as "$\yen 4K 1…$"). Quotes above normalize only these OCR formatting glitches; wording and numbers are kept as printed. Verify exact p-values/effect sizes against the published PDF before citing.
- [ ] Read at source (for first-hand citation rather than via this paper): Buccitelli & Selbach 2020 (*Nat Rev Genet* — principles of post-transcriptional control); Csárdi et al. 2015 (*PLOS Genet* — mRNA vs protein determinants); Battle et al. 2015 (*Science* — regulatory variation RNA→protein); Chick et al. 2016 (*Nature* — proteome-wide consequences of genetic variation); Mirauta et al. 2020 (*eLife* — human iPSC proteome variation).
- [ ] Reference not resolved: "Taggart et al., 2020" (protein-complex buffering, Discussion) does not appear on the portion of the reference list captured (lines 303–345); full citation not confirmed from the source text.
- [ ] Scope note: this is a yeast trans-eQTL/pQTL genetics paper. Its on-roadmap value is the modality-orthogonality evidence (Claim 4) and the matched-measurement / comparability argument (Claim 9); the extensive strain-construction, FACS, qPCR, and mass-spec protocol sections are off-roadmap and were not captured.
