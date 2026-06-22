# Evidence Extraction: AI Virtual Cell in Preclinical Research (review) — for "the virtual-cell input debate is really about admitting cells live in space and time, which the dominant dissociation-based data paradigm throws away"

> **Paper:** [Authors TBD — verify]. *AI-driven virtual cell models in preclinical research: technical pathways, validation mechanisms, and clinical translation potential*. **npj Digital Medicine (2025)** (received Aug 2025, published online 11 Dec 2025). A broad applied review of how virtual-cell models are built, validated, and translated for drug discovery.
> **BibTeX key:** `aivcpreclinical2025` (entry exists in `references.bib` but **author/title/DOI are `TODO` — must be filled in and verified before citing**).
> **Citation eligibility:** formal citation (peer-reviewed review, npj Digital Medicine). Use as a *recent secondary source* — for primary claims, prefer the primary papers it cites (e.g., Bunne 2024, the spatial/temporal method papers).
> **What this paper is to our paper (one line):** mostly a **foil / representative of the paradigm we critique** — it treats the loss of spatial and temporal information as a *technical bottleneck to be patched by AI fusion*, exactly the framing our thesis pushes against; but it concedes several facts (spatial loss, ST resolution/coverage limits, destructiveness of single-cell assays) that we can quote *as the field's own admissions*.

Writing type detected: **perspective / position paper**. Below: why it matters → direct ammunition → indirect/framing → tension & novelty → usage cheat-sheet.

---

## 1. Why it matters to our thesis

This review is useful in two opposite ways:

1. **As a hostile witness.** It openly states, in its own words, that scRNA-seq "loses spatial context," that ST is limited in resolution/throughput/coverage, and that single-cell assays are *destructive* (no repeated measurement of the same cell). These are precisely the three facts our §2 (space), §3 (time), and §4 (trilemma) rest on — and here they come from a mainstream applied review, not from us. Quoting them lets us say "even the field's own surveys admit the loss."
2. **As the diagnosis target.** The review's *response* to these admissions is the paradigm we argue against: it frames the losses as engineering gaps to be closed by AI cross-modal fusion (SpatialScope, scVI, GraphST, GLUE, moscot…), i.e., "let the model recover what the data threw away." Our thesis says this is backwards: space and time should be carried by the *input*, not reconstructed by ever-larger models from static dissociated snapshots. This review is the clean, citable embodiment of the "patch it with modeling" stance we diagnose in §1.

It also supplies a couple of concrete, quotable facts (the ~20,000-gene imaging-ST ceiling; distribution-level evaluation forced by destructiveness) useful in §2/§4.

---

## 2. Direct ammunition (quote + how to use)

### A. The field admits scRNA-seq drops space and ST is resolution/coverage-limited
- **Quote (Technical Pathways → Multimodal data integration):** "scRNA-seq resolves gene expression at single-cell resolution but loses spatial context; ST preserves spatial structure yet faces limits in resolution, throughput, and gene coverage."
- **How to use:** §2 (space axis) and §4 (trilemma) — a compact, citable statement of the core trade-off from a mainstream review. Especially valuable because it states the resolution × throughput × coverage tension in one sentence — almost our §4 trilemma, minus "destructiveness."
  > Note: Sample rewrite — "Recent surveys concede the bind plainly: dissociated scRNA-seq 'loses spatial context,' while spatial transcriptomics 'faces limits in resolution, throughput, and gene coverage' (AIVC-Preclinical 2025)." Then we add the missing third horn (destructiveness) to complete our trilemma.

### B. The destructiveness of single-cell assays is named — and used only to justify modeling workarounds
- **Quote (Validation → Computational Evaluation):** "Driven by the destructive nature of single-cell assays—which precludes repeated measurements on the same cell—evaluation should pivot to the population-distribution level by comparing the statistical distributions of perturbed simulated cell populations with those observed experimentally."
- **How to use:** §3 (time axis) and §4. This is an explicit admission that the *same cell cannot be measured twice* — our core argument for why dissociation erases time/history. Note how the review's only response is to retreat to population-distribution comparison (Wasserstein/KL/MMD). We use it to show the cost of the destructive regime: you lose the individual cell trajectory and can only argue at the distribution level.
  > Note: Pairs perfectly with the Waddington-OT quote ("scRNA-seq destroys cells … one cannot follow the same cell"). Two independent sources (a 2019 Cell method paper and a 2025 review) name the same destructiveness — strong for §4. See [[提取_WaddingtonOT]] ammunition A.

