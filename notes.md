# Varieties as Conditioning Structure

**Status:** Exploratory notes (informal capture)
**Perspective:** HPC-Bayesian
**Created:** 2026-01-20
**Feeds into:** HPC book (likely Part III or IV)

---

## Core Insight

The only thing that distinguishes "register" from "dialect" from "discourse community" is: *what latent/observed variable you condition on when you assign probabilities to competing form–meaning pairings, and how stable you take that variable to be across situations and speakers*.

**Compact summary:**
- **Discourse community** answers "whose data are we conditioning on?"
- **Register** answers "in what activity context are we conditioning on that data?"
- **Dialect** answers "which durable, socially transmitted bundle of distributions is providing the baseline across contexts?"

---

## Informal Definitions

### Discourse Community

A discourse community is the group whose usage you are implicitly conditioning on when you learn what counts as normal. It is not just people who talk about the same topics; it is people who share (and police, softly or explicitly) the same expectations about how certain meanings get packaged.

In Bayesian terms, a discourse community is basically a "mixture component" in the input: a cluster where certain constructions have stable rates, and where departures from those rates are heard as marked, funny, wrong, or identity-signalling.

If Simpsons fans start saying *Whose did I eat sandwich?* as an in-group marker, that's a new discourse community forming around a new distribution.

### Register

A register is the situational slice of language use: how the same person (and the same community) talks/writes in a particular activity type, medium, and stance (edited prose vs spontaneous conversation, classroom explanation vs texting, etc.).

In Bayesian terms, register is a systematic shift in construction choice probabilities driven by context, not by a different underlying speaker group. Registers are where you expect big swings in rates for things like fused-head vs pied-piping, disfluencies, parentheticals, and so on, without needing to posit a different "English".

### Dialect

A dialect is the more durable, socially anchored variety you carry around across situations: the bundle of phonological, lexical, and grammatical norms tied to region/ethnicity/class/network history.

In probabilistic terms, dialect corresponds to a broader reparameterisation (lots of constructions at once) that stays mostly stable across registers, even though each dialect still has its own register range. Dialect differences are not just "style choices"; they are community-stabilised distributions that persist when the context changes.

---

## Formal Definitions

### Discourse Community (Formal)

A discourse community is an inferred population-level source of linguistic evidence whose members exhibit coherent, mutually recognisable distributional regularities over form–meaning pairings.

In a Bayesian learning model, it corresponds to a **latent component in a mixture over input sources**: learners track constructional rates (and their uncertainty) conditional on that component rather than pooling all observed tokens into a single homogeneous grammar.

**Normativity** arises as an emergent property of this conditioning: a pattern is experienced as unacceptable insofar as it has:
1. near-zero attestation relative to a large opportunity set in the relevant component, and
2. strong competition from entrenched alternatives within the same component (e.g., fused-head and pied-piped options).

**Innovation** is compatible with this definition: a novel pattern can become learnable precisely when it is reinterpreted as evidence for a distinct component (i.e., as a community marker), rather than as noise within the baseline component.

### Register (Formal)

A register is a **context-conditioned subdistribution over constructions**: a systematic reweighting of alternatives induced by communicative situation (genre/activity, medium, audience design, level of editing, interactional constraints).

Registers are therefore not primarily defined by stable speaker identity but by **recurrent task ecology**.

Formally, register can be modelled as conditioning variables that shift the expected rates of competing constructions within a discourse community (or within a dialect), without requiring a change in the underlying community component.

On this view, register effects are differences in **selection probabilities among already-available packaging strategies** (e.g., the relative preference for fused-head vs pied-piping, the tolerance for disfluency, the incidence of parenthetical interruption), rather than categorical changes in what the system can generate.

### Dialect (Formal)

A dialect is a relatively stable, socially indexed variety characterised by **correlated distributional differences across multiple linguistic domains** (phonology, morphosyntax, lexicon, pragmatics), typically linked to durable social networks and histories of transmission.

In probabilistic terms, a dialect corresponds to a **higher-level shift in the parameter landscape**: many constructional rates (and associated expectations) differ in a coordinated way, and these differences persist across registers, even though each dialect supports its own register range.

Dialect is thus distinct from register: register is primarily situational conditioning *within* a variety, whereas dialect is primarily population conditioning *across* varieties.

---

## Bayesian Formalisation

### Setup

Fix a **constructional niche**: an opportunity set where speakers choose among alternatives that do (roughly) the same discourse job.

*Example from LBE paper:* in a fronting context, choose among Y ∈ {pied-piping headed NP, fused-head NP, other workaround …}.

For token i, let:
- Yᵢ = observed choice
- Rᵢ = register label (or register feature vector)
- Sᵢ = speaker index

