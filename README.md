# 30-Day Introduction to Biomedical Science (Quarto Book)

A Quarto-based repository configured for a 30-day biomedical science course and rendered by GitHub Actions onto GitHub Pages.

## Overview

The repository holds:

- [`.github/workflows/quarto-render.yml`](.github/workflows/quarto-render.yml): Install, setup, and render a Quarto book using R and Python
- [`_quarto.yml`](_quarto.yml): Core course/book metadata and chapter structure (for more options see [Quarto: Book Structure](https://quarto.org/docs/books/book-structure.html))
- [`index.qmd`](index.qmd): Course landing page

Additional files:

- [`requirements.txt`](requirements.txt): List of Python Packages to install
- [`DESCRIPTION`](DESCRIPTION): List of R Packages using the standard DESCRIPTION file to install with `pak`.

## Adding your day files

This repository is set up so you can drop in your course files later without creating them in advance.

When ready, add your files using this naming convention in the repository root:

- `day-01.qmd` through `day-30.qmd`

Then update the `book.chapters` section in [`_quarto.yml`](_quarto.yml) to include them in order.

## Publishing with GitHub Actions

Included in the repository is a custom GitHub Action that will automatically render and deploy the book onto GitHub Pages. 
Before the first run of the GitHub Action, please make sure to use locally in terminal the following:

```sh
quarto publish gh-pages
```

This command [initializes the `gh-pages` branch and turns on GitHub Pages for the repository](https://quarto.org/docs/publishing/github-pages.html#source-branch).

If you do not run this command before the first GitHub Action is triggered, you will likely encounter the following error message in the build log:

```sh
ERROR: No _publish.yml file available (_publish.yml specifying a destination required for non-interactive publish)
```

To avoid this issue, please make sure to run the GitHub Action locally so that GitHub can render and publish your Quarto document after every push to the repository.
