# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal study notes for the DataCamp "Natural Language Processing in Python" skill track. There is no application code, build, lint, or test suite — the content is Jupyter notebooks, one per course chapter, each next to the PDF of that chapter's slides:

- `01-natural-language-processing-in-python/<n>-<chapter-name>/<n>-<chapter-name>.ipynb`

Commits are one per topic covered (e.g. "TF-IDF vectorization", "Embeddings"), so new material is appended to the chapter notebook and committed per topic.

## Environment

- Dependencies are managed with pipenv (`Pipfile`, Python 3.13); the pyenv virtualenv is named after the repo, via `.python-version`.
- Install: `pipenv install`. Run notebooks: `pipenv run jupyter notebook`.
- Add a dependency with `pipenv install <pkg>` (keeps `Pipfile.lock` in sync).
- Libraries in use: nltk, scikit-learn, gensim, and Hugging Face `transformers` + `torch` (chapter 3 pipelines, zero-shot classification, QNLI). Hugging Face models download on first run, so chapter 3 needs network access and disk space.