The basic Bayesian object is a conditional distribution: **P(Yᵢ | Rᵢ, Sᵢ, …)**.

### Register in Bayesian Terms

A register is a **context-conditioned shift in the predictive distribution over constructions**.

Formally: register is the variable R that indexes (or predicts) the parameter(s) governing choice among alternatives in a niche.

**Notation:**
```
Yᵢ | Rᵢ = r  ~  Categorical(θ_r)
```

With uncertainty about θ_r:
```
θ_r  ~  prior over rates (e.g. Dirichlet for categorical; Beta for binary)
posterior: P(θ_r | data in register r) ∝ P(data | θ_r) P(θ_r)
```

**Interpretation:** "Register" is not a separate grammar; it is a different *conditional distribution* over the same menu of constructions, induced by situational variables.

**Drop-in phrasing:** "In Bayesian terms, a register is a conditioning variable on production probabilities: it does not introduce new structural possibilities so much as it shifts the expected rates of competing constructions within a stable opportunity set."

### Dialect in Bayesian Terms

A dialect is a **persistent shift in the distribution** that travels with speakers (or stable social groups) across situations.

Dialect is a speaker-linked (or group-linked) parameterisation that provides a **baseline across registers**, with register modulating around that baseline.

**Minimal encoding:**
```
Yᵢ | (speaker Sᵢ = s, register Rᵢ = r)  ~  Categorical(θ_{d(s), r})
```
where d(s) is the dialect (observed or inferred) associated with speaker s.

**Additive parameterisation (binary choice):**
```
logit P(Yᵢ=1 | d, r) = μ + δ_d + ρ_r + (optional interaction δρ_{d,r})
```

- δ_d = durable dialect effect
- ρ_r = situational register effect

Dialect differences are "broad": δ_d can be shared across many niches/features (phonology, lexicon, morphosyntax), not just one constructional choice.

### Discourse Community in Bayesian Terms

A discourse community is the **relevant population component you condition on when you decide what counts as normal**, often modelled as a latent mixture component over sources.

It's the variable C that says "which group's usage statistics am I using as the reference distribution right now?"

**Minimal mixture statement:**
```
Cᵢ  ~  Categorical(w)   (community assignment / component weight)
Yᵢ | (Cᵢ=c, Rᵢ=r)  ~  Categorical(θ_{c,r})
```

**Interpretation:** Discourse communities matter when learners/listeners do not pool all input as one homogeneous source. They maintain (implicitly or explicitly) separate expectations for "people like this" or "talk like this", and decide which component to use for prediction in the current interaction.

---

## Full Hierarchical Model (Sketch)

If you want to be explicit, the cleanest route is a hierarchical model with three distinct roles:
- **register** as an observed situational predictor
- **dialect** as a relatively stable speaker-level (or region/network-level) effect
- **discourse community** as a latent clustering/mixture structure over speakers (or over interactional networks)

**Token-level model (binary choice like fused-head vs pied-piping):**

For each opportunity i from speaker s in situation/register r:
```
y_i ∈ {0,1}
P(y_i = 1) = logit⁻¹(α + u_s + v_r + …)
```
where u_s is a speaker random effect (capturing persistent variety differences) and v_r is a register effect.

**Adding latent community:**
```
c_s ~ Categorical(w), with w ~ Dirichlet(…)
u_s = u_{c_s} + ε_s
u_{c} ~ Normal(0, σ_c)
```

Then "community" is literally the mixture component that shifts baseline rates.

**Style-shifting extension:** If people are partly in multiple communities, let each speaker have a mixture vector m_s (Dirichlet-distributed), and each token draws a community assignment z_i ~ Categorical(m_s). This matches the intuition that learners infer "this speaker is doing something marked in this context".

---

## Bayesian Semantics for "Sounds Unacceptable"

A form feels bad when it has extremely low posterior predictive probability under the distribution you're currently conditioning on:

```
posterior predictive: P(y_new | past data, C=c, R=r) = ∫ P(y_new | θ_{c,r}) P(θ_{c,r} | past data) dθ_{c,r}
```

So "that's not how we talk" corresponds to "under the listener's posterior predictive for the relevant community-and-register component, this utterance is near-zero probability relative to its alternatives".

---

## Realism Assessment

### Realistic as Statistical Idealisation: YES

A Bayesian model compactly represents three things:
1. learners are sensitive to relative frequencies (rates with denominators, not just raw counts)
2. learners update expectations with accumulating evidence
3. learners condition on source heterogeneity (different people/situations contribute different distributions)

