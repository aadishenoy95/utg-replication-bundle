# Unified Temporal Gravity: A Non-Curvature Field Theory and Its Four Detector-Level Laws

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

## Abstract

Unified Temporal Gravity (UTG) is a flat-background field theory in which gravitational behavior is described by a temporal-rate scalar field and a symmetric interaction field. The theory does not use spacetime curvature, dynamical metric geometry, Einstein field equations, geodesic curvature, or emergent curvature. The scalar field determines local physical time rate, and the symmetric tensor field carries propagating interaction structure. In gravitational-wave data, these fields are accessed through detector projections. The resulting detector-pair source state separates into a coherent channel and a morphology channel. Their calibrated sum defines a total UTG source strength, while their normalized weights define a two-state sector with a phase and an interference observable. The four current UTG laws are detector-level predictions derived from this single source-state construction.

## 1. Purpose

This document states the UTG core in journal form:

```text
axioms -> fields -> action -> field equations -> measurement map -> detector variables -> four laws
```

The four laws are not presented as isolated curve fits. They are the gravitational-wave detector consequences of the same non-curvature field structure.

## 2. Core Axioms

### Axiom 1: Temporal Evolution

Every admissible physical system is defined by quantities whose states evolve with respect to an evolution parameter `t`. If `A` is a physical quantity, then on its domain of validity:

```text
A = A(t)
```

and its evolution law must be well-defined:

```text
dA/dt
```

in the classical or weak sense required by the system.

This axiom makes time evolution part of the definition of a physical system.

### Axiom 2: Valid Systems Rule

A system is physically admissible only if its fields, sources, and observables remain mathematically well-defined throughout the interval under study. For UTG this requires:

```text
Phi(x,t) > 0
```

and:

```text
sigma_ij(x,t) = sigma_ji(x,t)
```

with finite source terms, finite detector projections, and finite event-level observables.

### Axiom 3: Field Representation

Physical reality is represented by fields. UTG uses:

```text
Phi(x^mu)
```

and:

```text
sigma_ij(x^mu)
```

where:

```text
x^mu = (t, x^i)
```

`Phi` is the temporal-rate scalar field. `sigma_ij` is the symmetric interaction field.

### Axiom 4: Measurability

A quantity is physical only if it can enter a measurement map:

```text
O = M[Phi, sigma_ij, rho, T_ij]
```

where `O` is an observable and `M` is an explicitly defined measurement or detector projection.

For gravitational-wave tests, this axiom requires a map from UTG fields to detector strain and then from detector strain to event-level statistics.

## 3. Background and Notation

UTG is formulated on a fixed flat background:

```text
eta_mu_nu = diag(-1, 1, 1, 1)
```

The background is not dynamical.

The fundamental fields and sources are:

```text
Phi       = temporal-rate scalar field
sigma_ij  = symmetric interaction field
rho       = scalar source density
T_ij      = interaction source tensor
```

The theory excludes:

```text
metric curvature
dynamical spacetime geometry
Einstein field equations
geodesic curvature
emergent curvature
```

## 4. Fundamental Fields

### 4.1 Temporal-Rate Field

The temporal-rate field satisfies:

```text
Phi(x^mu) > 0
```

and defines physical time increment:

```text
d tau = Phi(x) dt
```

Thus `Phi` controls local time rate.

### 4.2 Interaction Field

The interaction field satisfies:

```text
sigma_ij = sigma_ji
```

and carries propagating interaction degrees of freedom. It is an independent field on the flat background.

## 5. Action

The UTG action is:

```text
S = integral d^4x L
```

with:

```text
L =
  1/2 partial_mu Phi partial^mu Phi
  - V(Phi)
  + 1/2 partial_mu sigma_ij partial^mu sigma_ij
  + mu_1 partial_i sigma_ij
  + mu_2 sigma_ii
  + Phi rho
  + sigma_ij T_ij
```

Here:

```text
V(Phi) = temporal-rate self-potential
mu_1   = transversality constraint multiplier
mu_2   = tracelessness constraint multiplier
```

The constraint terms select the admissible propagating sector of `sigma_ij`.

## 6. Field Equations

Variation with respect to `Phi` gives:

```text
Box Phi = dV/dPhi - rho
```

where:

```text
Box = partial_mu partial^mu
```

Variation with respect to `sigma_ij` gives:

```text
Box sigma_ij = T_ij
```

with constraints:

```text
partial_i sigma_ij = 0
```

and:

```text
sigma_ii = 0
```

so the propagating interaction equation is:

```text
Box sigma_ij = T_ij^TT
```

## 7. Weak-Field and Motion Limits

In the static source-dominated limit:

```text
nabla^2 Phi = rho
```

With:

```text
Phi = 1 + phi/c^2
```

the weak-field form is:

```text
nabla^2 phi = rho
```

The particle Lagrangian is:

```text
L_particle = 1/2 v^2 - c^2 ln Phi
```

and gives:

```text
dv^i/dt = -c^2 partial_i Phi / Phi
```

or:

```text
dv^i/dt = -c^2 partial_i ln Phi
```

The UTG signal-propagation rule used in the present formulation is:

