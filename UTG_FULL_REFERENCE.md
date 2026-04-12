# UTG Full Reference

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

This file is the single-file UTG reference. It is meant to collect the main definitions, equations, frozen laws, event sets, expected outputs, and claim boundaries in one place.

## 1. What UTG Is

UTG is a proposed framework that tries to connect:

- gravity-side signal behavior
- temporal or phase structure in the signal
- a quantum-sector layer built on top of the same frozen source law

The current public UTG package is a frozen evidence package. It does not claim to be a full textbook treatment of the theory. What it provides is a set of explicit laws that can be rerun, criticized, or broken.

## 2. What The Current Package Actually Reproduces

The current package reproduces:

- fixed code
- fixed event sets
- fixed target observables
- fixed expected outputs for the current laws

So when someone reruns the package, they are checking whether the same frozen laws produce the same frozen numerical results.

## 3. Main Definitions

### 3.1 Coherent channel

The coherent channel is the part of the UTG source law that depends on a phase-gated impulse-like signal shared across the detector pair. In the current code it is built from the complex impulse measures `Q_H1` and `Q_L1`, together with a phase gate `C_phi_pi`.

### 3.2 Morphology channel

The morphology channel is the part of the source law that tracks broader residual structure rather than only sharp coherent impulse content. In the current implementation it is built from:

- residual RMS
- spectral spread
- envelope roughness

### 3.3 Phase-bearing temporal sector

This means that the relevant residual structure is not treated as only a magnitude. It also carries phase structure, which is why variables such as `dphi_pi` appear in later laws.

### 3.4 `dphi_pi`

`dphi_pi` is the wrapped phase mismatch variable used in the frozen laws. It is one of the key temporal variables that later UTG laws try to predict.

### 3.5 `p_C` and `p_M`

These are the normalized coherent and morphology weights:

- `p_C` measures how much of the total frozen source strength is attributed to the coherent channel
- `p_M` measures how much is attributed to the morphology channel

By construction, they sum to 1 within the current two-channel source law.

### 3.6 Quantum-sector state

The current quantum-sector layer uses the effective two-state form

`|Psi_UTG> = sqrt(p_C)|C> + exp(i Delta_phi_pi)sqrt(p_M)|M>`

This is not presented as the full quantum completion of UTG. It is a frozen two-state construction built on top of the frozen source law.

## 4. Core Frozen Quantities

### 4.1 Two-channel source law

The strongest current UTG source law is

\[
\Delta_{\rm UTG}
\sim
\underbrace{(|Q_{H1}|^2 + |\beta|^2 |Q_{L1}|^2)\,C_{\phi,\pi}}_{\text{coherent impulse channel}}
\;+\;
\lambda_{\rm core}\,
\underbrace{\left(\mathrm{residual\_rms}^2 \times \mathrm{spectral\_spread} \times \mathrm{envelope\_roughness}\right)}_{\text{broadband morphology channel}}
\]

with frozen constants:

- `phi_* = 0.13566981938455774`
- `sigma_phi = 0.6`

and `lambda_core` calibrated only from:

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
C_{\rm coh} = (|Q_{H1}|^2 + |beta|^2 |Q_{L1}|^2)\,C_{\phi,\pi}
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

with

\[
p_C = \frac{\mathrm{coherent}}{\mathrm{coherent} + \mathrm{morph}}
\qquad
p_M = \frac{\mathrm{morph}}{\mathrm{coherent} + \mathrm{morph}}
\]

## 5. The Four Frozen Laws

### Law 1. Two-Channel Source Law

Prediction:

`Delta_UTG ~ coherent_channel + lambda_core * morphology_channel`

Meaning:

- stronger combined coherent-plus-morphology source strength should track larger observed signal ranking

### Law 2. Phase-Morphology Law

Prediction:

\[
\mathrm{higher\ morph\_frac} \Rightarrow \mathrm{larger}\ |d\phi_{\pi}|
\]

Meaning:

- events with stronger morphology fraction should show larger phase mismatch magnitude