You don't need to claim learners literally compute posteriors. "Bayesian" can be an *as-if* description: any incremental learner that strengthens hypotheses that predict observed data, weakens ones that don't, and partitions evidence by source will behave Bayes-like in aggregate.

### Realistic as Cognitive/Process Model: PLAUSIBLE BUT UNDERSPECIFIED

The core Bayesian update is cognitively cheap: after many "opportunities" with zero "hits", any learner that tracks contingency (even roughly) will converge to "don't expect this".

The psychologically loaded part is not the Bayes update; it's the notion of **"opportunity sets"** and the learner's ability to recognise them.

Realism hinges on whether conditioning variables are learnable/trackable:
- recognising fronting environments and relevant competitors is plausible (salient constructional families with recurring surface cues)
- treating "tokens from people like X" separately needs either observable correlates (speaker identity, network ties, platform, genre, stance) or strong priors

### Main Realism Problems

**A. Identifiability and interpretability**
Latent "discourse communities" inferred purely from construction rates are notorious for label-switching and weak identifiability. Fixable with anchors:
- metadata (speaker network, platform, region, age cohort)
- informative priors (few communities, alignment with known partitions)
- design where community membership is externally defined

**B. Confounding of register and community**
If "community" data all come from one register, register and community become statistically entangled. Need cross-classified evidence: same speakers across registers, or same registers across multiple communities.

**C. Data requirements**
Speaker-level community inference needs repeated observations per speaker. Corpus-level mixtures can be done with fewer assumptions, but then "community" is really "corpus source".

**D. Opportunity sets are doing heavy work**
The argument depends on "many chances for X to show up." A Bayesian model makes that precise only if the opportunity definition is defensible.

---

## Pragmatic Options for Modelling

### Option 1: Extend Beta–Binomial with Register Predictor (Robust, Interpretable)

Keep partial pooling, add register as a predictor (multilevel logistic regression / varying intercepts by corpus-register). Then you can say: even allowing register-conditioned rate shifts, the posterior mass for [phenomenon] remains near zero.

### Option 2: Light-Touch Mixture with External Anchors

If you have a dataset where community is externally meaningful (e.g., fandom subcorpus vs mainstream controls), treat community membership as observed, not latent. Then community becomes an estimable difference in θ between groups, and diffusion = changing mixture weights over time.

Both are "Bayesian" in the relevant sense, and both avoid inferring social structure from syntax alone.

---

## Literature

### Wiese 2023 – *Grammatical systems without language borders*

**Core thesis:** The basic unit of grammatical organisation is the communicative situation (com-sit), not a named language. "Free-range" settings (urban markets, heritage speakers, multiethnic peer groups, digital media) make this visible by showing grammar emerging from situationally organised repertoires.

**Key construct – communicative situation (com-sit):**
- A com-sit is the setting of communication as perceived by speakers: a dynamic, socially interpreted bundle of situational characteristics (participants, activity type, medium, goals, stance).
- Com-sits are primary; language categories emerge from com-sit distributions.
- Com-sit features can be encoded alongside phonology, syntax, and semantics (compatible with Construction Grammar, HPSG).

**Alignment with this framework:**
| This paper | Wiese 2023 |
|------------|------------|
| Register = context-conditioned subdistribution | Register = linguistic face of com-sit differences |
| Conditioning on situational variables | Com-sit = primary unit; grammar emerges from com-sit distribution |
| Discourse community = mixture component | Language labels = optional sociolinguistic indices over com-sit-based systems |
| Dialect = durable population conditioning | Dialect-like patterns emerge when com-sit clusters specialise |

**Mechanism for variety emergence:** Repeated co-occurrence in specific com-sits strengthens connections (entrenchment + alignment). This moves an unstructured "feature pool" toward a more structured "feature pond" – exactly the HPC story of clustering without hard borders.

**Acquisition evidence:** Children learn com-sit differentiation early. The "Daddy register" example (child uses German with father, then broadens to conventional com-sit) shows com-sit identification is a *learned hypothesis*, supporting the claim that learners track source heterogeneity.

**Three headline lessons:**
1. Com-sits support linguistic differentiation (speakers organise repertoires by com-sit).
2. Grammar is grounded in com-sits (selective reinforcement within com-sits creates grammar-like regularities).
3. "Languages" index belonging (named languages are optional sociolinguistic indices, not grammatically necessary).

**Cautions:** Wiese does not deny the reality of languages; she recasts them as sociolinguistic indices. Avoid straw-manning as "languages are unreal."

**Use in this paper:** Provides sociolinguistic legitimacy for treating register/dialect/discourse community as different slices of the same conditioning structure. Supplies empirical cases from "free-range" settings and acquisition evidence.

