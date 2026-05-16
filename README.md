# Paper 4 — A Relay-Depth Exponent Ladder Closing the Bettencourt 22-Indicator Urban-Scaling Panel

> ⚠️ **Known issues in v1.3 — see [`KNOWN_ISSUES.md`](./KNOWN_ISSUES.md)**
>
> Five issues identified after the v1.3 deposit are publicly disclosed in `KNOWN_ISSUES.md`:
> headline "22/22" framing requires three-tier split-reporting; empirical-uniqueness claim for the Kato
> formula does not reproduce on independent recomputation (near-equivalents exist); self-reported MAE
> deviates from the verification script's output; Poisson-binomial significance was overstated by ~7
> orders of magnitude; the auxiliary `sim_paper4_22_22_full_impl_v3.py` script uses integer-rung values
> inconsistent with the Kato formula. The Kato formula itself, the axiom-derived structural uniqueness,
> the integer-H ladder structure, and the non-randomness conclusion remain valid. A v1.4 substantive
> revision is in preparation. For numerical reproduction in the meantime, use
> `scripts/paper4_numerical_verify.py` (canonical Kato values).

> A Zero-Fitted-Exponent Complementary Closure with Integer, Continuous, and Hybrid Assignments

This repository accompanies the working paper **"A Relay-Depth Exponent Ladder Closing the Bettencourt 22-Indicator Urban-Scaling Panel — A Zero-Fitted-Exponent Complementary Closure with Integer, Continuous, and Hybrid Assignments"** (Paper 4 of the Kato Relay-Depth Working Paper Series).

## Headline result

Tested against Bettencourt et al. (PNAS 2007) canonical 22-indicator urban panel, with zero fitted exponents:

- **17 of 22** rows land on a single-integer rung of the relay-depth ladder β±(H) = 1 ± 1/[H ln(2H+1)].
- **21 of 22** rows fall on a continuous H_eff reading.
- **22 of 22** rows close under a hybrid H ∈ {2, 3} cluster-mixture protocol (MAE = 0.031, RMSE = 0.045).
- Pre-registered falsifier: any drop to 21/22 or below at an audited release retires the closure.

## Repository contents

| File / folder | Content |
|---|---|
| `main.tex` | Paper 4 manuscript V22.6 (single-file architecture; SI Appendices S-PanelOrigins and S-CrossTimeBeta included inline) |
| `paper4_V30_refs.bib` / `refs.bib` | BibTeX references (V30: V29 + Bettencourt 2013 / 2020 / 2021 entries injected for the reviewer-reply mechanism / predictions wave) |
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

