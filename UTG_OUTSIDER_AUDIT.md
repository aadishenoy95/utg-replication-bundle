# UTG Outsider Audit

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

This note records a skeptical check of the strongest frozen UTG law.

The audit standard used here was:

1. reproduce the frozen result in a separate environment
2. attack the law with hostile robustness checks
3. compare the law against simpler non-UTG baselines on the same frozen event set

## Scope

This audit focuses on the first and strongest UTG law:

\[
\Delta_{\rm UTG}
\sim
(|Q_{H1}|^2 + |\beta|^2 |Q_{L1}|^2)\,C_{\phi,\pi}
\;+\;
\lambda_{\rm core}\,
(\mathrm{residual\_rms}^2 \times \mathrm{spectral\_spread} \times \mathrm{envelope\_roughness})
\]

with frozen calibration on:

- `GW170729`
- `GW170814`
- `GW170818`

and frozen unseen evaluation on:

- `GW150914`
- `GW151226`
- `GW170104`
- `GW170608`
- `GW170823`
- `GW200129_065458`
- `GW200128_022011`
- `GW200209_085452`
- `GW200210_092254`
- `GW200311_115853`
- `GW200219_094415`
- `GW200316_215756`
- `GW200220_061928`

## 1. Reproduction

The full frozen 4-law bundle was reproduced in a separate local environment using:

- `utg_external_replication_bundle/RUN_ALL_UTG_LAWS.ps1`
- `utg_external_replication_bundle.zip`

For the first law, the separate-environment reproduction matched exactly:

- `rho = 8.736264e-01`
- `p = 1.499925e-04`

## 2. Attack

The hostile robustness battery was run with:

- `utg_first_law_hostile_robustness.py`

Results:

- full set:
  - `rho = 8.736264e-01`
  - `p = 1.499925e-04`
- leave-one-era-out:
  - drop `O1`: `rho = 8.636364e-01`, `p = 8.499575e-04`
  - drop `O2`: `rho = 9.030303e-01`, `p = 5.499725e-04`
  - drop `O3`: `rho = 1.000000e+00`, `p = 7.349633e-03`
- bootstrap over event resampling:
  - `q05(rho) = 6.296296e-01`
  - `q50(rho) = 8.666667e-01`
  - `q95(rho) = 9.831933e-01`
  - `P(rho > 0) = 0.999700`
  - `P(rho > 0.5) = 0.983500`
  - `P(rho > 0.7) = 0.902000`

Interpretation:

- the law does not collapse when an observing era is removed
- the positive correlation is not being carried by one narrow bootstrap corner
- the law remains strong under hostile resampling pressure

## 3. Compare

The first law was compared against simpler baselines built from the same frozen event rows:

- coherent-only predictor
- morphology-only predictor
- equal-weight sum of coherent and morphology channels

Using the same permutation test definition:

- coherent-only:
  - `rho = 7.857143e-01`
  - `p = 1.249938e-03`
- morphology-only:
  - `rho = 8.296703e-01`
  - `p = 5.499725e-04`
- equal-weight sum:
  - `rho = 8.296703e-01`
  - `p = 5.499725e-04`
- frozen UTG two-channel law:
  - `rho = 8.736264e-01`
  - `p = 1.499925e-04`

Interpretation:

- the frozen UTG law beats each simpler baseline on the same data
- the two-channel structure is not just cosmetic; it improves the fit beyond either single channel alone

## Outsider Verdict

From a skeptical standpoint, the strongest frozen UTG law passes a serious internal stress test:

- it reproduces in a separate environment
- it survives hostile robustness checks
- it outperforms simpler non-UTG baselines on the same frozen unseen set

The strongest remaining caveat is analyst independence:

- the same operator developed and audited the theory
- there is still no different-human-analyst replication
- the law was not pre-registered before any data contact

So the honest outsider conclusion is:

- the first UTG law is hard to dismiss as a simple machine artifact or trivial one-channel fit
- the remaining attack surface is mainly analyst independence and outside scrutiny, not an obvious local failure of the frozen law itself
