# Paper Revision Plan: "Varieties as Conditioning Structure"

> **For agentic workers:** This is a LaTeX paper revision, not software. Execute tasks sequentially. Run `/check-style` after each edit. Build with `make` or `xelatex main.tex && biber main && xelatex main.tex && xelatex main.tex` to verify compilation.

**Goal:** Integrate session insights (O'Connor, coordination costs, projectibility, D&S) and address review board consensus weaknesses.

**Architecture:** Seven revision tasks, ordered by dependency. Tasks 1-3 are terminological/framing changes that propagate everywhere. Tasks 4-6 add new content. Task 7 restructures the conclusion. Each task produces a committable state.

**Source materials in context:** O'Connor 2019 (Games and Kinds), O'Connor 2021 (Measuring Conventionality), O'Connor 2022 (Why Natural Social Contracts are Not Fair), Drummond & Schleef 2016 (Identity in VS), plus all five review board reports.

---

## Task 1: Replace "appropriateness" with "listener expectation"

**Rationale:** Critical reviewer (both slides and paper) flagged that "appropriateness" is ideologically loaded (Flores & Rosa). The math doesn't need the word. The paper currently uses it as the organizing concept (section heading, abstract, conclusion).

**Files:**
- Modify: `main.tex` (throughout)

**Steps:**

- [ ] Replace the section heading "Appropriateness as the fundamental category" with "Listener expectation as the fundamental category" or similar
- [ ] Rewrite the abstract to use "listener expectation" instead of "appropriateness" throughout
- [ ] In Section 4.1, reframe: instead of "dimensioning appropriateness," say "dimensioning listener expectation -- what a listener predicts given their model of the speaker and situation"
- [ ] Replace "appropriate" / "appropriateness" throughout the body text with "expected" / "listener expectation" / "predictive match" as context requires
- [ ] Preserve the distinction in Section 6 (Normativity) where "appropriateness" is explicitly defined as the genus and distinguished from grammaticality, acceptability, and correctness. Here, add a footnote: "I avoid the term 'appropriateness' for the conditioning-structure framework because it has been argued to embed normative assumptions about whose communicative practices count as situationally correct (Flores & Rosa 2015). The model-internal concept is listener expectation: what the listener's model predicts given inferred S/A/I. The normativity section uses 'appropriateness' in a technical sense that is explicitly probabilistic and listener-relative, not normatively loaded."
- [ ] Update the conclusion accordingly
- [ ] Build and verify

**Note:** This is the highest-impact, lowest-effort change. Do it first because it propagates.

---

## Task 2: Add acknowledgment that listener expectations are ideologically mediated

**Rationale:** Critical reviewer: "listeners' priors are shaped by raciolinguistic ideologies -- the Bayesian machinery operates over ideologically contaminated data." Brett's instruction: acknowledge broadly (race, class, sex, attractiveness, BMI), not singling out raciolinguistic ideologies.

**Files:**
- Modify: `main.tex` Section 5 (Bayesian formalisation), near the operationalization discussion

**Steps:**

- [ ] After the current paragraph on operationalization (line ~254), add a new paragraph:

> "A further limitation: the listener's model is not ideologically neutral. Priors on ascription are shaped by the listener's own social position and by the ideological structures they've internalized -- structures organized around race, class, sex, age, body type, and other axes of social sorting. A listener who has learned to associate certain phonological features with a racialized category will hear those features differently from a listener who hasn't. The Bayesian machinery is real, but it operates over ideologically structured data. The framework can represent this (the prior on A is where ideology enters), but it doesn't derive it. This is a limitation worth naming: the framework diagnoses how listener expectations produce inequity, but the formation of those expectations is upstream of the model."

- [ ] Build and verify

---

## Task 3: Engage third-wave literature explicitly

**Rationale:** Philosopher, hostile, and variationist reviewers all flagged insufficient engagement with Eckert, Silverstein, Agha, Bucholtz & Hall. The paper risks looking like a relabelling. The D&S point (framework resolves a tension the three waves created) is the answer.

**Files:**
- Modify: `main.tex` Section 4 (Varieties as emergent partitions), after "Preserving working distinctions" subsection

**Steps:**

- [ ] Add a new subsection: "Relationship to three-waves variationism"
- [ ] Content should include:
  - Acknowledge that third-wave work (Eckert 2012, Silverstein 2003, Agha 2005, Bucholtz & Hall 2005) already distinguishes indexicality from demographic coding, stance from identity, enregisterment from correlation
  - The D&S point: Drummond & Schleef (2016) describe a tension across the three waves that none resolves. First and second wave treat identity as stable and imposed; third wave treats it as fluid and constructed. Both are real simultaneously. S/A/I holds both at once by making them structurally different parameters whose divergence generates predictions -- not just whose coexistence needs acknowledgment
  - State what S/A/I adds beyond the third wave: (i) the formal separability of the durable and the agentive, with their divergence generating specific distributional predictions; (ii) the game-theoretic explanation of why equilibria are inequitable (not just that they are); (iii) the explicit link between indexicality and inverse conditioning
  - "The contribution is not that variationists haven't noticed these distinctions. It's that S/A/I provides a formal unification that makes their divergence analytically productive."
- [ ] Add bib entries for Eckert 2012, Silverstein 2003, Agha 2005, Bucholtz & Hall 2005 if not already present
- [ ] Build and verify

---

## Task 4: Add exogenous/endogenous stabilizers and coordination costs

**Rationale:** This morning's central insight, absent from the paper entirely. O'Connor's game theory adds a stabilizer LVC doesn't typically model. Coordination costs explain why varieties are bundles, not independently varying features.

**Files:**
- Modify: `main.tex` Section 3 (Com-sits as coordination problems), new subsection after 3.3

**Steps:**

- [ ] Add subsection: "Exogenous and endogenous stabilizers"
- [ ] Content:
  - S/A/I are exogenous stabilizers: situation stabilizes because activities recur; ascription because others' perceptions are durable; identification because normative orientation is sticky
  - Coordination costs are the endogenous stabilizer: once a community converges on a bundle of conventions, unilateral deviation is costly (O'Connor 2019, 2021)
  - These interpenetrate: ascription locks in partly because others coordinate on it; coordination costs operate through S/A/I. The distinction is useful, not clean
  - This explains bundling: varieties are coherent packages because you're coordinating on the whole bundle. Deviate on one feature and you've signalled you might be playing a different game
  - Reference O'Connor 2021's basin-of-attraction formalization: a variety occupies a basin; switching means climbing over the boundary; deeper basin = more stable variety
  - The cultural red king effect (O'Connor 2017, cited in O'Connor 2022): minority groups encounter outgroup members more often, so they accommodate majority norms faster. Asymmetric coordination costs
  - O'Connor 2022: even arbitrary social categories produce discriminatory equilibria. The dynamics themselves generate inequity whenever social categories exist
- [ ] Note: disagree with O'Connor on primacy (this is Brett's position). Coordination costs aren't *the* fundamental mechanism with S/A/I as landscape; they interpenetrate
- [ ] Build and verify

---

## Task 5: Add "variables live at the divergence points"

**Rationale:** Novel prediction from this morning's session. The framework doesn't just condition on variables -- it predicts where variables should exist.

**Files:**
- Modify: `main.tex` Section 4 (Varieties as emergent partitions), in or after "Stability profiles" subsection

**Steps:**

- [ ] Add a paragraph (or short subsection) after stability profiles:

> "The framework also predicts where sociolinguistic variables should be found. Where S, A, and I converge -- where all three dimensions predict the same form -- the feature is invariant. It sits in the stable core of the cluster. A feature becomes variable precisely when the conditioning dimensions pull in different directions: situation predicts one form, ascription another, identification a third. The envelope of variation should map onto the divergence structure of the conditioning space. Variables aren't randomly distributed across the grammar; they cluster at the fringes where different S/A/I configurations make different predictions."

- [ ] Build and verify

---

## Task 6: Develop the Bayesian formalization

**Rationale:** All five reviewers flagged the Bayesian section as gestural. The three marginal conditionals need to become a joint model. No data fitting (it's not that kind of paper), but the generative model should be fully specified.

**Files:**
- Modify: `main.tex` Section 5 (Bayesian formalisation)

**Steps:**

- [ ] After Equations (1)-(3) and "In practice, all three matter at once," replace the current gesture at a joint model with the actual joint model:

$$Y \mid S{=}s,\, A{=}a,\, I{=}i \;\sim\; \text{Categorical}(\theta_{s,a,i})$$

- [ ] Gloss: "The distribution over variants depends on all three dimensions jointly. This is not three independent effects added together; it's a single distribution parameterized by the full S/A/I configuration."

- [ ] Add the hierarchical structure explicitly:

$$\theta_{s,a,i} \sim \text{Dirichlet}(\alpha_{a,i})$$
$$\alpha_{a,i} \sim \text{Gamma}(\mu_a, \sigma_a)$$

- [ ] Gloss: "Speaker-level parameters are drawn from ascription-level distributions (speakers with similar ascriptions share structure), which are themselves drawn from population-level priors. Situation enters at the token level; identification modulates how much situation shifts the distribution (the random slope). This is a standard Bayesian multilevel model, not a novel architecture -- the contribution is identifying S/A/I as the conditioning variables that parameterize it."

- [ ] Add: "Marginalize over A and I to recover register variation. Marginalize over S and I to recover dialect variation. Marginalize over S and A to recover discourse-community variation. The three variety types are slices of one joint distribution, not three separate models."

- [ ] Add the circularity dissolution: "A potential worry: identification shapes production, and production signals identification. But this isn't a vicious circle; it's the homeostatic feedback loop the framework predicts. As long as the model is time-indexed (the posterior at $t$ becomes the prior at $t{+}1$), reciprocal causation is a feature, not a bug."

- [ ] Build and verify

---

## Task 7: Restructure conclusion around projectibility

**Rationale:** Projectibility reviewer: "the conclusion cashes out in 'what holds the categories together' rather than 'what the categories let you do.'" The HPC slogan is "a profile, stabilised by mechanisms, projectible for a purpose." The third clause is missing.

**Files:**
- Modify: `main.tex` Section 7 (Conclusion)

**Steps:**

- [ ] Keep the existing opening paragraph (what distinguishes register from dialect from discourse community)
- [ ] After the three-item list, add a projectibility paragraph:

> "The value of this framework is not that it provides a cleaner taxonomy. It's that the taxonomy is projectible. Knowing a speaker's S/A/I configuration lets you predict their distributional behaviour; observing their behaviour lets you infer S/A/I. The framework generates specific predictions: (a) distributional predictions -- form frequencies given S/A/I; (b) acquisition predictions -- learners track S/A/I as conditioning variables and revise with experience; (c) diffusion predictions -- forms spread along identification networks before becoming ascription-durable; (d) inequity predictions -- discrimination anchors on salient ascription categories and can be disrupted by shifting conditioning toward situation and identification; (e) variation predictions -- sociolinguistic variables should cluster at the divergence points of the conditioning space, where S, A, and I make different predictions."

- [ ] Add a sentence naming the HPC connection explicitly (for the book chapter this feeds into): "In HPC terms: each variable is a category, social context is one of the homeostatic properties in its cluster, and the coordination dynamics that maintain the bundle are the homeostatic mechanisms. Varieties are projectible cluster kinds -- real without essences, maintained by mechanisms, and epistemically valuable because they support induction."

- [ ] Fix the symmetry claim (Section 6.5): change "The mechanism is symmetric; the ethics need not be" to add one sentence on structural asymmetry: "The mechanism is symmetric, but the structural position is not: prestige norms are enforced by institutions that control material outcomes (hiring, education, housing); counter-norms are typically enforced by communities that don't. The asymmetry is structural, not merely ethical."

- [ ] Build and verify

---

## Task 8: Appendix -- worked example with published data

**Rationale:** All five reviewers flagged the absence of empirical demonstration. The hostile reviewer called it the single highest-value addition. An appendix is the right home: it shows the framework has empirical content without derailing the conceptual arc. No new data collection or model fitting required.

**Files:**
- Modify: `main.tex` (add appendix before `\printbibliography`)
- Possibly modify: `references-local.bib` (add Denis 2016 if not present)

**Steps:**

- [ ] Check that Denis (2016) on MTE first-person *mans* is cited and accessible. Verify what factor groups Denis reports (style, demographic, network, etc.). [Source grounding: read the actual paper before writing the appendix.]

- [ ] Write the appendix (~2 pages). Structure:

  **A. The variable and the published analysis.**
  Brief description of *mans* vs *I* in MTE (Denis 2016). State what factor groups the original study reports and their constraint rankings.

  **B. Mapping published factor groups onto S/A/I.**
  Show the correspondence: style/context factors → S; demographic coding (neighbourhood, ethnicity) → A; network/CofP membership (if reported) → I. If the original study codes "MTE speaker" as a single demographic factor, note that this conflates A and I — and that the conflation is precisely what the framework makes visible.

  **C. Predictions S/A/I generates that the original analysis doesn't.**
  Three specific predictions:

  1. **A/I separation:** Speakers with the same ascription (same neighbourhood, same demographic profile) but different identification (differing in network centrality, self-reported orientation, or participation in MTE-identified practices) should show different *mans* rates. The original analysis cannot detect this because it treats A and I as one factor.

  2. **S × I interaction:** The magnitude of situational shifting (formal → informal) should depend on identification. Speakers who strongly identify with MTE should show less suppression of *mans* in formal contexts than speakers who orient toward Standard Canadian English norms. This is a random slope for style by identification — testable in a mixed-effects model if I is independently measured.

  3. **Divergence-point prediction:** *mans* should be variable precisely because S, A, and I make divergent predictions at this constructional niche. S says: suppress in formal contexts. A says: available to MTE-ascribed speakers. I says: use it if orienting to MTE norms. The dimensions pull in different directions, which is why it's a variable rather than an invariant feature of either variety. This prediction is falsifiable: if *mans* usage shows no sensitivity to any of S, A, or I (i.e., it's used uniformly or randomly), the framework is wrong about where variables live.

  **D. What would falsify the framework.**
  State clearly: if independently measured identification adds no predictive power over ascription and situation, the A/I distinction has no empirical content for this variable. If *mans* usage is insensitive to all three dimensions, the framework fails entirely.

- [ ] Add a sentence in the conclusion (Task 7) pointing to the appendix: "Appendix A demonstrates this with a worked example using published data on MTE first-person *mans*."

- [ ] Build and verify

**Note:** This appendix requires reading Denis (2016) before writing. Source grounding applies — do not fabricate factor weights or constraint rankings. If Denis doesn't report the right factor groups, substitute another published MTE or Toronto English study that does (Walker, Tagliamonte, etc.).

---

## Task 9 (review board amendment): Additional plan adjustments

Based on review board feedback on the plan itself:

- [ ] **Index A to the listener-speaker pair in Task 6.** The Bayesian specification should reflect that ascription is perceiver-relative: $A_{l,s}$ (listener $l$'s ascription of speaker $s$), not $A_s$ (speaker's intrinsic property). Add a sentence: "Ascription is indexed to the listener-speaker pair because different listeners may ascribe the same speaker differently. The model represents this: $A$ is a property of the perception, not the person."

- [ ] **Add projectibility to the intro/abstract (extends Task 7).** The reader needs to know from paragraph one that the payoff is predictive. Add one sentence to the abstract: "The framework is projectible: knowing a speaker's S/A/I configuration predicts their distributional behaviour, and observing their behaviour lets you infer S/A/I."

- [ ] **Trim Task 4 to one paragraph** within the existing game-theory section, not a new subsection.

- [ ] **Trim Task 2 to ~50 words.** The hostile reviewer is right that the current draft is too apologetic.

- [ ] **Sharpen Task 3** into the waves-as-successive-discovery argument, not just acknowledgment. Lead with: "The three waves can be read as successive discoveries of conditioning dimensions."

---

## Execution Order

1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9

Tasks 1-2 are terminological/framing (propagate everywhere, do first). Task 3 is positioning. Tasks 4-5 add new theoretical content. Task 6 develops existing content. Task 7 restructures the conclusion. Task 8 adds the empirical appendix. Task 9 applies review board amendments across all tasks.

## What This Plan Does NOT Do

- **No game specification.** Specifying a payoff matrix for a concrete sociolinguistic variable is important but requires choosing a variable and computing equilibria. Deferred to a follow-up paper or the HPC book chapter.
- **No ballroom case revision.** The ballroom case study works well as-is; reviewers praised it.
- **No normativity section revision.** Section 6 (normativity) was not flagged by any reviewer as problematic.
