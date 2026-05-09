# CLAUDE.md — Python: From Foundations to Mastery

Project context for future Claude sessions.

## What this is

A Quarto book that takes a reader from zero programming experience to advanced
Python. Renders to HTML and PDF. The structure mirrors `hadley/ggplot2-book`:
flat `.qmd` files in the project root, ordered and grouped into parts via
`_quarto.yml`.

The pedagogical model is *R for Data Science* + *Advanced R* unified into one
continuous read. Foundations chapters give the *first pass* at decorators,
generators, dataclasses, async, and classes; Parts I–V *deconstruct* them
through the data model, protocols, descriptors, and metaclasses.

## Sources

| Role | Path / citation |
| --- | --- |
| Primary for Foundations (Part 0) | `~/Downloads/python_from_scratch.txt` |
| Primary for Parts I–V | `~/Downloads/fluent_python_notes.txt` |
| Reference text (Parts I–V) | `~/Downloads/luciano-ramalho-fluent-python_-clear-concise-and-effective-programming-oreilly-media-2022.pdf` |
| Secondary reference (whole book) | `~/Downloads/Python Distilled - David M Beazley 2.pdf` |
| Structural template | `https://github.com/hadley/ggplot2-book` |

The Foundations notes are pre-chunked into 14 chapters (0–13) with `CHAPTER N · Title`
markers and `THE CORE IDEA:` callouts. The Fluent Python notes are 5 parts /
24 chapters with `◈ Core idea`, `◈ Key concepts`, `◈ Code`, `◈ The insight` markers.

## Authoring rules

These come from the agreed plan and are non-negotiable:

1. **Verbatim callouts.** "Core idea" callouts are transcribed verbatim from
   the source notes. Do not paraphrase them — they are the source's words.
2. **No invented examples.** Every code block must trace to the source notes
   (primary) or the canonical book PDFs (secondary). No fabricated benchmarks,
   no invented quotes.
3. **Paraphrase the PDFs.** When Ramalho or Beazley is consulted, paraphrase
   in a sentence or two and attribute by chapter and section. Never reproduce
   long passages.
4. **Beazley is light-touch.** He appears as "Further reading" callouts on 7
   existing chapters and as a co-primary reference in
   `modules-and-packages.qmd` and `standard-library-tour.qmd` (where Ramalho
   is silent). No paraphrased Beazley examples in other chapter bodies.
5. **Exercises are an authored addition.** Derived from the existing examples
   on the page. The preface states this explicitly.
6. **"Going deeper" forward references.** Every Foundations chapter ends with
   explicit pointers to the chapter in Parts I–V where the topic is taken
   further. This is the bridge.

## Status — all 36 chapters full

| Part | qmd files (state) |
| --- | --- |
| Part 0 — Foundations | how-python-thinks, values-and-variables, strings-and-text, control-flow-basics, collections-basics, functions-basics, errors-and-exceptions, files-and-io, classes-basics, modules-and-packages, standard-library-tour, writing-real-programs (12 ✓ full) |
| Part I — Data Structures | data-model, sequences, dicts-sets, unicode, dataclasses, references-mutability (6 ✓ full) |
| Part II — Functions as Objects | first-class-functions, type-hints, decorators, design-patterns (4 ✓ full) |
| Part III — Classes and Protocols | pythonic-objects, sequence-methods, protocols-abcs, inheritance, advanced-typing (5 ✓ full) |
| Part IV — Control Flow & Concurrency | operator-overload, iterators, with-match-else, concurrency, executors, async (6 ✓ full) |
| Part V — Metaprogramming | dynamic-attrs, descriptors, metaclasses (3 ✓ full) |

Beazley "Further reading" callouts inserted in: `pythonic-objects.qmd`,
`decorators.qmd`, `inheritance.qmd`, `concurrency.qmd`, `executors.qmd`,
`async.qmd`, `with-match-else.qmd`.

## Per-chapter template

1. `# Title {#sec-slug}` (slug matches filename)
2. `:::{.callout-note}` "Core idea" — verbatim from source
3. Numbered learning goals
4. One section per `◈` block (or `┌─ Boxed Section ─┐` for Foundations)
5. Runnable `{python}` code cells
6. `:::{.callout-tip}` "Why this matters"
7. **(Foundations only)** "Going deeper" forward reference to a Part I–V chapter
8. **(Selected chapters)** `:::{.callout-note}` "Further reading" — Beazley citation
9. Numbered exercises (3–5)
10. Summary paragraph pointing to the next chapter

## Build

```bash
quarto check               # verify environment
quarto render              # build _book/
quarto preview             # live reload
```

Jupyter is required at render time (`engine: jupyter` in `_quarto.yml`).
The project venv is at `.venv/` with `jupyter`, `ipykernel`, `nbformat`,
`nbclient` installed via `uv pip`.

## Skills used

- `quarto-authoring` — for callouts, cross-references, YAML idioms.

## Out of scope

- Publishing / hosting. Local rendering only.
- CI to rebuild on changes.
- Substantial rewrites of existing chapter prose. Surgical changes only.

## Things not to do

- Do not delete pre-existing dead code in the boilerplate (`style.css`,
  `preamble.tex`) — surgical changes only.
- Do not inline content from any of the source PDFs beyond a sentence-or-two paraphrase.
- Do not paraphrase Beazley examples into existing chapter bodies — keep him
  in "Further reading" callouts and the two designated chapters.
- Do not add features to chapters beyond what was agreed in the plan.
