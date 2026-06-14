# 30-Day Introduction to Biomedical Science (Quarto Book)

A Quarto-based repository configured for a 30-day biomedical science course and rendered by GitHub Actions onto GitHub Pages.

## Overview

The repository holds:

- [`.github/workflows/quarto-render.yml`](.github/workflows/quarto-render.yml): Install Quarto CLI, install Python dependencies, render, and deploy the Quarto book
- [`_quarto.yml`](_quarto.yml): Core course/book metadata and chapter structure (for more options see [Quarto: Book Structure](https://quarto.org/docs/books/book-structure.html))
- [`index.qmd`](index.qmd): Course landing page
- [`syllabus.qmd`](syllabus.qmd): Syllabus page with links to all day lessons

Additional files:

- [`requirements.txt`](requirements.txt): List of Python Packages to install
- [`DESCRIPTION`](DESCRIPTION): Optional R package metadata for local/project use.

## Adding your day files

This repository is set up so you can drop in your course files later without creating them in advance.

When ready, add your files using this naming convention in the `day/` folder:

- `day/day-02.qmd` through `day/day-31.qmd`

Then update the `book.chapters` section in [`_quarto.yml`](_quarto.yml) to include them in order.

## Publishing with GitHub Actions

Included in the repository is a GitHub Actions workflow that renders the Quarto book and deploys it to GitHub Pages using the built-in Pages artifact/deploy workflow.

This setup does **not** require a `gh-pages` branch or `quarto publish gh-pages`.

For repository settings, make sure:

1. GitHub Pages is enabled.
2. The Pages source is set to **GitHub Actions**.

After that, pushes to `main`/`master` will render and deploy automatically, and pull requests will run render checks without deploying.
