# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Quarto-based educational website for the course "Programming: Everyday Decision-Making Algorithms" at Kühne Logistics University. The course teaches algorithmic thinking concepts (optimal stopping, explore/exploit, caching, scheduling, randomness) while introducing Python programming to business students.

## Build Commands

```bash
# Render the entire website (the slide PDF hook needs uv)
uv run quarto render

# Publish that build and keep gh-pages at one commit; a bare `quarto publish` re-renders outside uv and fails
bash ../Lecture-Foundations/scripts/publish-gh-pages.sh

# Preview with live reload
uv run quarto preview

# Render a single file
uv run quarto render lectures/lec_01_optimal_stopping.qmd

# Check Quarto installation (may need QUARTO_CHROMIUM set for PDF export)
QUARTO_CHROMIUM=/Applications/Brave\ Browser.app/Contents/MacOS/Brave quarto check
```

## Python Environment

The project uses `uv` for Python dependency management (Python 3.12):

```bash
# Sync dependencies from pyproject.toml
uv sync

# Run Python scripts
uv run python script.py

# Add a package
uv add package_name
```

Key dependencies: jupyter, jupytext, matplotlib, numpy, pandas

## Repository Structure

- `lectures/` - RevealJS slide decks (`.qmd` files with `format: revealjs`)
- `tutorials/` - Interactive Python tutorials in Quarto format
- `general/` - Course information pages (syllabus, FAQ, installation guide)
- `_quarto.yml` - Main Quarto configuration (website structure, theme, output formats)
- `_brand.yml` - Brand/styling configuration
- `styles.scss` - Custom SCSS styles
- `helpers/` - Conversion scripts (pypercent format)
- `include/` - Reusable Quarto includes (e.g., tutorial_end.qmd)
- `_site/` - Generated output (do not edit)

## Content Authoring

- Lectures use RevealJS format with custom CSS classes (`.flow`, `.highlight`, `.question`, `.incremental`)
- Tutorials include executable Python code cells
- The `execute: freeze: true` setting caches code execution results
- With `freeze: true` a full render does not pick up edits to a file that has code cells, not even to its text: render that file on its own first (`uv run quarto render path/to/file.qmd`), then the site
- The diagrams in lecture 4 need a browser of their own: if a render hangs there, set `QUARTO_CHROMIUM` to a Chromium binary (Playwright's works)
- Output formats: HTML (primary) and Typst (PDF)
- Two post-render hooks from `../Lecture-Foundations/scripts/` (`split_refs_post.py`, then `create_pdf.py`) print each rendered deck to `lec_XX_presentation.pdf` next to it, linked per lecture via `format-links` ("Slides (PDF)"). The slide PDF hook needs the sibling checkout `../Lecture-Foundations`, `uv run playwright install chromium` once per machine, and rendering through `uv run`. A deck that cannot be printed fails the render on purpose, as its page already links the PDF.

## Shared foundations

`../lecture-foundations` holds the cross-course standard (branding,
slide/tooling conventions, quizkit guides) and shared scripts. Two of them
need a rendered `_site/` and a one-time `uv add --dev playwright`: the
revealjs slide overflow gate
(`uv run ../lecture-foundations/scripts/check_slide_overflow.py`) and the
slide-deck PDF exporter
(`uv run ../lecture-foundations/scripts/create_pdf.py --dir _site/ --output-dir pdf-slides/`).
Check it before solving a problem that smells course-generic — it may
already be solved there, and generic fixes belong there, not here.
