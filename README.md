# Fluent Python — A Distillation

A Quarto book distilled from Luciano Ramalho's *Fluent Python* (2nd edition,
O'Reilly Media, 2022). Twenty-four chapters, five parts, structured for
working programmers who already know basic Python.

## Building the book

```bash
# One-time setup
pip install jupyter ipykernel

# Render to HTML
quarto render

# Preview with live reload
quarto preview
```

The rendered HTML lands in `_book/`. Open `_book/index.html`.

## Structure

The project mirrors the layout of `hadley/ggplot2-book`. Chapters are flat
`.qmd` files; `_quarto.yml` controls order and grouping into parts.

## Status

| Chapter | State |
| --- | --- |
| 1. The Python Data Model | full |
| 2. An Array of Sequences | full |
| 3. Dictionaries and Sets | full |
| 4–24 | stubs |

## Source notes

The book is built from `~/Downloads/fluent_python_notes.txt`, with
`~/Downloads/luciano-ramalho-fluent-python_-clear-concise-and-effective-programming-oreilly-media-2022.pdf`
as a secondary reference for clarification only.
