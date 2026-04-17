# UTG: A Frozen Replication Package for Gravity, Temporal Structure, and Quantum-Sector Behavior

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

## Abstract

UTG is a proposed framework that tries to connect gravity-side signal behavior, temporal phase structure, and a quantum-sector layer built from the same source decomposition. The current public UTG package is not a full textbook presentation of the theory. It is a frozen replication package containing explicit laws, fixed event sets, and fixed expected outputs.

The strongest current UTG result is a two-channel source law with a frozen unseen-set correlation of `rho = 8.736264e-01` and `p = 1.499925e-04`. This law survives leave-one-out checks, hostile robustness testing, and separate-environment replication. Three additional derived laws also survive frozen validation: a phase-morphology law, a phase-strength law, and a quantum interference law. The package is public, citable, and designed for reproduction or hostile audit.

## 1. Motivation

The aim of UTG is not to claim that a single code run proves a new theory. The aim is narrower and more testable:

- freeze one source law
- freeze the event sets
- freeze the observables
- see whether the same structure keeps appearing under unseen validation and replication

That makes the package closer to a scientific testbed than a finished theory statement.

## 2. Core Definitions

### 2.1 Coherent channel

The coherent channel is the phase-gated impulse-like component of the source law. In the current implementation it is built from the complex impulse measures `Q_H1` and `Q_L1` and a phase gate `C_phi_pi`.

### 2.2 Morphology channel

The morphology channel tracks broader residual structure. In the current implementation it is built from:

- residual RMS
- spectral spread
- envelope roughness

### 2.3 Phase-bearing temporal sector

This means the relevant residual structure is not treated as a magnitude only. It also carries phase structure, which is why `dphi_pi` appears in later laws.

### 2.4 Quantum-sector state

The current quantum-sector layer uses the effective two-state form

`|Psi_UTG> = sqrt(p_C)|C> + exp(i Delta_phi_pi)sqrt(p_M)|M>`

where `p_C` and `p_M` are the normalized coherent and morphology weights induced by the frozen source law.

## 3. Frozen Source Law

The strongest current UTG law is:

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
- `lambda_core` calibrated only on:
  - `GW170729`
  - `GW170814`
  - `GW170818`

This law is the basis for the remaining derived predictions.

## 4. Derived Predictions

### 4.1 Phase-morphology law

Prediction:

\[
\mathrm{higher\ morph\_frac} \Rightarrow \mathrm{larger}\ |d\phi_{\pi}|
\]

Operationally:

\[
\mathrm{morph\_frac}
=
\frac{\lambda_{\rm core}\,M_{\rm morph}}
{C_{\rm coh} + \lambda_{\rm core}\,M_{\rm morph}}
\]

with

\[
C_{\rm coh} = (|Q_{H1}|^2 + |\beta|^2 |Q_{L1}|^2)\,C_{\phi,\pi}
\]

and

\[
M_{\rm morph} = \mathrm{residual\_rms}^2 \times \mathrm{spectral\_spread} \times \mathrm{envelope\_roughness}
\]

Frozen result:

- `rho = 6.648352e-01`
- `p = 9.599520e-03`

### 4.2 Phase-strength law

Prediction:

\[
\text{higher } S_{\rm UTG}^{(2)} \Rightarrow \text{lower } |d\phi_{\pi}|
\]

where

\[
S_{\rm UTG}^{(2)} = C_{\rm coh} + \lambda_{\rm core} M_{\rm morph}
\]

Frozen result:

- `rho = -5.172932e-01`
- `p = 1.049948e-02`

### 4.3 Quantum interference law

Prediction:

`stronger interference => smaller abs(dphi_pi)`

with

\[
I_{\rm UTG} = 2 \sqrt{p_C p_M}\cos(\Delta\phi_\pi)
\]

Frozen result:

- `rho = -8.956044e-01`
- `p = 4.999750e-05`

## 5. Data and Event Sets

### Calibration core

- `GW170729`
- `GW170814`
- `GW170818`

### Frozen unseen set

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

### Broader evaluation set

- `GW191109_010717`
- `GW191127_050227`
- `GW200208_130117`
- `GW200216_220804`
- `GW200220_124850`
- `GW200224_222234`
- `GW200225_060421`

## 6. Results

### 6.1 Two-channel source law

- `rho = 8.736264e-01`
- `p = 1.499925e-04`

Robustness:

- leave-one-out worst `p = 6.499675e-04`
- separate-environment replication matched
- hostile outsider audit passed

### 6.2 Phase-morphology law

- `rho = 6.648352e-01`
- `p = 9.599520e-03`

Robustness:

- worst leave-one-out `p = 1.849908e-02`
- clean-environment replication matched

### 6.3 Phase-strength law

- `rho = -5.172932e-01`
- `p = 1.049948e-02`

Robustness:

- worst leave-one-out `p = 2.664867e-02`
- clean-environment replication matched

### 6.4 Quantum interference law

- `rho = -8.956044e-01`
- `p = 4.999750e-05`

Robustness:

- worst leave-one-out `p = 3.999800e-04`
- clean-environment replication matched

## 7. Replication Status

The package has been checked through:

- frozen in-workflow reruns
- clean-environment replications
- blind-bundle replication for the first law
- separate-environment replication of the full 4-law bundle

What is still missing for the strongest outside-world standard:

- replication by a different human analyst or team

## 8. Interpretation

The strongest reading that is still honest is:

- UTG now has a frozen evidence package with four successful predictions
- the first law is the strongest and most robust result
- the later laws are derived from the same frozen source structure
- the package is reproducible enough to invite hostile audit

What should not be claimed yet:

- that UTG is automatically accepted by the wider physics community
- that the theory is fully complete
- that analyst-independence has already been established

## 9. Reproduction

The fastest public entry point is:

`UTG_QUICKSTART_VALIDATION.md`

The most complete overview is:

`UTG_FULL_REFERENCE.md`

The main bundle is:

`utg_external_replication_bundle.zip`

## 10. Conclusion

UTG is best understood today as a frozen replication package with four successful laws and a clear boundary on what has and has not yet been established. The strongest current task is not to keep changing the laws. It is to keep the package clean enough that another person can actually rerun it and decide for themselves.
