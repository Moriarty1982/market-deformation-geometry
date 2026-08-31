# Market Deformation Geometry

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22051019.svg)](https://doi.org/10.5281/zenodo.22051019)

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

Working paper, v0.4 line. Since v0.3.0 the paper reports the results of a first
implementation cycle (Stages I–II plus a measurement floor for the conformal shape) and a
mathematical sharpening: on simply connected patches the proposed distance is identically
zero, so the tractable carrier of Teichmüller structure is the torus, where the distance
has a closed form and coordinate robustness (H7) is a theorem for that estimator. v0.4.0
adds the preregistered **estimation floor**: against the sampling noise of the window
covariance — measured with an instrument validated against a registered χ² prediction, a
published analytic sampling law, exact GL(2) invariance, and a direction-null control —
the daily shape movement runs at ≈2.0× the floor (not the 9.8× venue-floor headline), the
preregistered verdict is *undecidable* in 43 of 45 pairs, and every subsection of the
empirical cycle has now passed a dedicated adversarial review. v0.4.1 corrects a √2 unit
slip in the escape-route figures of that section (caught while preregistering the
follow-up: in consistent pair units the escape needs ≈2.1× the measured floor, not 1.4×,
and the diffusive overshoot is 4.9×, not 4× — both corrections strengthen the claim) and
records that the deciding volatility-clustering null is now preregistered and frozen.
None of the hypotheses H1–H6 has been tested — see the falsification criteria and the
research-status matrix (Appendix E) inside the paper for what is established mathematics,
what is proposed, what is measured, and what is merely hypothesized.

## Citing

Cite the concept DOI, which always resolves to the latest version:

> Brendecke, M. (2026). *Market Deformation Geometry: A Teichmüller Framework for
> Structural Change Detection in Multi-Asset, Multi-Venue Markets.* Zenodo.
> https://doi.org/10.5281/zenodo.22051019

## Releasing a new version

The repository is connected to Zenodo through the GitHub integration; every GitHub
release is archived automatically and receives its own version DOI under the concept
DOI above. To publish a new version:

1. Edit `market-deformation-geometry.tex` and rebuild the PDF (command above).
2. Commit, then create a GitHub release with the next tag (e.g. `v0.2.0`), attaching
   the rebuilt PDF as a release asset.
3. Zenodo picks up the release within minutes — no further action needed.

`.zenodo.json` carries the deposit metadata (author, license, keywords); an ORCID can
be added to the `creators` entry at any time and takes effect with the next release.

## License

CC-BY-4.0, as declared in `.zenodo.json`, effective with the first public release.
