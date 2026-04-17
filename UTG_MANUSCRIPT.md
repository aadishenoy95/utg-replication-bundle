# UTG: Hypothesis and Frozen Validation Results

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

## Abstract

UTG is a proposed physics framework intended to connect three layers of the same signal analysis problem: gravity-side residual behavior, temporal phase structure, and a quantum-sector layer built on top of a frozen source decomposition. The current public UTG package is a replication bundle, not a completed theory paper. It contains explicit definitions, frozen event sets, and fixed numerical outputs.

The main testable hypothesis is that a two-channel source law, built from a coherent impulse channel plus a morphology channel, reproduces the observed ranking of GW events better than simpler alternatives and remains stable under unseen-event validation and replication. In the current frozen package, that hypothesis is supported by `rho = 8.736264e-01` and `p = 1.499925e-04` on the primary unseen set. Three additional laws derived from the same frozen source structure also survive frozen validation.

## Plain Hypothesis

The hypothesis is:

`A frozen two-channel law trained on a small core set of GW events should keep predicting the same ranking and phase structure on unseen GW events better than simpler alternatives.`

Everything else in this package exists to test that statement.

## 1. Hypothesis

The UTG hypothesis being tested is:

`A frozen two-channel source law, together with derived phase and interference relations, should reproduce a stable pattern in GW event data under unseen validation and replication.`

In shorter form:

- there is a coherent channel
- there is a morphology channel
- the combined source law should rank events in a repeatable way
- later temporal and quantum-sector observables should also follow from that same source structure

## 2. What Is Being Tested

This package tests whether the following frozen relationships hold on fixed GW event sets:

1. Two-channel source law
2. Phase-morphology law
3. Phase-strength law
4. Quantum interference law

The package does not claim that a code run alone proves a final theory. It asks whether the same frozen structure survives unseen-event validation, robustness checks, and replication.

## 3. Main Definitions

### 3.1 Coherent channel

The coherent channel is the phase-gated impulse-like part of the source law. In the current implementation it is built from the complex impulse measures `Q_H1` and `Q_L1`, together with a phase gate `C_phi_pi`.

### 3.2 Morphology channel

The morphology channel tracks broader residual structure rather than only sharp coherent impulse content. In the current implementation it is built from:

- residual RMS
- spectral spread
- envelope roughness

### 3.3 Phase mismatch

`dphi_pi` is the wrapped phase mismatch variable used in the later laws.

### 3.4 Source weights

- `p_C` is the normalized coherent weight
- `p_M` is the normalized morphology weight

They sum to 1 within the current two-channel construction.

### 3.5 Quantum-sector state

The quantum-sector layer uses the effective two-state form:

`|Psi_UTG> = sqrt(p_C)|C> + exp(i Delta_phi_pi)sqrt(p_M)|M>`

This is not claimed to be the full quantum completion of UTG. It is a frozen effective construction built on top of the source law.

## 4. Frozen Equations

### 4.1 Two-channel source law

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

### 4.2 Morphology fraction

\[
\mathrm{morph\_frac}
=
\frac{\lambda_{\rm core}\,M_{\rm morph}}
{C_{\rm coh} + \lambda_{\rm core}\,M_{\rm morph}}
\]

where

\[
C_{\rm coh} = (|Q_{H1}|^2 + |\beta|^2 |Q_{L1}|^2)\,C_{\phi,\pi}
\]

and

\[
M_{\rm morph} = \mathrm{residual\_rms}^2 \times \mathrm{spectral\_spread} \times \mathrm{envelope\_roughness}
\]

### 4.3 Total two-channel source strength

\[
S_{\rm UTG}^{(2)} = C_{\rm coh} + \lambda_{\rm core} M_{\rm morph}
\]

### 4.4 Quantum interference observable

\[
I_{\rm UTG} = 2 \sqrt{p_C p_M}\cos(\Delta\phi_\pi)
\]

## 5. Data

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

### Law 1: Two-channel source law

- `rho = 8.736264e-01`
- `p = 1.499925e-04`

This is the strongest result in the current package.

### Law 2: Phase-morphology law

- `rho = 6.648352e-01`
- `p = 9.599520e-03`

### Law 3: Phase-strength law

- `rho = -5.172932e-01`
- `p = 1.049948e-02`

### Law 4: Quantum interference law

- `rho = -8.956044e-01`
- `p = 4.999750e-05`

## 7. Replication Status

The package has been checked through:

- frozen in-workflow reruns
- leave-one-out robustness
- clean-environment replication
- blind-bundle replication for the first law
- separate-environment replication of the full 4-law bundle

The strongest remaining standard that is still missing is replication by a different human analyst or team.

## 8. What This Does And Does Not Show

What it does show:

- UTG is a physics proposal with a concrete, frozen test package
- the strongest law survives several internal consistency checks
- the public package is now readable in a single reference file

What it does not show:

- final acceptance by the physics community
- complete proof of a full UTG theory
- analyst-independent external replication

## 9. Reproduction

Fastest entry points:

- `UTG_QUICKSTART_VALIDATION.md`
- `UTG_FULL_REFERENCE.md`

Main bundle:

- `utg_external_replication_bundle.zip`

## 10. Short Conclusion

UTG is not presented here as a finished theory of everything. It is presented as a frozen physics hypothesis with a reproducible evidence package. The main claim is that the frozen two-channel source law, together with its derived phase and quantum-sector relations, survives the current validation pipeline on the GW event sets used here.