### O'Connor 2019 – *Games and kinds*

**Core thesis:** Even when property clusters exist, evolved terms may not map cleanly to them. Terms track *payoff space*, not property space.

**Key claims:**
- Evolutionary game theory (sim-max games) shows two failure modes for cluster-tracking: conventionality (multiple stable partitions) and functionality (payoff-relevant distinctions dominate).
- The link between property clusters and inductive success is not automatic; it depends on whether properties matter for payoffs.
- Promiscuous realism: kinds are natural *relative to* particular payoff-relevant purposes.

**Alignment with this paper:**
- Com-sits define payoff structures. Dialect/register choices evolve to solve social coordination problems (identity, prestige, alignment), not to mirror intrinsic structural clusters.
- Explains why sociolinguistic categories are messy: shaped by payoff relevance rather than property clustering alone.
- Multiple overlapping variety categories can coexist because different payoff spaces yield different stabilised partitions.

**Key quote:** "Terms track payoff space, not property space."

### O'Connor 2021 – *Measuring conventionality*

**Core thesis:** Conventions come in degrees of arbitrariness. An information-theoretic measure captures how constrained or underdetermined a conventional outcome is.

**Key claims:**
- Lewis-style conventions are binary, but real conventions vary in how many alternatives were plausible.
- Degree of arbitrariness = unpredictability of outcome in cultural evolutionary process.
- Functional and conventional explanations are complementary, not competing: many traits are both to differing degrees.

**Alignment with this paper:**
- Some dialect/register features are tightly constrained (low arbitrariness): e.g., turn-taking repair strategies, articulatory constraints on phonology.
- Others are highly arbitrary (high arbitrariness): e.g., choice of specific discourse markers, particular politeness formulae.
- "Functional does not mean inevitable; arbitrary does not mean useless."

### O'Connor 2022 – *Methods, models, and the evolution of moral psychology*

**Core thesis:** Triangulate sparse empirical data with formal evolutionary models. Game-theoretic models are especially useful because traits evolve to solve strategic social problems.

**Key claims:**
- Models by themselves explain behavior, not psychology. To connect to psychology, you need independent empirical evidence.
- Best practice: model results + empirical data + careful interpretation.
- Recurring strategic scenarios (PD, Stag Hunt, bargaining, coordination) shape which traits stabilise.

**Alignment with this paper:**
- Methodological justification for modeling sociolinguistic categories as emergent conventions shaped by strategic interactions.
- Com-sits are recurring strategic contexts (coordination games, signaling games, bargaining games over social meaning).
- "Communicative situations are not just contexts; they are recurring strategic games."

### O'Connor 2022 – *Why natural social contracts are not fair*

**Core thesis:** When social categories are introduced, cultural evolution predicts *inequity* as the robust outcome, not fairness. Discriminatory norms emerge easily and persist.

**Key claims:**
- Fairness is stable under symmetry (Nash demand game), but once agents recognize and condition on categories, unequal equilibria become focal.
- Minimal conditions for inequity: (1) individuals recognize social categories, (2) they condition behavior on category membership, (3) they adapt to improve their own payoff.
- Inequity is a stable equilibrium, not an anomaly. Fairness is fragile.

**Alignment with this paper:**
- Categories like "native speaker," "standard," dialect labels are exactly the coordination signals that stabilise inequity.
- Stigma and prestige are stable conventions, not noise.
- Register policing (e.g., "professional" register as gatekeeping) is an equilibrium, not mere prejudice.
- "As soon as categories become salient, coordination can stabilize inequity."

---

## Connections

- **LBE paper:** opportunity sets, zero-attestation logic, posterior predictive for unacceptability
- **HPC book:** varieties as cluster kinds; Part III on dynamics and emergence
- **Grammaticality papers:** normativity as conditioning, speaker variation
- **Labels_to_Stabilisers:** how labels (register names, dialect names) stabilise distributions
- **Wiese 2023:** com-sit as primary unit; varieties as different slices of com-sit conditioning

---

## Open Questions

1. How do learners *detect* community boundaries vs register shifts?
2. What's the acquisition timeline for community-conditioned expectations?
3. How do new communities crystallise (the Simpsons example)?
4. Relationship to sociolinguistic "style" (Labov, Eckert)?
5. Can this framework handle code-switching and translanguaging?

---

## Next Steps (When Ready)

1. Literature review: Labov, Eckert, Coupland on style/register; Bayesian sociolinguistics (Fruehwald?)
2. Identify a concrete empirical case (fused-head rates across registers? community-specific constructions?)
3. Sketch minimal model for HPC book chapter
4. Consider whether this becomes standalone paper or book section