### C. The "let AI recover what the data lost" stance — explicit, citable
- **Quote (Technical Pathways → Multimodal data integration):** "To bridge these gaps, AI-based cross-modal fusion methods have been proposed. … SpatialScope uses deep generative modeling to project high-dimensional scRNA-seq data into ST coordinates, enhancing resolution and imputing missing genes."
- **How to use:** §1 (frame the dominant stance we critique) and §3/§4. This is the cleanest statement of the paradigm our thesis opposes: spatial coordinates are *imputed/projected* by a model rather than measured at input. Use it as the representative "patch the gap with modeling" position, then state our counter-claim.
  > Note: Sample phrasing — "The prevailing response is to 'bridge these gaps' computationally — projecting dissociated cells back into spatial coordinates and imputing missing genes (AIVC-Preclinical 2025). We argue the gap should not exist in the input to begin with." This is a key *tension* anchor — see §4.

### D. Imaging-ST gene-coverage ceiling (~20,000 genes) — concrete number
- **Quote (Technical Pathways):** "High-throughput imaging–driven advances in spatial transcriptomics now enable the simultaneous detection of ~20,000 genes, producing near-whole-transcriptome spatial maps and progressively mitigating the historical gene-coverage bottleneck of imaging-based ST."
- **How to use:** §4 (trilemma) — a concrete, current data point on where imaging-based ST stands on the coverage axis. Use carefully: it's an *optimistic* framing ("mitigating the bottleneck"); we should cite the number but note the trade-off it omits (high gene count at single-cell spatial resolution still trades against throughput/cost). Good for showing the frontier without overclaiming.
  > Note: Verify the ~20,000-gene figure against the primary refs it cites (seqFISH / MERFISH papers, refs 22–23) before using as a hard claim — review-level numbers can be rounded or aspirational.

### E. GNNs exist *because* dissociation drops cell–cell relationships
- **Quote (Technical Pathways → Graph neural networks):** "Cells influence each other through signaling pathways, cell–cell communication networks, and spatial proximity. Biologically faithful virtual cells must model such topology and information flow. … Treating each cell as a node, GNNs iteratively aggregate neighborhood information to capture contextual dependencies."
- **How to use:** §2 (space axis — niche/neighborhood/CCI fields). Useful as support that "biologically faithful virtual cells must model topology and spatial proximity" — i.e., the field agrees neighborhood structure matters. Then our increment: GNNs reconstruct an *inferred* graph from expression similarity when spatial coordinates are absent; we argue the real adjacency graph belongs in the input (real coordinates, real neighbors), not a similarity-graph proxy.
  > Note: Sharp contrast point — co-expression graph ≠ spatial adjacency graph. The review blurs these; our §2 should distinguish them.

### F. Lineage tracing named as external "ground truth" to calibrate models
- **Quote (Application → Boundary setting and complementarity):** "when combined with single-cell lineage tracing technology, they can provide developmental pathways, which are difficult for models to simulate, serving as ground truth to calibrate model parameters."
- **How to use:** §3 (time axis — lineage as a field) and §5 (outlook). The review treats real lineage as an *external calibration* source the model can't simulate. We flip this: if lineage is the ground truth models can't fabricate, that is exactly the argument for putting it *in the input*. Strong ally-by-concession.
  > Note: Echoes Waddington-OT's "future prospects" remark about folding lineage barcodes into the model. Two sources independently treat lineage as a missing input the field reaches for. See [[提取_WaddingtonOT]] ammunition E.

---

## 3. Indirect / framing material

