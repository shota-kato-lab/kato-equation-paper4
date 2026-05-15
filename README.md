# Paper 4 — A Relay-Depth Exponent Ladder for the Bettencourt 22-Indicator Urban-Scaling Panel

> A Zero-Fitted-Exponent Complementary Closure with Integer, Continuous, and Hybrid Assignments

This repository accompanies the working paper **"A Relay-Depth Exponent Ladder for the Bettencourt 22-Indicator Urban-Scaling Panel — A Zero-Fitted-Exponent Complementary Closure with Integer, Continuous, and Hybrid Assignments"** (Paper 4 of the Kato Relay-Depth Working Paper Series).

## Headline result

Tested against Bettencourt et al. (PNAS 2007) canonical 22-indicator urban panel, with zero fitted exponents:

- **17 of 22** rows land on a single-integer rung of the relay-depth ladder β±(H) = 1 ± 1/[H ln(2H+1)].
- **21 of 22** rows fall on a continuous H_eff reading.
- **22 of 22** rows close under a hybrid H ∈ {2, 3} cluster-mixture protocol (MAE = 0.031, RMSE = 0.045).
- Pre-registered falsifier: any drop to 21/22 or below at an audited release retires the closure.

## Repository contents

| File / folder | Content |
|---|---|
| `main.tex` | Paper 4 V206 manuscript (single-file architecture; SI Appendices S-PanelOrigins and S-CrossTimeBeta included inline) |
| `paper4_V28_refs.bib` / `refs.bib` | BibTeX references (V28: cited paper titles aligned with cluster canonical names) |
| `paper4_fig_main.png` | Figure 1: Bettencourt 22-Indicator closure forest plot |
| `fig_2_epsilon_curve.pdf` | Figure 2: ε(H) relay-depth curve |
| `significance.tex` | 150-word significance statement |
| `submission/cover_letter.tex` | Cover letter |
| `figures/` | Source figures (PNG/PDF) |
| `scripts/` | Minimal Python reproducibility bundle |
| `data/` | Placeholder (panel β_obs values hardcoded inline in `scripts/sim_paper4_22_22_full_impl_v3.py`) |
| `LICENSE` | CC-BY-4.0 (text and figures) |
| `LICENSE-CODE` | MIT (analysis / simulation code; mirrored as `scripts/LICENSE`) |
| `.zenodo.json` | Zenodo deposit metadata |

## Release history

- **v1.0 (this release; manuscript V206)** — Closing Bettencourt's canonical 22-indicator urban panel with a zero-fitted-exponent integer relay-depth ladder β±(H). Single-file source architecture (main body + SI Appendices S-PanelOrigins / S-CrossTimeBeta inline). Drucker-style framing: the 2007 panel is treated as the foundational empirical reference throughout; this manuscript is offered as a complementary refinement of that framework, not a replacement. Internal build chain V162 → V200 → V205 → V206 (paper polish iterations preserved as comment history at the top of `main.tex`). V206 = V205 + bibtex V27→V28 (cited paper titles aligned with cluster canonical names).
- v0.2-internal-polish (not deposited; manuscript V128/V129) — Internal polish wave. Pushed to GitHub as historical tag `v1.1` but no GitHub Release was published; no Zenodo deposit was minted.
- v0.1-bettencourt (withdrawn; manuscript V105) — Initial Bettencourt outreach deposit. Withdrawn 2026-05-12 once the manuscript polish gap to v1.0 was recognised. Zenodo tombstone: 10.5281/zenodo.20111480. Retired from this repository on 2026-05-13.

## Reproducibility

This v1.0 deposit includes a minimal Python reproducibility bundle in `scripts/`:

- `scripts/sim_paper4_22_22_full_impl_v3.py` — central K=2 cluster-mixture closure protocol implementation (Stages 1–3 of Results §3.5–3.6). Reproduces the 17/22 single-integer + 22/22 hybrid closure with hardcoded Bettencourt 2007 PNAS panel values; no external data fetch required. Run: `python3 sim_paper4_22_22_full_impl_v3.py` (deps: numpy, pandas, scipy).
- `scripts/paper4_numerical_verify.py` — independent re-computation of all β±(H) integer-rung values (H = 1 .. 8), the continuous β±(H_eff) values for the six mixture rows, and the MAE / RMSE on the audited 22-row slice.

The following peripheral pipelines are **deferred to a subsequent versioned release** (v1.1):

- USPTO–CBSA 2010 cross-section standalone reconstruction (Paper 4 main-text primary anchor at β_obs = 1.298 [1.198, 1.398]).
- EOC (Era of Crystallisation) audit bootstrap (n = 10 000) for the SI Appendix S-PanelOrigins window count [18, 22].

For these pipelines, the manuscript text + SI documents the methodology prose-and-equation; full simulation/audit code is available from the corresponding author upon request.

## Author

**Shota Kato** — Founder, AI and Future Co., Ltd. (Tokyo, Japan)

ORCID: [0009-0007-6001-3267](https://orcid.org/0009-0007-6001-3267)

## Citation

```
Kato, S. (2026). A Relay-Depth Exponent Ladder for the Bettencourt 22-Indicator Urban-Scaling Panel:
A Zero-Fitted-Exponent Complementary Closure with Integer, Continuous, and Hybrid Assignments.
Zenodo. https://doi.org/10.5281/zenodo.20145298 (versioned DOI).
```

## License

- Manuscript text and figures: CC-BY-4.0 (`LICENSE`).
- Reproducibility code: MIT (`LICENSE-CODE`, mirrored as `scripts/LICENSE`).