```text
||dx/dt|| = c / Phi(x)
```

This is the flat-background temporal-rate propagation law used by the current UTG core.

## 8. Detector Projection

By the measurability axiom, the field theory must be connected to measured detector channels. For detector `a`:

```text
h_a(t) = P_a[Phi, sigma_ij](t) + n_a(t)
```

where:

```text
P_a    = detector response functional
n_a(t) = detector noise
```

For a two-detector event:

```text
H_e(t) = h_H1(t)
```

and:

```text
L_e(t) = h_L1(t)
```

The detector-coupled residual is:

```text
R_e(t; beta) = H_e(t) - beta L_e(t)
```

After whitening:

```text
R_e^W(t; beta) = W[H_e](t) - beta W[L_e](t)
```

The measured UTG residual strength is:

```text
Delta_e = max_beta,tau,window |<R_e^W, T_tau>|^2
```

where `T_tau` is the frozen temporal-tail template.

## 9. Event-Level Source State

The detector-pair event is represented by two measured channels.

### 9.1 Coherent Channel

Let `Q_H` and `Q_L` be the complex impulse statistics in H1 and L1. The phase mismatch is:

```text
Delta_phi_pi = wrap_pi[(arg Q_H - beta arg Q_L) - phi_*]
```

with:

```text
phi_* = 0.13566981938455774
```

The phase gate is:

```text
G_phi = exp[-(Delta_phi_pi)^2 / (2 sigma_phi^2)]
```

with:

```text
sigma_phi = 0.6
```

The coherent channel is:

```text
C_e = (|Q_H|^2 + |beta|^2 |Q_L|^2) G_phi
```

### 9.2 Morphology Channel

The morphology channel is:

```text
M_e = residual_rms^2 * spectral_spread * envelope_roughness
```

with:

```text
residual_rms^2 = mean[(R_e^W)^2]
```

```text
spectral_spread =
sqrt[ sum_f (f - f_centroid)^2 P(f) / sum_f P(f) ]
```

```text
f_centroid = sum_f f P(f) / sum_f P(f)
```

and:

```text
envelope_roughness = integral |d^2 E(t)/dt^2| dt
```

where:

```text
E(t) = |Hilbert[R_e^W(t; beta)]|
```

### 9.3 Total Source Strength

The scale conversion between channels is fixed by the calibration core:

```text
lambda_core = median(C_core) / median(M_core)
```

The total event source strength is:

```text
S_e = C_e + lambda_core M_e
```

### 9.4 Normalized Source Sector

Define:

```text
p_C = C_e / S_e
```

and:

```text
p_M = lambda_core M_e / S_e
```

so:

```text
p_C + p_M = 1
```

The event-level UTG sector state is:

```text
|Psi_UTG,e> = sqrt(p_C)|C> + exp(i Delta_phi_pi) sqrt(p_M)|M>
```

The interference observable is:

```text
I_e = 2 sqrt(p_C p_M) cos(Delta_phi_pi)
```

## 10. Four Detector-Level Laws

The four UTG laws are the observational predictions of the event-level source state.

### Law 1: Two-Channel Source Law

Since `Delta_e` and `S_e` are both detector-level projections of the same event source structure, UTG predicts:

```text
higher S_e -> higher Delta_e
```

Observed frozen result:

```text
rho = 8.736264e-01
p   = 1.499925e-04
```

### Law 2: Phase-Morphology Law

Since morphology fraction measures how much of the source state is carried by the morphology channel:

```text
p_M = lambda_core M_e / S_e
```

UTG predicts:

```text
higher p_M -> larger |Delta_phi_pi|
```

Observed frozen result:

```text
rho = 6.648352e-01
p   = 9.599520e-03
```

### Law 3: Phase-Strength Law

Since stronger total source states have stronger phase-stabilized coherent contribution, UTG predicts:

```text
higher S_e -> smaller |Delta_phi_pi|
```

Observed frozen result:

```text
rho = -5.172932e-01
p   = 1.049948e-02
```

### Law 4: Quantum-Sector Interference Law

Since:

```text
I_e = 2 sqrt(p_C p_M) cos(Delta_phi_pi)
```

is largest when the sector is phase-aligned, UTG predicts:

```text
higher I_e -> smaller |Delta_phi_pi|
```

Observed frozen result:

```text
rho = -8.956044e-01
p   = 4.999750e-05
```

## 11. Summary of the Theory Chain

The complete chain is:

```text
Phi, sigma_ij
-> detector projection h_a(t)
-> detector-pair residual R_e
-> residual strength Delta_e
-> coherent channel C_e
-> morphology channel M_e
-> source strength S_e
-> phase mismatch Delta_phi_pi
-> normalized weights p_C, p_M
-> sector state |Psi_UTG,e>
-> interference I_e
-> four laws
```

This is the present mathematical identity of UTG.

## 12. Final Statement

UTG is a flat-background temporal-rate and interaction-field theory. Its fundamental equations are:

```text
Box Phi = dV/dPhi - rho
```

and:

```text
Box sigma_ij = T_ij^TT
```

Its gravitational-wave predictions arise after detector projection and source-state decomposition. The four confirmed laws are the current measured consequences of that structure.
