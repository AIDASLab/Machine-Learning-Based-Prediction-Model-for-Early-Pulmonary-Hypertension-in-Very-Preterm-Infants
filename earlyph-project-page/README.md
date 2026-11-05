# Machine Learning-Based Prediction of Early Pulmonary Hypertension in Very Preterm Infants

Project page for the study, built on the
[AIDAS Lab project page template](https://github.com/AIDASLab/aidas-project-page-template)
(derived from [Nerfies](https://nerfies.github.io)).

## Run it locally

```bash
python3 -m http.server 8000 --bind 127.0.0.1
# open http://localhost:8000
```

## Deploy to GitHub Pages

Push this directory to a repository, then **Settings → Pages → Source: Deploy from a branch →
`main` / `(root)`**. The site is live at `https://<user>.github.io/<repo>/` within a minute or two.

No build step and no external requests — every stylesheet, script, font and image is served from
this directory, so the page renders identically offline and behind restrictive networks.

## Layout

```
index.html              the whole page, including four figures as inline SVG
static/css/index.css    template styles + this page's additions at the bottom
static/css/fonts.css    self-hosted Noto Sans
static/fonts/           the two woff2 files it references
static/images/          roc-curves.png, plus the template's logos and favicon
static/js/              jquery, bulma-carousel, bulma-slider, fontawesome, index.js
```

Sections run **Abstract → Methods → Results → Analysis → BibTeX**, with the ROC curves as the teaser.

## Figures

| Figure | Section | Form |
| --- | --- | --- |
| ROC curves | Teaser | `static/images/roc-curves.png` |
| Cohort selection | Methods | Inline SVG |
| Prediction / outcome windows | Methods | Inline SVG |
| Performance radar | Results | Inline SVG |
| SHAP value distributions | Analysis | Inline SVG |

All inline SVGs use CSS classes rather than hardcoded colors — `d-*` for the hand-drawn diagrams,
`rd-*` for the radar, `sw-*` for the SHAP ridges, all defined at the bottom of `index.css`. They
stay sharp at any zoom and their text is selectable.

The **performance radar** selects a model with hidden radio inputs and sibling-combinator CSS, so it
needs no JavaScript. Each axis runs 0 at the center to 1 at the rim. The full metrics table sits
under it in a `<details>` element.

The **SHAP figure is a ridge plot, not a beeswarm**: each feature's distribution is drawn as a
filled ridge, which shows the same spread and direction while remaining an aggregate view.

## Data policy

**No patient-level data belongs in this repository or on this page.** Everything shown is an
aggregate, group-level summary, and no individual-level element appears anywhere on the page.

Before committing anything new, check that it contains no per-infant rows, no dates of birth or
admission, no medical record numbers, and no free-text clinical notes. Do not commit CSVs, notebooks
with cell outputs, or model files trained on and carrying raw records.

# Website License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
