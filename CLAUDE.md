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
- Libraries in use: nltk, scikit-learn, gensim, and Hugging Face `transformers` + `torch` (chapters 3–4: pipelines, zero-shot classification, QNLI, NER, question answering, text generation). Hugging Face models download on first run, so these chapters need network access and disk space.
- `transformers` is pinned to `<5` in the `Pipfile` on purpose: the course code uses pipeline tasks and arguments that 5.x removed (e.g. the `question-answering` task). Quote the specifier in shell commands (`pipenv install "transformers<5"`), otherwise `<5` is parsed as a redirect. Prefer `aggregation_strategy="simple"` over the deprecated `grouped_entities=True` for NER pipelines.
- The notebook kernel runs in the pyenv virtualenv (`~/.pyenv/versions/natural-language-processing-in-python`), which `pipenv run` may not resolve to. To check the installed version, use that environment's Python directly rather than `pipenv run`.
- If a notebook fails on a course snippet, the cause is usually a library version difference from the course's, not the code.
