# KNOWN ISSUES — Paper 4 v1.3 (manuscript V22.6)

**Status as of 2026-05-17.** This document is a self-disclosure of issues identified after the v1.3 deposit, currently being addressed in a forthcoming v1.4 substantive revision. The Kato relay-depth ladder concept and the empirical observation that the 22-row Bettencourt panel exhibits integer-H grid structure remain valid; the issues below concern *headline framing*, *empirical uniqueness claims*, and *one auxiliary simulation script*, not the core mathematical formula.

This disclosure is provided so that readers who clone the v1.3 repository can correctly interpret the headline numbers and the auxiliary scripts. The v1.4 release will fold these fixes into the paper text, the SI, and the supporting code in a single coordinated revision.

---

## 1. Headline "22/22 with zero fitted exponents" requires re-calibration

The v1.3 headline counts the 22 indicators uniformly. In fact:

- **12/22** rows have a *direct* β_obs measurement that lands at a strict-integer Kato rung.
- **5/22** rows are audit-qualified single-H closures (proxy×3 + residual×1 + reference×1).
- **5/22** rows (Tier B: Gasoline sales, Gasoline stations, AIDS deaths, Inventors, Patents Bettencourt 2007) are closed via continuous H_eff = ε⁻¹(|β_obs − 1|), which *constructively* forces β_pred = β_obs and is therefore a tautological match rather than a blind prediction.

The v1.4 revision will split-report these three tiers ("12/22 direct strict + 5/22 audit-qualified + 5/22 H_eff fit closure") and reserve the "22/22 closure" language for the union of the three operations, with the construction status of each tier explicit in both the abstract and the SI table.

## 2. Empirical uniqueness of ε(H) = 1/[H ln(2H+1)]

The v1.3 SI section S-epsilon-alternative-rejection asserts that the Kato formula attains the lowest ΔAIC and that all seven alternative state-counts fail by ΔAIC ≥ 5. This empirical-uniqueness claim does **not** reproduce on independent re-computation:

| Formula                          | CI hits / 22 | MAE    | ΔAIC vs best |
|----------------------------------|--------------|--------|--------------|
| 1/H²                             | 21/22        | 0.0250 | (best CI)    |
| 1/[H · ln(2H+3)]                 | 14/18 direct | 0.0238 | best AIC     |
| 1/[H · ln(3H+1)]                 | 19/22        | 0.0225 | within 1     |
| Kato 1/[H · ln(2H+1)]            | 19/22        | 0.0255 | within 6     |

(Both an internal sandbox replication and an external independent audit obtained these numbers.)

The **structural-axiomatic uniqueness** of the Kato form (axioms A1–A4 → minimal signed-alphabet integer extension → z(H) = 2H+1) is unchanged and remains valid in v1.3 §2.2. What does **not** hold is the empirical claim that "no alternative state-count attains comparable empirical fit". The v1.4 revision will:

- Recast the comparison as "axiom-derived minimality" rather than "lowest empirical ΔAIC".
- Acknowledge near-equivalent empirical fits from 1/H² and 1/[H · ln(3H+1)].
- Republish the SI comparison table with a reproducible script and full numerical disclosure.

## 3. Self-reported MAE / RMSE mismatch with verification script

