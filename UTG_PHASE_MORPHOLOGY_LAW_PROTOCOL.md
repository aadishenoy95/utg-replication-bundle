# UTG Phase-Morphology Law Protocol

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

This note freezes the current second independent UTG prediction.

## Frozen Law

The law is:

\[
|d\phi_{\pi}|
\text{ increases with the morphology fraction of the frozen two-channel source law.}
\]

Operationally:

\[
\mathrm{morph\_frac}
=
\frac{\lambda_{\rm core}\,M_{\rm morph}}
{C_{\rm coh} + \lambda_{\rm core}\,M_{\rm morph}}
\]

where:

- `C_coh = (|Q_H1|^2 + |beta|^2 |Q_L1|^2) * C_phi_pi`
- `M_morph = residual_rms^2 * spectral_spread * envelope_roughness`
- `lambda_core` is calibrated only on:
  - `GW170729`
  - `GW170814`
  - `GW170818`

Prediction:

\[
\mathrm{higher\ morph\_frac} \Rightarrow \mathrm{larger}\ |d\phi_{\pi}|
\]

## Frozen Scripts

Do not modify:

- `utg_cross_detector_residual_test.py`
- `utg_cross_residual_two_channel_scaling_test.py`
- `utg_phase_morphology_law_test.py`
- `utg_phase_morphology_leave_one_out.py`

Clean-environment replica:

- `utg_clean_env_replication\utg_phase_morphology_law_test.py`

## Frozen Event Set

Unseen evaluation set:

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

Calibration-only core:

- `GW170729`
- `GW170814`
- `GW170818`

## Exact Commands

Run from the repository root and point `--data-dir` to the folder containing the GWOSC `.hdf5` files.

Primary run:

```powershell
python .\utg_phase_morphology_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

Leave-one-out robustness:

```powershell
python .\utg_phase_morphology_leave_one_out.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

Clean-environment replication:

```powershell
python .\utg_clean_env_replication\utg_phase_morphology_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

## Frozen Results

Primary law result:

- `spearman_rho = 6.648352e-01`
- `empirical_positive_correlation_p = 9.599520e-03`

Leave-one-out summary:

- worst leave-one-out:
  - `rho = 6.083916e-01`
  - `p = 1.849908e-02`
- median leave-one-out:
  - `rho = 6.503497e-01`
  - `p = 1.144943e-02`

Clean-environment replication:

- matched the primary result exactly
  - `rho = 6.648352e-01`
  - `p = 9.599520e-03`

## Claim Boundary

Currently justified:

- "The frozen UTG phase-morphology law has strong independent support on the 13-event unseen set."

Not yet justified:

- "The phase-morphology law is as strongly locked as the primary two-channel source law."

That stronger claim would require either better significance or more unseen-event growth.

## Disallowed Moves

Do not:

- retune `phi_*`
- retune `sigma_phi`
- retune `lambda_core` on unseen events
- change the event set
- change the morphology definition
- replace `|dphi_pi|` with another target

If any of those change, it is no longer this frozen second-law protocol.
