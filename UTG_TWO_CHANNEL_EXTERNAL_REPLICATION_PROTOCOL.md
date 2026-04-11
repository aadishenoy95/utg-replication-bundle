# UTG Two-Channel External Replication Protocol

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

This note freezes the strongest current UTG source law in a form suitable for replication.

## Claim Boundary

What is frozen here is the specific two-channel UTG source law

\[
\Delta_{\rm UTG}
\sim
\underbrace{(|Q_{H1}|^2 + |\beta|^2 |Q_{L1}|^2)\,C_{\phi,\pi}}_{\text{coherent impulse channel}}
\;+\;
\lambda_{\rm core}\,
\underbrace{\left(\mathrm{residual\_rms}^2 \times \mathrm{spectral\_spread} \times \mathrm{envelope\_roughness}\right)}_{\text{broadband morphology channel}}
\]

with:

- `phi_* = 0.13566981938455774`
- `sigma_phi = 0.6`
- `lambda_core` calibrated only from:
  - `GW170729`
  - `GW170814`
  - `GW170818`

This protocol does not claim that all of UTG is proven in every possible sense. It freezes the source law that currently has the strongest unseen-event support.

## Frozen Scripts

Do not modify:

- `utg_cross_detector_residual_test.py`
- `utg_cross_residual_two_channel_scaling_test.py`
- `utg_cross_residual_two_channel_replication.py`

## File Hashes

SHA256:

- `utg_cross_detector_residual_test.py`
  - `83CC94ACDCF79DCEB3C28DED847B2632A383423174DCC492474760DCF0A6342A`
- `utg_cross_residual_two_channel_scaling_test.py`
  - `4340418CEC1D77F6B284AAF269F91B0C38F31C93136DBAB3D5E86F0149CBE91A`
- `utg_cross_residual_two_channel_replication.py`
  - `5ECA55ACCCE111F308BCDA249451BCAB9853A0A370BB46229B61BD28CC927B88`

## Frozen Event Sets

Calibration-only core:

- `GW170729`
- `GW170814`
- `GW170818`

Frozen unseen evaluation set:

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

## Exact Commands

Run from the repository root and point `--data-dir` to the folder containing the GWOSC `.hdf5` files.

Primary run:

```powershell
python .\utg_cross_residual_two_channel_scaling_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

Independent replication run:

```powershell
python .\utg_cross_residual_two_channel_replication.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

## Expected Result

Both frozen implementations should return:

- `spearman_rho = 8.736264e-01`
- `empirical_positive_correlation_p = 1.499925e-04`

Equivalent rounded summary:

- `rho ≈ 0.874`
- `p ≈ 1.50e-04`

## Interpretation

This is:

- strong unseen-event validation for the frozen two-channel law
- independent reproduction by a second implementation in the same evidence package

What is still missing for the strongest outside-world standard is:

- another analyst or team running the same frozen law and reproducing the same result

## Disallowed Moves

Do not:

- retune `phi_*`
- retune `sigma_phi`
- change the morphology channel
- change the event set
- recalibrate `lambda_core` on the unseen events
- change the residual observable
- change the permutation test definition

If any of those change, it is no longer this frozen replication protocol.
