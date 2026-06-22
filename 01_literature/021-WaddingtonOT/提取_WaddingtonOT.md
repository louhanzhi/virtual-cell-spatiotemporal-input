# Evidence Extraction: Waddington-OT — for "the virtual-cell input debate is really about admitting cells live in space and time, which the dominant dissociation-based data paradigm throws away"

> **Paper:** Schiebinger, Shu, Tabaka, Cleary, Subramanian, Solomon, et al. *Optimal-Transport Analysis of Single-Cell Gene Expression Identifies Developmental Trajectories in Reprogramming*. **Cell 176(4), 928–943 (2019)**. Field-defining method that reconstructs developmental trajectories from *destructive* scRNA-seq snapshots via optimal transport.
> **BibTeX key:** `schiebinger2019waddingtonot` (verified against `01_literature/references.bib`).
> **Citation eligibility:** formal citation (peer-reviewed, *Cell*).
> **What this paper is to our paper (one line):** the canonical worked example for the **time axis (§3)** of a *destructive, snapshot-based* measurement regime whose temporal information must be **computationally back-inferred** rather than observed — simultaneously an ally (it names the destructiveness problem out loud) and a foil (it accepts the loss and works around it, whereas we argue the input itself should carry real time + lineage).

Writing type detected: **perspective / position paper**. Below: why it matters → direct ammunition (quote + use) → indirect/framing → tension & novelty → usage cheat-sheet.

---

## 1. Why it matters to our thesis

Our thesis claims the dominant data paradigm (dissociation-based scRNA-seq) discards both space *and* time. Waddington-OT is the **most-cited demonstration that the time loss is real and structural**: its entire method exists *because* sequencing destroys the cell it measures, so you can never follow the same cell forward. It is therefore the perfect anchor for §3 (time axis) and §4 (the resolution × throughput × destructiveness trilemma):

- It states the destructiveness constraint in plain language (ammunition for our diagnosis).
- It embodies the "pseudotime/inferred-time vs. real time" divide our outline builds §3 around: WOT does **not** give you a real clock per cell — it gives you a *probability distribution* over inferred ancestors/descendants. That is exactly the "reconstructed movie from snapshots" we want to contrast against non-destructive live imaging.
- It self-acknowledges (in Discussion) that lineage barcodes and real per-cell history are *not* in the input and can at best be bolted on later — supporting our claim that lineage/time should be a first-class **input field**, not a post-hoc inference.

---

## 2. Direct ammunition (quote + how to use)

### A. Destructiveness is the root cause (the single most important quote for us)
- **Quote (Introduction):** "Because scRNA-seq destroys cells in the course of recording their profiles, one cannot follow expression of the same cell and its direct descendants across time. While various approaches can record information about cell lineage, they currently provide only very limited information about a cell's state at earlier time points."
- **How to use:** Drop verbatim (or lightly paraphrased) into §3 and §4 as the authoritative statement that destructive sequencing forecloses true temporal observation. This is our strongest external endorsement that "time is thrown away at the measurement step."
  > Note: Sample rewrite — "As Waddington-OT's authors put it, sequencing 'destroys cells in the course of recording their profiles,' so the same cell can never be followed forward — temporal continuity must be inferred, not observed (Schiebinger et al., 2019)."

### B. Snapshots → "movies" must be computationally connected
- **Quote (Introduction):** "Comprehensive studies of cell trajectories thus rely heavily on computational approaches to connect discrete 'snapshots' into continuous 'movies.'"
- **How to use:** §3 framing sentence. Use to set up the binary our outline names — *inferred/back-computed time* (WOT, stVCR) vs. *directly observed time* (live imaging, Caliban). The "snapshot → movie" phrasing is quotable and intuitive.
  > Note: This is the cleanest one-line articulation of why destructive modalities yield only pseudo-temporal, model-dependent trajectories.

