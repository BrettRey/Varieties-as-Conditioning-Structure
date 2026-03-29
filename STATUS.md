# STATUS: Varieties as Conditioning Structure

**Stage:** Draft / submission polishing
**Created:** 2026-01-20

## What This Is

HPC-Bayesian framework for discourse community, register, and dialect as conditioning structure in a probabilistic model of construction choice.

Core insight: the three variety types differ only in *what you condition on* and *how stable that conditioning is across situations and speakers*.

## Current State

- `notes.md`: Comprehensive capture of informal + formal definitions, Bayesian formalisation, realism assessment, modelling options
- `slides-v3.qmd`: Talk slides delivered at LVC study group 2026-03-27. Talk went well.
- `slides.qmd`, `slides-v2.qmd`: Earlier iterations (kept for reference)

## Likely Trajectory

1. HPC book section (Part III or IV on dynamics/emergence)
2. Possible standalone paper if the framework proves generative

## Session Log

### 2026-03-26 (Claude, afternoon)
- Created `slides.qmd` (Quarto revealjs + house style) for LVC study group talk on 2026-03-27
- Brett rewrote slides: personal Japan examples, quotative like/だよね trajectories, humble framing, predictions slide, backup formal notation slide
- Slide order question flagged by Brett ("middle bit" backwards) -- not yet resolved
- Talk is at 10:10, second talk starts at 10:50

### 2026-03-26 night – 2026-03-27 afternoon (Claude, marathon session)
- Major restructuring of slides through v1, v2, v3 iterations with multiple review boards
- Centred talk on HPC theory (saber-tooth opening, bridge to LVC, reciprocity)
- Key intellectual breakthroughs in dialogue: coordination loss (not deadweight loss), passing/raciolinguistic perception as mirror cases, varieties real the way words are real, divergence stable like cattle at countability boundary, all divergence pairs (not just A/I), S×A/I interaction testable but direction-indeterminate
- Separated HPC contribution from S/A/I contribution as distinct slides
- O'Connor gets own slide before dark side
- Avoided "appropriateness" (Flores & Rosa) — use "listener expectation"
- Brett made significant manual edits: rewrote slide 4 ("each variable, each grammar is a category, and social context is one of the homeostatic properties"), expanded mirror-cases slide with Bayesian framing, connected divergence slide to three waves
- Fixed settings: effort level defaulted to max, env var for subagents
- Meta-lesson: best results came from genuine co-thinking, not production mode; review boards useful as guides not masters

### 2026-03-27 morning (Claude Opus, pre-talk session)
- Read all four O'Connor papers (Games and Kinds 2019, Measuring Conventionality 2021, Methods/Models/Moral Psychology 2022, Why Natural Social Contracts are Not Fair 2022)
- Major integration of O'Connor into slides: exogenous vs endogenous stabilizers, basins of attraction, cultural red king effect
- Key insight: coordination costs are a fourth stabilizer (endogenous), interpenetrating with S/A/I (exogenous). Disagree with O'Connor on primacy.
- Variables live at divergence points of the conditioning space — genuine novel prediction
- Cut restaurant slide (anecdote isn't data), cut like/だよね (secondary), moved Bayes to mirror cases
- Renamed "dark side" → "origins of unfairness"
- D&S (Drummond & Schleef 2016): framework resolves waves 1-3 tension re identity
- Review board (5 reviewers): all R&R. Consensus: A/I mirror cases are strongest contribution; no empirical demo is main weakness; projectibility disappears in middle slides
- Acted on reviews: threaded projectibility through middle slides, restructured "What HPC adds," replaced "appropriateness," acknowledged third-wave overlap in notes, named political forces in Belfast
- Talk delivered successfully at 10:10

### 2026-03-28 afternoon/evening (Claude Opus, paper revision session)
- Executed 8-task revision plan addressing review board feedback
- Major additions: O'Connor integration, Kiesling appendix, Bayesian joint model, third-wave engagement, divergence-point prediction, HPC argument, Cavell connection
- "Appropriateness" → "participant expectation" throughout
- R2 review board: projectibility reviewer accepted; all others minor R&R
- Made HPC argument directly rather than deferring to book
- Polish pass: priamel opening, ring structure, rhetorical figures, humor, dash audit
- Metacommentary and corrective framing rules added to house style guide
- De-structured over-sectioned material (Sections 2, 3, 4, 7)
- Brett took over with ChatGPT for continued editing during the session
- Paper approaching LingBuzz-ready state

### 2026-03-29 afternoon (Codex, revision + ship)
- Tightened the paper around a weaker and cleaner claim: varieties are worth positing when they support stable, purpose-relative prediction; the draft no longer tries to win the full HPC-threshold question.
- Reworked the exogenous/endogenous split so S/A/I are explicit exogenous maintenance dynamics feeding the Bayesian layer, while coordination costs remain endogenous and group-level.
- Fixed Section 5 technical issues: exchangeability now holds across encounters sharing an S/A/I configuration, not within them; RSA/social-meaning work is cited; notation and glosses were tightened.
- Added a more concrete identification-operationalization paragraph and an explicit raciolinguistic-listening limitation.
- Reworked Section 7 so inequity is tied to purpose-relative projectibility and to shifts among situation, identification, and outsider ascription.
- Rewrote the conclusion, then resynced the abstract and introduction to match the weaker claim and removed wording that presupposed the revision history.
- House-style cleanup continued throughout; `check-style.py` is clean and `make` succeeds. Remaining build noise is limited to the small overfull box in the Bayesian opening and the usual `microtype`/font warnings.

### 2026-03-29 afternoon (Claude Opus, review board + polish + ship)
- Three rounds of review board (5 independent reviewers each), synthesized after each round. Consensus: A/I separation is strongest move; HPC threshold question is the biggest remaining exposure; identification operationalizability is the practical bottleneck.
- Proofread audit (linter + manual checklist): fixed AI voice words (underpin→ground, robust→persistent), punctuation (⟨Th⟩→⟨th⟩, comma collision→parentheses, bare commas→en-dashes), split overlong paragraph, cut breezy aside.
- Bibliography validation: all 28 citation keys resolve; 9 local entries ready for `/push-bib`.
- HPC projectibility audit: GREEN across all 7 checks. Projectibility is structural, not decorative.
- Conclusion fix: echoed purpose-relative projectibility across parties (same category supports different inferences for in-group vs. outsider).
- Paper posted to LingBuzz. 18 pages, clean build.

## Connections

- English_LBC_functionalist (opportunity sets, posterior predictive)
- Grammaticality_de_idealized (normativity as conditioning)
- Labels_to_Stabilisers (how labels stabilise distributions)
- HPC book (varieties as cluster kinds)

### Literature: Many Minds podcast (Frank & Lupyan, 2026-03-26)
- **WEIRD problem in AI:** Frank: "if the people that the models are interacting with are substantially underrepresented then there are concerns." If models trained on English text produce English-biased cognition, that's varieties-as-conditioning-structure operating on AI.
- **Instruction tuning ≈ education:** Lupyan: base models need instruction tuning to become competent conversationalists. Parallel to how social context (education, register, community) conditions linguistic behaviour — conditioning structure shapes output.
- See `literature/many-minds-frank-lupyan-2026.md` for full notes + transcript.
