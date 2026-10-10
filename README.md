# Programming-Everyday-Decisions
This repository contains the lectures and tutorials of the course: Programming - Everyday Decision-Making Algorithms

## Build and publish

```bash
uv sync
uv run quarto render
bash ../Lecture-Foundations/scripts/publish-gh-pages.sh
```

The render also prints a PDF of every slide deck. The slide PDF hook needs the sibling checkout `../Lecture-Foundations`, `uv run playwright install chromium` once per machine, and rendering through `uv run`. A deck that cannot be printed fails the render on purpose, as its page already links the PDF. The publish script puts `_site/` online and keeps the `gh-pages` branch at one commit.
