# UTG Phase-Strength Law Protocol

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

This note freezes the current third independent UTG prediction.

## Frozen Law

\[
\text{stronger total two-channel source strength}
\Rightarrow
\text{smaller } |d\phi_{\pi}|
\]

Operationally:

\[
S_{\rm UTG}^{(2)}
=
C_{\rm coh} + \lambda_{\rm core} M_{\rm morph}
\]

with:

- `C_coh = (|Q_H1|^2 + |beta|^2 |Q_L1|^2) * C_phi_pi`
- `M_morph = residual_rms^2 * spectral_spread * envelope_roughness`
- `lambda_core` calibrated only on:
  - `GW170729`
  - `GW170814`
  - `GW170818`

Prediction:

\[
\text{higher } S_{\rm UTG}^{(2)}
\Rightarrow
\text{lower } |d\phi_{\pi}|
\]

## Frozen Scripts

Do not modify:

- `utg_cross_detector_residual_test.py`
- `utg_cross_residual_two_channel_scaling_test.py`
- `utg_phase_strength_law_test.py`
- `utg_phase_strength_leave_one_out.py`

Clean-environment replica:

- `utg_clean_env_replication\utg_phase_strength_law_test.py`

## Frozen Event Set

Broad evaluation set:

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
- `GW191109_010717`
- `GW191127_050227`
- `GW200208_130117`
- `GW200216_220804`
- `GW200220_124850`
- `GW200224_222234`
- `GW200225_060421`

Calibration-only core:

- `GW170729`
- `GW170814`
- `GW170818`

## Exact Commands

Run from the repository root and point `--data-dir` to the folder containing the GWOSC `.hdf5` files.

Primary run:

```powershell
python .\utg_phase_strength_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 GW191109_010717 GW191127_050227 GW200208_130117 GW200216_220804 GW200220_124850 GW200224_222234 GW200225_060421 --n-trials 20000
```

Leave-one-out robustness:

```powershell
python .\utg_phase_strength_leave_one_out.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 GW191109_010717 GW191127_050227 GW200208_130117 GW200216_220804 GW200220_124850 GW200224_222234 GW200225_060421 --n-trials 20000
```

Clean-environment replication:

```powershell
python .\utg_clean_env_replication\utg_phase_strength_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 GW191109_010717 GW191127_050227 GW200208_130117 GW200216_220804 GW200220_124850 GW200224_222234 GW200225_060421 --n-trials 20000
```

## Frozen Results

Primary law result:

- `spearman_rho = -5.172932e-01`
- `empirical_negative_correlation_p = 1.049948e-02`

Leave-one-out summary:

- worst leave-one-out:
  - `rho = -4.578947e-01`
  - `p = 2.664867e-02`
- median leave-one-out:
  - `rho = -5.008772e-01`
  - `p = 1.567422e-02`

Clean-environment replication:

- matched the primary result exactly
  - `rho = -5.172932e-01`
  - `p = 1.049948e-02`

## Claim Boundary

Currently justified:

- "The UTG phase-strength law has strong support on the broad 20-event set and survives leave-one-out and clean-environment replication."

Not yet justified:

- "The phase-strength law is as strongly locked as the primary two-channel source law."

That stronger claim would require better significance or outside replication.

## Disallowed Moves

Do not:

- retune `lambda_core` on evaluation events
- change the event set
- replace `|dphi_pi|` with another target
- replace the two-channel total source definition

If any of those change, it is no longer this frozen third-law protocol.