- **The "validation-driven → prediction-driven simulation loop" framing.** The review's thesis is a closed-loop computational↔experimental↔translational pipeline. This is the *applications/translation* lens — orthogonal to our input-centric argument, so we don't engage it, but it usefully positions virtual cells as drug-discovery infrastructure (one sentence of context for §1 if needed).
- **Distribution-level metrics (Wasserstein, KL, MMD).** Named as the response to destructiveness (ties to ammunition B). Indirect support that the field has *given up* on per-cell temporal fidelity and retreated to distribution comparison — a consequence of the data paradigm we critique.
- **2025 Virtual Cell Challenge + Bunne 2024 (ref #1).** The review's framing rests on Bunne et al. 2024 as the field-defining vision. Confirms Bunne is the right anchor for our §1; this review is a downstream applied elaboration of that vision. (Cite Bunne directly for the vision, this review only for "the applied field has consolidated around it.")

---

## 4. Tension & novelty vs. our thesis

This review is the single clearest *foil* in the literature folder, which makes it valuable: it lets us name the stance we oppose with a concrete, recent, citable source rather than a strawman.

1. **Gap-as-engineering vs. gap-as-input-design.** The review's entire spatial/temporal section is organized around "bridge these gaps" with AI fusion (ammunition C). Our thesis: the gap is not a modeling deficiency to be patched but a *structural property of the input data* — you cannot reliably impute an address and a history the measurement physically destroyed. This is our central antagonism and the review states the opposing view crisply.
2. **It lists data modalities; it never theorizes space and time as orthogonal input axes.** Table 1 enumerates scRNA-seq/ST/multi-omics/proteomics as a shopping list of "modalities" — exactly the "more scales, more modalities" framing our outline's opening rejects. We supply the missing organizing principle: space and time as two orthogonal input axes, anchored on *data requirements*, not model capabilities.
3. **It names destructiveness but not the trilemma.** Ammunition B admits destructiveness; ammunition A admits the resolution/throughput/coverage limits — but the review never couples them into a single hard constraint. Our §4 trilemma (resolution × throughput × destructiveness, three-way unobtainable) is the synthesis it stops short of.
4. **Lineage/space treated as external add-ons, not input fields.** Lineage tracing is "ground truth to calibrate" (F); spatial coordinates are "imputed/projected" (C); neighborhood is reconstructed by GNNs (E). In every case the real spatiotemporal information is *outside* the input and recovered/calibrated after the fact. Our increment is to promote all of these to *required input fields* (coordinates, niche, CCI, lineage, real time) in the ideal-input spec (§5).

> **The target is the paradigm this review represents, not the review itself.** We cite it to (a) source the field's own admissions of spatial/temporal loss (ammunition A, B) and (b) exhibit the "patch with modeling" stance (ammunition C) as the position our thesis displaces. Because author/title/DOI are still `TODO` in the .bib, **resolve the citation metadata before relying on it**, and where possible cite the primary papers it points to (Bunne 2024; the ST method papers) for load-bearing claims.

---

## 5. Usage cheat-sheet

| Where in our paper | Snippet to deploy | Strength |
|---|---|---|
| §1 (frame the stance we critique) | "To bridge these gaps, AI-based cross-modal fusion methods have been proposed … project … scRNA-seq data into ST coordinates" (C) | Clean citable statement of the "impute it with a model" paradigm |
| §2 (space axis) | "scRNA-seq … loses spatial context; ST … faces limits in resolution, throughput, and gene coverage" (A); GNN "topology and information flow" (E) | Field's own admission of spatial loss; motivates niche/CCI input fields |
| §3 (time axis) | "destructive nature of single-cell assays — which precludes repeated measurements on the same cell" (B); lineage as "ground truth" (F) | Two-source corroboration of destructiveness; lineage-as-missing-input |
| §4 (trilemma) | A + B together; ~20,000-gene imaging-ST ceiling (D) | Supplies two horns + a concrete coverage number; we add the synthesis |
| §5 (ideal input spec / outlook) | lineage "difficult for models to simulate, serving as ground truth" (F) | Field admits lineage can't be faked — argue it belongs in input |

> **Overall:** use this review as a *recent, mainstream foil* — quote its admissions of spatial loss, ST limits, and destructiveness (§2–§4) to source the problem from inside the field, then quote its "bridge the gaps with AI fusion" stance (§1) as the paradigm our thesis displaces. State our increment via §4 (Tension): the field patches; we re-specify the input. **Caveat: fill in and verify the `aivcpreclinical2025` BibTeX entry (author/title/DOI all `TODO`) before formal citation; prefer primary sources for load-bearing claims.**

---

> Note (scope): Large portions of this review are irrelevant to our thesis and deliberately omitted — the deep-generative/PINN method taxonomy, the platform/toolbox catalog (VCell, COPASI, PhysiCell…), the entire validation-mechanism and closed-loop architecture, and the clinical-translation block (regulatory trends, data privacy, IP/liability, fairness/XAI). These concern *how virtual cells are built, validated, and deployed for drug discovery*, not *what spatiotemporal information the input should carry*. The one borderline-but-omitted item is moscot (optimal-transport multi-omics → "spatiotemporal developmental trajectories"); it's mentioned only in passing here, and if we want OT-for-spacetime we should extract its primary paper rather than this review's one-liner. See [[提取_WaddingtonOT]] for the OT-time-inference angle done properly.