### Law 3. Phase-Strength Law

Prediction:

\[
\text{higher } S_{\rm UTG}^{(2)} \Rightarrow \text{lower } |d\phi_{\pi}|
\]

Meaning:

- events with stronger total frozen source strength should show smaller phase mismatch magnitude

### Law 4. Quantum Interference Law

Prediction:

`stronger interference => smaller abs(dphi_pi)`

Meaning:

- larger quantum-sector interference should track smaller phase mismatch magnitude

## 6. Frozen Event Sets

### 6.1 Calibration-only core

- `GW170729`
- `GW170814`
- `GW170818`

### 6.2 Frozen unseen set used by Laws 1, 2, and 4

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

### 6.3 Broader evaluation set used by Law 3

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

## 7. Frozen Results

### Law 1. Two-Channel Source Law

- `spearman_rho = 8.736264e-01`
- `empirical_positive_correlation_p = 1.499925e-04`

Robustness:

- leave-one-out worst `p = 6.499675e-04`
- hostile outsider audit passed
- separate-environment replication matched

### Law 2. Phase-Morphology Law

- `spearman_rho = 6.648352e-01`
- `empirical_positive_correlation_p = 9.599520e-03`

Robustness:

- worst leave-one-out `p = 1.849908e-02`
- clean-environment replication matched
- separate-environment replication matched

### Law 3. Phase-Strength Law

- `spearman_rho = -5.172932e-01`
- `empirical_negative_correlation_p = 1.049948e-02`

Robustness:

- worst leave-one-out `p = 2.664867e-02`
- clean-environment replication matched
- separate-environment replication matched

### Law 4. Quantum Interference Law

- `spearman_rho = -8.956044e-01`
- `empirical_negative_correlation_p = 4.999750e-05`

Robustness:

- worst leave-one-out `p = 3.999800e-04`
- clean-environment replication matched
- separate-environment replication matched

## 8. What Has Replicated

The current UTG package has been rerun through:

- frozen in-workflow reruns
- clean-environment replications
- blind-bundle replication for the first law
- separate-environment replication of the 4-law bundle

## 9. What Is Still Missing

The strongest outside-world standard is still missing:

- replication by a different human analyst or team

So the current package is best understood as:

- a reproducible frozen evidence package
- not yet the final social proof of the whole theory

## 10. Claim Boundary

What is justified from the current evidence:

- the two-channel source law is strongly supported and has survived the heaviest internal pressure
- the phase-morphology law is strongly supported
- the phase-strength law is strongly supported
- the quantum interference law is very strongly supported
- UTG currently has gravity-side, temporal, and quantum-sector support within one consistent evidence package

What is not yet justified:

- that UTG has already achieved full outside-world acceptance
- that the full quantum completion of UTG is proven
- that analyst-independence has already been established

## 11. Fast Reproduction Entry Points

Run from the repository root and point `--data-dir` to the folder containing the GWOSC `.hdf5` files.

### Law 1

```powershell
python .\utg_cross_residual_two_channel_scaling_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

### Law 2

```powershell
python .\utg_phase_morphology_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

### Law 3

```powershell
python .\utg_phase_strength_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 GW191109_010717 GW191127_050227 GW200208_130117 GW200216_220804 GW200220_124850 GW200224_222234 GW200225_060421 --n-trials 20000
```

### Law 4

```powershell
python .\utg_quantum_interference_law_test.py --data-dir "<path-to-gwosc-data>" --events GW150914 GW151226 GW170104 GW170608 GW170823 GW200129_065458 GW200128_022011 GW200209_085452 GW200210_092254 GW200311_115853 GW200219_094415 GW200316_215756 GW200220_061928 --n-trials 20000
```

## 12. Where To Start

If someone is new to UTG, the recommended reading order is:

1. `UTG_FULL_REFERENCE.md`
2. `UTG_ONE_PAGE.md`
3. `UTG_EXECUTIVE_SUMMARY.md`
4. `UTG_OUTSIDER_AUDIT.md`
5. `utg_external_replication_bundle.zip`