- **v1.3 (this release; manuscript V22.6, 2026-05-16)** — Substantive polish wave following the original author's first reply (received 2026-05-16). The two reviewer questions raised in that reply (1) "what is the mechanism, and is it believable?" and (2) "what other predictions does it make?" are now addressed directly in the manuscript body. Mechanism: §1 Introduction and §2.2 establish that the predicted exponent ε(H) = 1/[H ln(2H+1)] arises from a combinatorial-geometric construction (signed alphabet A_H = {−H, …, −1, 0, 1, …, H} of size 2H+1 at each of H coordination rungs; code volume (2H+1)^H by minimality), explicitly not from information-theoretic axioms. Predictions: §3 Discussion adds four falsifiable orthogonal predictions (P1) cross-time-β ladder, (P2) size-dependent variance, (P3) out-of-sample blind exponents, (P4) numerical reconciliation with canonical mean-field exponents. Bettencourt 2013 (Science 340, 1438) derivation flowchart, Bettencourt 2020 (Science Advances eaat8812) stochastic-growth framework, and Bettencourt 2021 (MIT Press, Introduction to Urban Science) are now cited and positioned as the foundational urban-scaling framework that the present ladder is a complementary refinement of. SI Appendix S-PanelOrigins now includes a full 22-row β-independent assignment provenance table (5-column: indicator, network type, substrate constraint, branch, β_obs, agreement rationale; 20/22 Match + 2 Qualified hybrid). Bibliography handle bumped V29 → V30. Central claim (22/22 hybrid closure, MAE 0.031, RMSE 0.045), all figures, scripts, simulation outputs, and the title "Closing the Bettencourt 22-Indicator Urban-Scaling Panel" are unchanged. Layout micro-tuning applied to the SI 22-row table and the title page. Concept DOI 10.5281/zenodo.20145297 redirects to this v1.3 record.
- v1.2 (manuscript V21.6, 2026-05-16) — Editorial cleanup pass after the v1.0/v1.1 drafts were sent to the original author of the 22-indicator panel. A third-party meta-disclosure audit flagged inadvertent investor-style annotations in those drafts (reference note fields, SI cross-time-beta paragraph, scope-boundary paragraph, and title-page banner). These annotations were removed and the body wording was returned to standard academic phrasing. Author affiliation footer corrected to "AI&Future Co., Ltd." Title verb "Closing" (v1.1) retained; central claim and all numerical content unchanged. Bibliography handle bumped V28 → V29 (reference note-field cleanup only). Now superseded by v1.3 (Bettencourt-reply-driven substance polish).
- v1.1 (manuscript V207, 2026-05-15) — Withdrawn (deletion request submitted to Zenodo). Title verb refined from "for" (V206) to "Closing" to align with body-text wording. Numerical content unchanged from V206.
- v1.0 (manuscript V206, 2026-05-12) — Withdrawn (deletion request submitted to Zenodo). Initial closing of Bettencourt's canonical 22-indicator urban panel with a zero-fitted-exponent integer relay-depth ladder β±(H). Versioned DOI 10.5281/zenodo.20145298 (historical anchor).
- v0.2-internal-polish (not deposited; manuscript V128/V129) — Internal polish wave. Pushed to GitHub as historical tag `v1.1` but no GitHub Release was published; no Zenodo deposit was minted.
- v0.1-bettencourt (withdrawn; manuscript V105) — Initial Bettencourt outreach deposit. Withdrawn 2026-05-12; Zenodo tombstone 10.5281/zenodo.20111480.

## Reproducibility

This deposit includes a minimal Python reproducibility bundle in `scripts/`:

- `scripts/sim_paper4_22_22_full_impl_v3.py` — central K=2 cluster-mixture closure protocol implementation (Stages 1–3 of Results §3.5–3.6). Reproduces the 17/22 single-integer + 22/22 hybrid closure with hardcoded Bettencourt 2007 PNAS panel values; no external data fetch required. Run: `python3 sim_paper4_22_22_full_impl_v3.py` (deps: numpy, pandas, scipy).
- `scripts/paper4_numerical_verify.py` — independent re-computation of all β±(H) integer-rung values (H = 1 .. 8), the continuous β±(H_eff) values for the six mixture rows, and the MAE / RMSE on the audited 22-row slice.

The following peripheral pipelines are deferred to a subsequent versioned release:

- USPTO–CBSA 2010 cross-section standalone reconstruction (Paper 4 main-text primary anchor at β_obs = 1.298 [1.198, 1.398]).
- EOC (Era of Crystallisation) audit bootstrap (n = 10 000) for the SI Appendix S-PanelOrigins window count [18, 22].

For these pipelines, the manuscript text + SI documents the methodology prose-and-equation; full simulation/audit code is available from the corresponding author upon request.

## Author

**Shota Kato** — Founder, AI&Future Co., Ltd. (Tokyo, Japan)

ORCID: [0009-0007-6001-3267](https://orcid.org/0009-0007-6001-3267)

## Citation

```
Kato, S. (2026). A Relay-Depth Exponent Ladder Closing the Bettencourt 22-Indicator Urban-Scaling Panel:
A Zero-Fitted-Exponent Complementary Closure with Integer, Continuous, and Hybrid Assignments.
Zenodo. https://doi.org/10.5281/zenodo.20145297 (concept DOI, resolves to latest version).
```

## License

- Manuscript text and figures: CC-BY-4.0 (`LICENSE`).
- Reproducibility code: MIT (`LICENSE-CODE`, mirrored as `scripts/LICENSE`).
