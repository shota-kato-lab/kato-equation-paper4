# The Kato Equation — Paper 4

> A zero-parameter exponent selection rule for urban scaling.

This repository accompanies the working paper **"The Kato Equation: A Zero-Parameter Exponent Selection Rule for Urban Scaling"** (Paper 4 of the Kato Equation Working Paper Cluster).

## Headline result

Tested against the Bettencourt et al. (PNAS 2007) 22-indicator urban panel:

- Integer relay-depth predictions match **17 of 22** reported confidence intervals.
- Network-anchored composition lifts coverage to **21 of 22**.
- A label-free **K = 2 lower-valley mixture (H ∈ {1, 2})** for physical d = 3 cities recovers **all 22 of 22** indicators with MAE = 0.031, RMSE = 0.045.

Patents land on H = 2; GDP and wages occupy an H = 4–5 corridor; infrastructure follows the negative branch.

## Repository contents

| File / folder | Content |
|---|---|
| `main.tex` | Paper 4 main manuscript |
| `SI.tex` | Supplementary Information (V71) |
| `refs.bib` | BibTeX references |
| `significance.tex` | 150-word significance statement (V2, Science Advances format) |
| `submission/cover_letter.tex` | Cover letter (V7, Science Advances tier) |
| `figures/` | Source figures (placeholder — embedded PDFs in `main.tex`) |
| `data/` | Simulation data + Bettencourt 22-indicator reference (placeholder) |
| `LICENSE` | CC-BY-4.0 (text and figures) |
| `LICENSE-CODE` | MIT (simulation / analysis code) |
| `.zenodo.json` | Zenodo deposit metadata |

## Release history

- **v1.2 (this release)** — **Closing Bettencourt's canonical 22-indicator urban panel with a zero-parameter relay-depth ladder.** Building on the seminal Bettencourt et al.~(PNAS 2007) framework, this manuscript proposes a zero-parameter Kato relay-depth ladder $\beta_\pm(H) = 1 \pm 1/[H \ln(2H+1)]$ that closes all 22 indicators at the 95% CI: 17/22 at strict integer H, 21/22 with continuous H_eff, **22/22 under a label-free K=2 lower-valley mixture protocol** (MAE = 0.031, RMSE = 0.045). Headline manuscript paired with a twelve-document cluster preview (Paper "-1" Manifesto 1 + Paper 0 Manifesto 2 + Papers 1–10) and one-click arXiv endorsement URLs for first-time submitter (physics.soc-ph + cs.AI).

  - **Hero page**: forest plot of the Bettencourt 22-indicator closure.
  - **SI Appendix S-PanelOrigins**: per-indicator panel with three coverage tiers (17 strict integer + 4 continuous H_eff + 1 K=2 cluster mixture). Reading guide formalises three non-H→∞ paths to β=1 (cross-branch σ_gc=0 / continuous H_eff Jensen / K=2 cluster integer mixture).
  - **SI Appendix S-CrossTimeBeta**: 15-row cross-time β reconstruction (hunter-gatherer band H=1 through post-human substrate H=8) with canonical β_pred values 1.311/1.171/1.114 for H=2/3/4.
  - **Bettencourt foundational reference acknowledged** with framework-specific reframe for integer-ladder testing.
  - All hyperlinks clickable (mailto, GitHub, Zenodo concept DOI, PatentsView, all bibliography DOIs via natbib auto-link).
  - Manuscript prepared through 162 iterations of careful manual revision (cluster preview / SI tables / cross-paper notation alignment / page-layout tuning) and three rounds of independent peer-style audit before release.

- v1.1 — Manuscript polish wave. Paper "-1" Manifesto 1 + Paper 0 Manifesto 2 reframe; abstract corrected to K=2 lower-valley H ∈ {1,2}; SI cross-time β table column collision fix; data and code availability section forward-looking.
- v1.0-bettencourt — Initial Bettencourt outreach deposit (manuscript V105). Concept DOI: [10.5281/zenodo.20111479](https://doi.org/10.5281/zenodo.20111479); versioned: [10.5281/zenodo.20111480](https://doi.org/10.5281/zenodo.20111480).

## Author

**Shota Kato** — Founder, AI and Future Co., Ltd. (Tokyo, Japan)

ORCID: [0009-0007-6001-3267](https://orcid.org/0009-0007-6001-3267)

## Companion papers

This is Paper 4 in the Kato Equation Working Paper Cluster (Papers 0–10 + Manifesto 1/2 forthcoming):

- Paper 1 — GDP scaling
- Paper 2 — Demographic transition
- Paper 3 — Kato Ladder & 70 ka human coordination (NHB)
- **Paper 4 — Urban scaling 22/22 (this repository)**
- Paper 5 — Civilizational ontology and dissipative cascade (Nature)

## License

- Manuscript text, figures, supplementary material: CC-BY-4.0
- Simulation and analysis code: MIT

## Citation

```
Kato, S. (2026). The Kato Equation: A Zero-Parameter Exponent Selection Rule for Urban Scaling.
Zenodo. https://doi.org/10.5281/zenodo.20111479 (concept DOI; resolves to latest version).
```
