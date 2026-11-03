# Public LaTeX paper template

This repository provides a shared-content LaTeX structure for adapting one manuscript to multiple journal formats.

## Layout

- `content/content.tex`: shared manuscript body included by every adapter.
- `content/abstract.tex`: shared abstract.
- `references/references.bib`: bibliography database.
- `ieee-latex/main.tex`: IEEE-style adapter.
- `wiley-latex/main.tex`: Wiley-style adapter.
- `else-latex/main.tex`: Elsevier CAS-style adapter.

Each adapter owns journal metadata, package configuration, bibliography style, and the document wrapper. Keep article sections, figures, tables, and citations in `content/` and `references/` so that the same content can be reused.

## Build

Run `latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex` from an adapter directory. The repository intentionally excludes compiled output and private manuscript materials.
