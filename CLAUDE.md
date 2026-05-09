# CLAUDE.md — Fluent Python Book

Project context for future Claude sessions.

## What this is

A Quarto book distilled from Luciano Ramalho's *Fluent Python* (2e). Renders
to HTML and PDF. The structure intentionally mirrors `hadley/ggplot2-book`:
flat `.qmd` files in the project root, ordered and grouped into parts via
`_quarto.yml`.

## Source files

| Role | Path |
| --- | --- |
| Primary notes (chapter structure, callouts, code) | `~/Downloads/fluent_python_notes.txt` |
| Secondary reference (clarification only) | `~/Downloads/luciano-ramalho-fluent-python_-clear-concise-and-effective-programming-oreilly-media-2022.pdf` |
| Structural template | `https://github.com/hadley/ggplot2-book` |

The notes file maps cleanly onto Fluent Python 2e: 5 parts, 24 chapters,
each with consistent markers (`◈ Core idea`, `◈ Key concepts`, `◈ Code`,
`◈ The insight`).

## Authoring rules

These come from the agreed plan and are non-negotiable:

1. **Verbatim callouts.** "Core idea" and "Why this matters" callouts in
   each chapter are transcribed verbatim from the notes. Do not paraphrase
   them — they are the user's words.
2. **No invented examples.** Every code block must trace to a code block in
   the notes (primary) or the PDF (secondary). No fabricated benchmarks,
   no invented quotes from Ramalho.
3. **Paraphrase the PDF.** When the PDF is consulted, paraphrase in a
   sentence or two and attribute by chapter and page. Never reproduce
   long passages — respects copyright and matches Hadley's own pattern.
4. **Exercises are an authored addition.** They are derived from existing
   examples in the notes (e.g., extend the `Vector` class). The preface
   states this explicitly.

## Status

| Chapter | File | State |
| --- | --- | --- |
| 1. Data Model | `data-model.qmd` | full |
| 2. Sequences | `sequences.qmd` | full |
| 3. Dicts & Sets | `dicts-sets.qmd` | full |
| 4–24 | various | stubs (title + Core idea callout + "In progress") |

When the user is happy with the style of the first three, fill in the rest
following the **same chapter template** (see `data-model.qmd` as the
canonical example):

1. `# Title {#sec-slug}` (slug matches the filename)
2. Optional epigraph in `>` quote
3. `:::{.callout-note}` "Core idea" — verbatim from notes
4. Numbered learning goals
5. One section per `◈` block in the notes
6. `:::{.callout-tip}` "Why this matters" — verbatim from notes' "The insight"
7. Numbered exercises (3–5)
8. Summary paragraph pointing to the next chapter

## Build

```bash
# Quarto is bundled with Positron:
QUARTO=/Applications/Positron.app/Contents/Resources/app/quarto/bin/quarto

$QUARTO render               # build the book
$QUARTO preview              # live reload
$QUARTO check                # verify environment
```

Jupyter is required at render time (`engine: jupyter` in `_quarto.yml`).
Install once with `pip install jupyter ipykernel`.

## Skills used

- `quarto-authoring` — for callouts, cross-references, YAML idioms.

## Out of scope

- Beginner Python content. The book starts where Fluent Python starts.
- Publishing / hosting. Local rendering only.
- CI to rebuild on changes.

## Things not to do

- Do not delete pre-existing dead code in the boilerplate (`style.css`,
  `preamble.tex`) — surgical changes only.
- Do not inline content from the PDF beyond a sentence-or-two paraphrase.
- Do not add features to chapters beyond what was agreed in the plan.
