# UTG Master Summary

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

This is the top-level summary of the current state of the UTG framework.

## Core Idea

UTG is a unification framework for:

- gravity
- temporal structure
- quantum-sector behavior

The current evidence base is organized around frozen laws, each with:

- a fixed functional form
- a fixed event set
- unseen-event validation
- robustness checks
- replication-style reruns

## Current Status

Within the current evidence package:

- frozen successful predictions: `4`

Broader outside-world recognition still requires outside analyst replication and community scrutiny.

Separate-environment replication has now also succeeded for the frozen 4-law bundle on a different local environment, reproducing the same headline outputs.

## Confirmed Laws

### 1. Two-Channel Source Law

Protocol:

- `UTG_TWO_CHANNEL_EXTERNAL_REPLICATION_PROTOCOL.md`

Law:

`Delta_UTG ~ coherent_channel + lambda_core * morphology_channel`

Main result on the frozen 13-event unseen set:

- `spearman_rho = 8.736264e-01`
- `empirical_positive_correlation_p = 1.499925e-04`

Robustness:

- leave-one-out worst `p = 6.499675e-04`
- independent in-workflow replication matched
- clean-environment replication matched
- blind bundle replication matched
- separate-environment bundle replication matched

### 2. Phase-Morphology Law

Protocol:

- `UTG_PHASE_MORPHOLOGY_LAW_PROTOCOL.md`

Law:

`higher morphology fraction => larger abs(dphi_pi)`

Main result on the frozen 13-event unseen set:

- `spearman_rho = 6.648352e-01`
- `empirical_positive_correlation_p = 9.599520e-03`

Breadth extension on the broader 20-event set:

- `spearman_rho = 5.353383e-01`
- `empirical_positive_correlation_p = 8.149593e-03`

Robustness:

- leave-one-out worst `p = 1.849908e-02`
- clean-environment replication matched
- separate-environment bundle replication matched

### 3. Phase-Strength Law

Protocol:

- `UTG_PHASE_STRENGTH_LAW_PROTOCOL.md`

Law:

`stronger total two-channel source strength => smaller abs(dphi_pi)`

Main result on the broad 20-event set:

- `spearman_rho = -5.172932e-01`
- `empirical_negative_correlation_p = 1.049948e-02`

Robustness:

- leave-one-out worst `p = 2.664867e-02`
- clean-environment replication matched
- separate-environment bundle replication matched

### 4. Quantum Interference Law

Protocol:

- `UTG_QUANTUM_INTERFERENCE_LAW_PROTOCOL.md`

Law:

`stronger interference => smaller abs(dphi_pi)`

with quantum-sector state:

`|Psi_UTG> = sqrt(p_C)|C> + exp(i Delta_phi_pi)sqrt(p_M)|M>`

Main result on the frozen 13-event unseen set:

- `spearman_rho = -8.956044e-01`
- `empirical_negative_correlation_p = 4.999750e-05`

Robustness:

- leave-one-out worst `p = 3.999800e-04`
- clean-copy replication matched exactly
- separate-environment bundle replication matched

## Key Files

Primary law and replication:

- `utg_cross_residual_two_channel_scaling_test.py`
- `utg_cross_residual_two_channel_replication.py`
- `utg_cross_residual_two_channel_leave_one_out.py`

Additional laws:

- `utg_phase_morphology_law_test.py`
- `utg_phase_morphology_leave_one_out.py`
- `utg_phase_strength_law_test.py`
- `utg_phase_strength_leave_one_out.py`
- `utg_quantum_sector.py`
- `utg_quantum_sector_scan.py`
- `utg_quantum_interference_law_test.py`
- `utg_quantum_interference_leave_one_out.py`

Replication assets:

- `utg_clean_env_replication`
- `utg_first_law_blind_bundle`
- `utg_external_replication_bundle`
- `UTG_TWO_CHANNEL_EXTERNAL_REPLICATION_PROTOCOL.md`

## Claim Boundary

What is justified from the current evidence:

- the two-channel source law is locked
- the phase-morphology law is strongly supported
- the phase-strength law is strongly supported
- the quantum interference law is very strongly supported
- UTG now has gravity, time-structure, and quantum-sector support inside one consistent program

What is not yet fully established outside the current evidence package:

- true outside-analyst replication
- broader community scrutiny
- external publication-level validation

## Practical Summary

Across the current frozen evidence package and a separate replicated local environment, UTG now stands as a serious and internally coherent theory framework with four successful frozen predictions.
