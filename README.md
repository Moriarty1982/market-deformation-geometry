# Market Deformation Geometry

**A Teichmüller framework for structural change detection in multi-asset, multi-venue markets.**

A structure-first research framework that represents observable markets not as a collection
of isolated price charts, but as a synchronized tensor *P(t, a, b)* over time, asset, and
observation venue. Rolling market states become geometric patches, their evolution a
deformation map, and quasiconformal dilatation — via the Beltrami coefficient — a candidate
measure of *structural* market change, distinct from price movement. Foreign exchange serves
as the running example; the construction applies to any universe of instruments observed
through several venues.

This is a research programme, deliberately without empirical results: hypotheses, null
models, estimator-validation tests, and falsification criteria are fixed **before** anything
is measured.

## Contents

| File | Purpose |
|---|---|
| `market-deformation-geometry.tex` | **The canonical source of the paper.** All content changes happen here. |
| `market-deformation-geometry.pdf` | The archival rendering, compiled from the `.tex`. Never edited directly. |
| `.zenodo.json` | Deposit metadata read by Zenodo when a GitHub release is archived. |

Rebuild the PDF after every content change (two passes, for TOC and references):

```
docker run --rm -v "$PWD:/work" -w /work texlive/texlive:latest sh -c "pdflatex -interaction=nonstopmode market-deformation-geometry.tex && pdflatex -interaction=nonstopmode market-deformation-geometry.tex"
```

Any local `pdflatex` works equally well. The PDF is committed so that the Zenodo–GitHub
integration — which archives the repository snapshot of a release — always contains a
reader-ready, self-contained copy.

## Status

Working paper, v0.1 line. No empirical results yet — see the falsification criteria and the
research-status matrix (Appendix E) inside the paper for what is established mathematics,
what is proposed, and what is merely hypothesized.

## Publishing via Zenodo

This directory is laid out so it can become the root of a standalone public repository and
be archived with a DOI through the Zenodo–GitHub integration:

1. **Split this directory into its own public GitHub repository** (subtree split, or copy —
   history is optional for a paper).
2. `.zenodo.json` already carries the deposit metadata (author, license CC-BY-4.0,
   keywords); optionally add an ORCID to the `creators` entry before the first release.
3. On [zenodo.org](https://zenodo.org), log in with GitHub and **enable the repository**
   under *GitHub* in the account settings.
4. **Create a GitHub release** (e.g. tag `v0.1.0`). Zenodo archives the release
   automatically and mints two DOIs: one for the version, one concept DOI that always
   resolves to the latest version.
5. Add the DOI badge Zenodo provides to this README and cite the concept DOI.

Optionally generate a PDF of the paper (print-to-PDF from the HTML preserves the layout)
and attach it to the release, since PDF is the conventional archival format.

## License

CC-BY-4.0, as declared in `.zenodo.json`, effective with the first public release.