The auxiliary verification script `scripts/paper4_numerical_verify.py`, executed against the v1.3 manuscript values, returns MAE = 0.0120 and RMSE = 0.0250, whereas the manuscript reports MAE = 0.031 and RMSE = 0.045. The 60% MAE discrepancy is too large to be attributed to rounding (the script's own caveat is that "the paper's MAE/RMSE are computed on the unrounded 95% CI midpoints").

The v1.4 revision will:

- Pin the canonical MAE/RMSE to a single deterministic script invocation.
- Separately report the strict-integer subset and the H_eff-fit subset.
- Have the script and the manuscript number agree to ≤ 1% relative error.

## 4. Poisson-binomial significance recomputation (3.6 × 10⁻¹⁵ → 2.3 × 10⁻⁸)

The v1.3 manuscript states that the exact Poisson-binomial probability for a random 22-point ladder to achieve at least 17 matches is 3.6 × 10⁻¹⁵. An independent recomputation under the natural definition (H drawn uniformly from {2..8}, branch ± with equal probability) returns 2.3 × 10⁻⁸, a 7-order-of-magnitude gap. Even at 10⁻⁸ the ladder is far above random; the *substantive* claim that the structure is non-random survives, but the specific decimal needs correction and the "random H" operational definition needs to be explicit in the SI.

The v1.4 revision will:

- Recompute the Poisson-binomial with an explicit operational definition of "random ladder".
- Distribute the recomputation script alongside the verification script.
- State the corrected order of magnitude, while keeping the substantive non-randomness conclusion.

## 5. `scripts/sim_paper4_22_22_full_impl_v3.py` integer-rung values are inconsistent with the Kato formula

The simulation script hardcodes:

```python
beta_plus  = {1: 1.000, 2: 1.311, 3: 1.171}
beta_minus = {2: 0.770, 3: 0.857}
```

These are inconsistent with the Kato formula ε(H) = 1/[H ln(2H+1)] for H = 1, H = 2−, and H = 3−:

| H, branch | sim hardcode | Kato analytical |
|-----------|--------------|-----------------|
| β+(1)     | 1.000        | **1.9102**      |
| β−(2)     | 0.770        | **0.6893**      |
| β−(3)     | 0.857        | **0.8287**      |

The β+(1) = 1.000 entry conflates the Kato β+(1) rung with the *Path 1 balanced* (σ_gc = 0, cross-branch cancellation) special case, which is a distinct framework discussed in the main paper §subsec:cross_branch_balance. The β−(2) and β−(3) entries do not correspond to either the Kato analytical values or the H_eff-fit values reported in the SI 22-row table, and their origin is unclear.

As a consequence, the script's per-row assignment table does **not** reproduce the SI Primary Panel Table (e.g., the script places Gasoline sales/stations in strict-integer H = 2 with β = 0.770, while the SI places them in the H_eff = 2.61 continuous mixture branch with β_pred = 0.790). The simulation reaches 22/22 closure by a different and *less canonical* path than the manuscript.

For the v1.3 deposit, readers who wish to reproduce the manuscript's numerical claims should use `scripts/paper4_numerical_verify.py`, which uses the analytical Kato formula directly.

The v1.4 revision will fully rewrite `sim_paper4_22_22_full_impl_v3.py` so that it (a) uses the analytical Kato formula for integer rungs, (b) follows the SI Primary Panel Table assignment logic, and (c) explicitly distinguishes Path 1 (balanced σ_gc = 0), Path 2 (continuous H_eff with Jensen convexity), and Path 2 extended (K = 2 central cluster mixture).

---

## What is **not** affected

These issues are confined to the *framing* of the empirical results, the *auxiliary* simulation script, and *one* significance recomputation. The following are **not** affected and remain valid as stated in v1.3:

- The closed-form expression β±(H) = 1 ± 1/[H ln(2H+1)] and its integer-H values (1.910 / 1.311 / 1.171 / 1.114 / 1.083 / 1.065 / 1.053 / 1.044).
- The continuous H_eff predictions for the Tier B rows (Gasoline 0.7904, AIDS 1.2300, Inventors 1.2492, Patents legacy 1.2888, GDP 1.099), all reproducible by `paper4_numerical_verify.py`.
- The integer-rung superlinear/sublinear ladder structure exhibits non-random optimisation: random H assignment achieves ≥ 17 matches with probability < 10⁻⁷ (corrected from the manuscript's 10⁻¹⁵), keeping the structure-versus-random conclusion robust.
- The structural-axiomatic uniqueness derivation in §2.2 (axioms A1–A4 → minimal signed-alphabet integer extension → z(H) = 2H + 1).
- The USPTO–CBSA 2010 patent anchor β_obs = 1.298 [1.198, 1.398] and its agreement with β+(H = 2) = 1.311.
- The Jensen-convexity argument for continuous-H_eff mixtures.

---

## v1.4 timeline

The v1.4 substantive revision will fold all five issues into the manuscript body, SI, and reproducibility code. Expected timeline: **a few days to a week**. The v1.4 deposit will inherit the same concept DOI (`10.5281/zenodo.20145297`), which already auto-resolves to the latest version, so existing citations remain stable.

This `KNOWN_ISSUES.md` will remain in the repository through the v1.3 → v1.4 transition for historical transparency.

---

*Issued: 2026-05-17. Author: Shota Kato, AI&Future Co., Ltd., Tokyo. Self-disclosure based on internal sandbox replication and an external independent audit.*