### C. Time is reconstructed as a *distribution*, not a measured value
- **Quote (Results, "Reconstruction of Probabilistic Trajectories"):** "because different cells are sampled independently at different time points, we lose the joint distribution of expression between pairs of time points, called temporal coupling. Absent any constraint on cellular transitions, we cannot infer the temporal coupling, but if we assume that cells move short distances over short time periods, then we can infer the temporal coupling by using … optimal transport."
- **How to use:** §3 (and §4) — evidence that recovering time from destructive data requires a **modeling assumption** (smoothness / short-distance moves) that may not hold; the "real" ancestor of a given cell is never recorded, only a distribution over plausible ones. Supports our argument that input-level time/lineage is preferable to assumption-laden inference.
  > Note: Sample rewrite — "Even state-of-the-art trajectory inference recovers only a *distribution* over plausible ancestors and descendants, contingent on an assumption that cells move short distances in short times — the actual lineage of any individual cell is never in the data (Schiebinger et al., 2019)."

### D. Markov assumption: history is explicitly discarded
- **Quote (Results):** "The optimal-transport calculation … implicitly assumes that a cell's fate depends on its current position but not on its previous history (i.e., the stochastic process is Markov) …"
- **How to use:** §3 / §4. This is a sharp, citable concession that the method *cannot* use a cell's history because the history is not in the input. Powerful support for our claim that lineage/trajectory should be an explicit input field rather than something assumed away.
  > Note: This directly motivates our "time input should carry lineage" field-list argument — Markovianity is a workaround for missing history, not a biological truth.

### E. Authors' own roadmap: lineage barcodes *should* be folded into the input
- **Quote (Discussion, "Future Prospects"):** "various methods exist for obtaining lineage information about cells … Barcodes can be used to recognize cells that descend from a recent common ancestor cell but do not currently directly reveal the full gene-expression state of the ancestral cell. However, they might be incorporated into our optimal-transport framework to better estimate temporal couplings."
- **How to use:** §3 / §5 (outlook). Use as an *ally* quote: even the inventors of the canonical inference method say richer temporal/lineage information *in the data* would improve things. Lets us say "the field is already reaching for what we argue should be a first-class input."
  > Note: Strong for §5's "ideal spatiotemporal input spec" — frame our lineage/real-time fields as the natural endpoint of a trajectory the WOT authors themselves point toward.

### F. Benchmark fact: most trajectory methods ignore time entirely
- **Quote (Discussion):** "we comprehensively reviewed 62 other approaches … category 1 (33 tools) is not applicable … category 2 (25 tools) is applicable but does not incorporate time information, and category 3 (4 tools) leverages time information, but does not model cell growth rates over time. … Waddington-OT is the only approach that incorporates temporal information and models cell growth over time."
- **How to use:** §1 or §3 — a hard, citable number showing that even the *computational* community largely fails to use temporal information, reinforcing how systematically under-weighted the time axis is. Useful as a one-line statistic.
  > Note: Sample phrasing — "Of 62 trajectory-inference tools surveyed by Schiebinger et al. (2019), only 4 used temporal information at all — a striking measure of how routinely the time axis is dropped."

---

## 3. Indirect / framing material

- **Scale as the cost of the workaround.** WOT needed **315,000 cells across 18 days, sampled every 12 h (every 6 h at the key transition)** to make snapshot interpolation work. Useful in §4 to illustrate the *price* of destructive sampling: because you destroy what you measure, you must pay in massive, dense, redundant sampling to approximate a movie you cannot record directly.
  > Note: Cite as "dense time courses of hundreds of thousands of cells are required precisely because no single cell can be observed twice."
- **Waddington landscape framing.** The paper's opening (marbles rolling through a developmental landscape; trains on branching tracks) is a vivid, citable metaphor for the time axis. Could anchor §3's opening line, but it is decorative — use sparingly.
- **Validation by held-out interpolation.** WOT is validated by predicting an intermediate time point from its neighbors. This underscores that the temporal structure is *interpolated*, not measured — reinforcing ammunition C/D.

