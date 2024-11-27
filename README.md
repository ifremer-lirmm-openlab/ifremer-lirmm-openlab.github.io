# Organisation Static Website

The website is available at : LINK HERE

## Overview

The pages are written in Markdown format.

All pages are strored in folder `docs/` and written in Markdwon format.

All related figures are stored in folder `docs/assets/` and saved as PNG.

The documentation is built as a static HTML web site with Mkdocs (https://www.mkdocs.org/getting-started/)

The rendering is configured with a config file at the root folder named `mkdocs.yml`.

## Setting the GitHub pipeline

Create the folder `.github/workflows/` and add a file nammed `deploy.yml` that have the following content

```yml
name: Deploy MkDocs to GitHub Pages

on:
  push:
    branches:
      - main  # Trigger deployment when changes are pushed to the main branch

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.9'

      - name: Install Dependencies
        run: |
          pip install mkdocs mkdocs-material

      - name: Build and Deploy
        run: |
          mkdocs gh-deploy --force

```