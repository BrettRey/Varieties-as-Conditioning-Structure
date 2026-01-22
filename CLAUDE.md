# CLAUDE.md

This file provides guidance to Claude Code when working in this repository.

## Project Overview

**Title:** Varieties as Conditioning Structure
**Author:** Brett Reynolds
**Stage:** Seed → paper draft
**Feeds into:** HPC book (Part III or IV)

An HPC-Bayesian framework treating discourse community, register, and dialect as conditioning variables in a probabilistic model of construction choice. The core insight: these variety types differ only in *what you condition on* and *how stable that conditioning is across situations and speakers*.

## Core Concepts

- **Discourse community** = "whose data are we conditioning on?" (latent mixture component)
- **Register** = "in what activity context?" (situational conditioning within a variety)
- **Dialect** = "which durable bundle of distributions?" (population conditioning across varieties)

## Build System

This LaTeX project requires **XeLaTeX** (not pdfLaTeX) due to the Charis SIL font requirement.

**Avoid LuaLaTeX** – it tends to run words together in the underlying PDF text layer, breaking copy-paste and accessibility.

### Compilation Commands

```bash
# Full build sequence
xelatex main.tex
biber main
xelatex main.tex
xelatex main.tex

# Or use automated build
make              # Full build
make quick        # Single pass
make clean        # Clean artifacts
```

## File Structure

```
Varieties_as_Conditioning_Structure/
├── main.tex                  # Main document
├── notes.md                  # Exploratory notes (source material)
├── references.bib            # → symlink to .house-style/references.bib
├── .house-style/             # → symlink to house style
├── Makefile                  # Build automation
├── STATUS.md                 # Project status
└── CLAUDE.md                 # This file
```

## House Style

This project uses Brett Reynolds house style (see `.house-style/style-guide.md`).

### Key Conventions

**Terms, Mentions, Quotations:**
- `\term{}` for concepts (small caps): `\term{register}`
- `\mention{}` for forms (italics): `\mention{the}`
- `\enquote{}` for quotations

**Writing Style:**
- Contractions preferred
- ~60 word paragraphs (max 100)
- Simple coordinators (and, but) over hackneyed connectives
- *Data* is singular
- Avoid "wh-" terminology – use interrogative/relative/exclamative

**Citations:**
- Parenthetical: `\citep{key}`
- Textual: `\textcite{key}`
- Must be verified against sources – never fabricate

## Connections to Other Projects

- **English_LBC_functionalist:** opportunity sets, posterior predictive for unacceptability
- **Grammaticality_de_idealized:** normativity as conditioning
- **Labels_to_Stabilisers:** how labels stabilise distributions
- **HPC book:** varieties as cluster kinds

## Role

When working in this project directory, Claude's role is **Editor/Researcher** (not PM). Deep editorial work is welcome here.
