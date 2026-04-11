# UTG Quantum Interference Law Protocol

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

This note freezes the first explicit quantum-sector prediction derived from the UTG two-channel source law.

## Law

The frozen quantum-sector law is:

`stronger interference => smaller abs(dphi_pi)`

where the sector interference observable is:

`I_UTG = 2 * sqrt(p_C * p_M) * cos(Delta_phi_pi)`

with:

- `p_C = coherent / (coherent + morph)`
- `p_M = morph / (coherent + morph)`
- `Delta_phi_pi` taken from the frozen two-channel source law

The underlying state is:

`|Psi_UTG> = sqrt(p_C)|C> + exp(i Delta_phi_pi)sqrt(p_M)|M>`

## Files

- `utg_quantum_sector.py`
- `utg_quantum_interference_law_test.py`
- `utg_quantum_interference_leave_one_out.py`
- `UTG_QUANTUM_SECTOR_PROTOCOL.md`
- `utg_clean_env_replication\utg_quantum_sector.py`
- `utg_clean_env_replication\utg_quantum_interference_law_test.py`

## Event Set

The frozen unseen set is:

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

Calibration remains the frozen source-law core:

- `GW170729`
- `GW170814`
- `GW170818`

## Exact Commands

Run from the repository root and point `--data-dir` to the folder containing the GWOSC `.hdf5` files.

Primary run:

```powershell
python .\utg_quantum_interference_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

Leave-one-out robustness:

```powershell
python .\utg_quantum_interference_leave_one_out.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

Clean-copy replication:

```powershell
python .\utg_clean_env_replication\utg_quantum_interference_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

## Frozen Results

Primary law result:

- `spearman_rho = -8.956044e-01`
- `empirical_negative_correlation_p = 4.999750e-05`

Leave-one-out summary:

- worst leave-one-out:
  - `rho = -8.671329e-01`
  - `p = 3.999800e-04`
- median leave-one-out:
  - `rho = -8.881119e-01`
  - `p = 1.499925e-04`

Clean-copy replication:

- matched the primary result exactly
  - `rho = -8.956044e-01`
  - `p = 4.999750e-05`

## Claim Boundary

This is not a replacement for the two-channel source law.

It is a distinct quantum-sector prediction built on top of that law. It should be judged on the same standard:

- frozen form
- unseen-event validation
- leave-one-out robustness
- replication

Currently justified:

- "The UTG quantum interference law has very strong support on the frozen 13-event unseen set."
- "The quantum-sector interference observable is one of the strongest UTG predictions in the current evidence package."

Not yet justified:

- "The full quantum completion of UTG is proven."

This protocol freezes one quantum-sector law, not the entire quantum completion.
