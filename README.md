# Python Mastery

A Quarto book that takes you from zero programming experience to advanced Python — one continuous read across 36 chapters.

**📖 Read online:** <https://vthanik.github.io/python-mastery/>

## What's in the book

The pedagogical model is *R for Data Science* + *Advanced R* unified into one volume — a beginner-friendly first pass, then the same topics deconstructed in depth.

| Part | Chapters | What it covers |
| --- | --- | --- |
| 0 — Foundations | 12 | Mental models, primitives, control flow, collections, functions, errors, files, classes, modules, the standard library |
| I — Data Structures | 6 | The data model, sequences, dicts/sets, unicode, dataclasses, references and mutability |
| II — Functions as Objects | 4 | First-class functions, type hints, decorators, design patterns |
| III — Classes and Protocols | 5 | Pythonic objects, sequence methods, protocols and ABCs, inheritance, advanced typing |
| IV — Control Flow & Concurrency | 6 | Operator overloading, iterators, `with`/`match`/`else`, concurrency, executors, async |
| V — Metaprogramming | 3 | Dynamic attributes, descriptors, metaclasses |

Every code block is executed during the build — the output you read is the output the code produced.

## Sources

- **Part 0** distilled from a from-scratch beginner's guide.
- **Parts I–V** distilled from Luciano Ramalho's *Fluent Python* (2e, O'Reilly Media 2022).
- **David Beazley's *Python Distilled*** (Addison-Wesley 2022) cited throughout as a secondary operational reference.

## Building locally

```bash
# One-time setup
python3.13 -m venv .venv
.venv/bin/pip install jupyter ipykernel nbformat nbclient

# Render to HTML
QUARTO_PYTHON=.venv/bin/python quarto render

# Live-reload preview
QUARTO_PYTHON=.venv/bin/python quarto preview
```

Rendered HTML lands in `_book/`. Open `_book/index.html`.

## Structure

The project mirrors the layout of [`hadley/ggplot2-book`](https://github.com/hadley/ggplot2-book) — flat `.qmd` files in the project root, ordered and grouped into parts via `_quarto.yml`.

## Contributing

Found a typo, a confusing passage, or a code block that won't run? Open an issue or a pull request — every chapter has an "Edit this page" link in the right sidebar.