---

## 4. Tension & novelty vs. our thesis

WOT is a methods paper that *accepts* the destructive constraint and engineers around it brilliantly; our perspective *refuses* to accept it as the end state. The increment:

1. **We reframe its premise as a data-agenda problem, not a modeling problem.** WOT asks "given that sequencing destroys cells, how do we infer trajectories?" We ask "should the input itself carry real time and lineage so we don't have to infer them?" WOT is the strongest evidence that the inference path is assumption-laden (Markov, short-distance moves, distributions not identities) — we use its own concessions to argue *upstream* for better input.
2. **We place it on a spectrum it doesn't draw.** Our §3 binary — destructive/inferred-time (WOT, stVCR) vs. non-destructive/observed-time (Caliban live imaging, lineage tracking) — is *our* axis. WOT lives entirely on the destructive side and never contrasts itself with live imaging; we supply that contrast.
3. **We connect it to the measurement trilemma (§4).** WOT's need for 315k cells × dense sampling is, in our framing, a direct consequence of the resolution × throughput × destructiveness trade-off. WOT does not articulate that trilemma; we do, and WOT becomes its illustration.
4. **Lineage as input vs. lineage as future add-on.** WOT relegates real lineage information to "Future Prospects." Our thesis promotes lineage/real-time to a *required input field* in the ideal spec (§5). Same direction, but we make it constitutive rather than optional — this is the answer to "isn't this already said?": WOT says "we could add it later," we say "it should have been in the input all along."

> **The real target is not WOT.** WOT is an ally we stand on. The target of our critique is the default *data paradigm* (dissociation-first scRNA-seq) that makes WOT-style inference necessary in the first place. We cite WOT to prove the loss is real and structurally costly, then argue the fix belongs at the input/measurement layer.

---

## 5. Usage cheat-sheet

| Where in our paper | Snippet to deploy | Strength |
|---|---|---|
| §1 (why spatiotemporal is key input) | "only 4 of 62 trajectory tools use temporal information" (quote F) | Hard statistic; shows systematic neglect of time |
| §3 (time axis — inferred vs. real time) | "scRNA-seq destroys cells … one cannot follow … the same cell" (A); "snapshots into … movies" (B) | Core anchor — destructiveness forces inference |
| §3 (time axis — what time input should contain) | Markov / "no previous history" concession (D); distribution-not-identity (C) | Motivates lineage + trajectory as explicit input fields |
| §4 (resolution × throughput × destructiveness trilemma) | 315k cells × 18 days × 12 h sampling (§3 indirect) | Illustrates the cost of destructive sampling |
| §5 (ideal input spec & outlook) | "barcodes … might be incorporated … to better estimate temporal couplings" (E) | Ally quote: field already reaching toward lineage-as-input |

> **Overall:** cite WOT as the authoritative, formally citable proof that destructive sequencing forecloses real temporal observation (§3) and that the workaround is assumption-laden and expensive (§4); use its own "future prospects" lineage remark (§5) as a bridge to our claim that time + lineage belong in the *input*, not in a downstream model. Formal citation OK throughout. State our increment via §4 (Tension) so reviewers see we stand on WOT rather than repeat it.

---

> Note (scope): This paper is rich in reprogramming biology — MET/stromal/trophoblast/neural trajectories, Obox6/GDF9 validation, paracrine ligand–receptor analysis. All of that is **irrelevant to our thesis** (it's the biological payload, not the data-paradigm argument) and is deliberately omitted. The one borderline item is the paracrine ligand–receptor interaction scoring; if §2 (space axis / CCI) ever needs a non-spatial precedent for inferring cell–cell interaction from co-expression, WOT's interaction-score method exists — but it is computed *without* spatial coordinates, so it is at best a weak indirect reference and likely better left to Spateo.
