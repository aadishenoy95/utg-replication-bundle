# Unified Temporal Gravity: Mathematical Derivation of the Field Theory and Four Laws

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

## Abstract

This paper gives the derivation chain for Unified Temporal Gravity (UTG). Starting from four axioms, the theory introduces a temporal-rate scalar field and a symmetric interaction field on a fixed flat background. Variation of the UTG action gives the scalar temporal-rate equation and the transverse-traceless interaction-field equation. The same framework gives particle motion, weak-field behavior, signal propagation, and detector-level gravitational-wave observables. The four empirical UTG laws follow as measured consequences of the projected event source state.

## 1. Axiomatic Basis

### Axiom 1: Temporal Evolution

For every admissible physical quantity `A`, there exists an evolution parameter `t` such that:

```text
A = A(t)
```

and the evolution law is defined on the interval of interest.

### Axiom 2: Valid Systems Rule

A physical system is admissible only when its fields, sources, and observables remain finite and well-defined under time evolution. For UTG:

```text
Phi(x,t) > 0
```

and:

```text
sigma_ij(x,t) = sigma_ji(x,t)
```

must hold wherever the theory is applied.

### Axiom 3: Field Representation

UTG represents physical reality by fields:

```text
Phi(x^mu)
```

and:

```text
sigma_ij(x^mu)
```

with:

```text
x^mu = (t, x^i)
```

### Axiom 4: Measurability

A quantity is physical only if it enters a measurement map:

```text
O = M[Phi, sigma_ij, rho, T_ij]
```

Thus the gravitational-wave laws require a detector projection from fields to measured strain.

## 2. Fields and Background

UTG is formulated on:

```text
eta_mu_nu = diag(-1, 1, 1, 1)
```

The background is fixed and non-dynamical.

The two fundamental fields are:

```text
Phi(x^mu) > 0
```

and:

```text
sigma_ij(x^mu) = sigma_ji(x^mu)
```

The physical time definition is:

```text
d tau = Phi(x) dt
```

No curvature quantity is introduced.

## 3. Action

The UTG action is:

```text
S = integral d^4x L
```

where:

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

The source terms are:

```text
rho  = scalar source density
T_ij = interaction source tensor
```

The multipliers `mu_1` and `mu_2` impose the allowed propagation constraints.

## 4. Scalar Field Equation

The scalar-field Lagrangian is:

```text
L_Phi = 1/2 partial_mu Phi partial^mu Phi - V(Phi) + Phi rho
```

The Euler-Lagrange equation is:

```text
partial L / partial Phi
- partial_mu[partial L / partial(partial_mu Phi)] = 0
```

Compute:

```text
partial L / partial Phi = -dV/dPhi + rho
```

and:

```text
partial L / partial(partial_mu Phi) = partial^mu Phi
```

Therefore:

```text
-dV/dPhi + rho - partial_mu partial^mu Phi = 0
```

so:

```text
Box Phi = dV/dPhi - rho
```

with:

```text
Box = partial_mu partial^mu
```

This is the UTG temporal-rate equation.

## 5. Weak-Field Limit

In the static source-dominated limit:

```text
nabla^2 Phi = rho
```

Let:

```text
Phi = 1 + phi/c^2
```

Then:

```text
nabla^2 Phi = nabla^2(1 + phi/c^2)
```

Since:

```text
nabla^2 1 = 0
```

we obtain:

```text
nabla^2 Phi = (1/c^2)nabla^2 phi
```

After fixing the source normalization, the weak-field equation is:

```text
nabla^2 phi = rho
```

Thus the Newton-like scalar limit comes from `Phi`, not from curvature.

## 6. Interaction Field Equation

The interaction-field Lagrangian is:

```text
L_sigma =
  1/2 partial_mu sigma_ij partial^mu sigma_ij
  + mu_1 partial_i sigma_ij
  + mu_2 sigma_ii
  + sigma_ij T_ij
```

The Euler-Lagrange equation for `sigma_ij` gives:

```text
partial L / partial sigma_ij
- partial_mu[partial L / partial(partial_mu sigma_ij)] = 0
```

The source derivative is:

```text
partial L / partial sigma_ij = T_ij
```

up to constraint contributions.

The kinetic derivative is:

```text
partial L / partial(partial_mu sigma_ij) = partial^mu sigma_ij
```

Therefore:

```text
T_ij - Box sigma_ij = 0
```

and:

```text
Box sigma_ij = T_ij
```

The constraint variations impose:

```text
partial_i sigma_ij = 0
```

and:

```text
sigma_ii = 0
```

so the propagating equation is:

```text
Box sigma_ij = T_ij^TT
```

## 7. Particle Motion

The particle Lagrangian is:

```text
L_particle = 1/2 v^2 - c^2 ln Phi
```

The Euler-Lagrange equation is:

```text
d/dt[partial L / partial v_i] - partial L / partial x_i = 0
```

Since:

```text
partial L / partial v_i = v_i
```

we have:

```text
d/dt[partial L / partial v_i] = dv_i/dt
```

Also:

```text
partial L / partial x_i = -c^2 partial_i ln Phi
```

Therefore:

```text
dv_i/dt + c^2 partial_i ln Phi = 0
```

so:

```text
dv_i/dt = -c^2 partial_i ln Phi
```

Since:

```text
partial_i ln Phi = partial_i Phi / Phi
```

the motion law is:

```text
dv_i/dt = -c^2 partial_i Phi / Phi
```

In the weak-field limit:

```text
Phi = 1 + phi/c^2
```

and:

```text
ln Phi approximately phi/c^2
```

so:

```text
dv_i/dt approximately -partial_i phi
```

## 8. Signal Propagation

The UTG temporal-rate propagation rule used in the current theory is:

```text
||dx/dt|| = c / Phi(x)
```

This rule says that increasing temporal-rate resistance lowers coordinate signal speed on the fixed background. It is part of the UTG propagation structure and is used consistently with the field equations and detector projection.

## 9. Detector Projection

By Axiom 4, the fields must be projected to measured quantities. For detector `a`:

```text
h_a(t) = P_a[Phi, sigma_ij](t) + n_a(t)
```

For H1 and L1:

```text
H_e(t) = h_H1(t)
```

and:

```text
L_e(t) = h_L1(t)
```

The detector-pair residual is:

```text
R_e(t; beta) = H_e(t) - beta L_e(t)
```

Whitening gives:

```text
R_e^W(t; beta) = W[H_e](t) - beta W[L_e](t)
```

The measured residual strength is:

```text
Delta_e = max_beta,tau,window |<R_e^W, T_tau>|^2
```

This is the measured target used by Law 1.

## 10. Coherent Channel

Let `Q_H` and `Q_L` be complex impulse statistics from the H1 and L1 event windows.

The raw coherent detector-pair strength is:

```text
|Q_H|^2 + |beta|^2 |Q_L|^2
```

The UTG phase mismatch is:

```text
Delta_phi_pi = wrap_pi[(arg Q_H - beta arg Q_L) - phi_*]
```

where:

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

## 11. Morphology Channel

The residual morphology channel is:

```text
M_e = residual_rms^2 * spectral_spread * envelope_roughness
```

where:

```text
residual_rms^2 = mean[(R_e^W)^2]
```

The spectral centroid is:

```text
f_centroid = sum_f f P(f) / sum_f P(f)
```

The spectral spread is:

```text
spectral_spread =
sqrt[sum_f (f - f_centroid)^2 P(f) / sum_f P(f)]
```

The residual envelope is:

```text
E(t) = |Hilbert[R_e^W(t; beta)]|
```

and:

```text
envelope_roughness = integral |d^2E/dt^2| dt
```

Thus `M_e` is a measurable residual-structure statistic.

## 12. Total Source Strength

The calibration factor is:

```text
lambda_core = median(C_core) / median(M_core)
```

The total source strength is:

```text
S_e = C_e + lambda_core M_e
```

This follows from the two-channel event representation:

```text
event source = coherent contribution + calibrated morphology contribution
```

## 13. Normalized Sector and Interference

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

The UTG event sector is:

```text
|Psi_UTG,e> = sqrt(p_C)|C> + exp(i Delta_phi_pi) sqrt(p_M)|M>
```

The interference term is:

```text
I_e = 2 sqrt(p_C p_M) cos(Delta_phi_pi)
```

## 14. Derivation of Law 1

The measured residual target is:

```text
Delta_e = max_beta,tau,window |<R_e^W, T_tau>|^2
```

The UTG source strength is:

```text
S_e = C_e + lambda_core M_e
```

Both are constructed from the same detector-pair event projection. Therefore UTG predicts:

```text
S_e ranks positively with Delta_e
```

Observed frozen result:

```text
rho = 8.736264e-01
p   = 1.499925e-04
```

## 15. Derivation of Law 2

The morphology fraction is:

```text
p_M = lambda_core M_e / S_e
```

The phase mismatch is:

```text
Delta_phi_pi
```

As `p_M` increases, the event state is less dominated by the coherent phase-aligned channel. UTG therefore predicts:

```text
p_M ranks positively with |Delta_phi_pi|
```

Observed frozen result:

```text
rho = 6.648352e-01
p   = 9.599520e-03
```

## 16. Derivation of Law 3

The total strength is:

```text
S_e = C_e + lambda_core M_e
```

The coherent part contains the phase gate:

```text
G_phi = exp[-(Delta_phi_pi)^2 / (2 sigma_phi^2)]
```

Large phase mismatch suppresses the coherent contribution. Strong total source strength therefore favors lower phase mismatch. UTG predicts:

```text
S_e ranks negatively with |Delta_phi_pi|
```

Observed frozen result:

```text
rho = -5.172932e-01
p   = 1.049948e-02
```

## 17. Derivation of Law 4

The UTG sector state is:

```text
|Psi_UTG,e> = sqrt(p_C)|C> + exp(i Delta_phi_pi) sqrt(p_M)|M>
```

Its interference term is:

```text
I_e = 2 sqrt(p_C p_M) cos(Delta_phi_pi)
```

The interference term is largest when the relative phase is aligned. Therefore UTG predicts:

```text
I_e ranks negatively with |Delta_phi_pi|
```

Observed frozen result:

```text
rho = -8.956044e-01
p   = 4.999750e-05
```

## 18. Complete Derivation Chain

The derivation is:

```text
Axioms
-> Phi, sigma_ij
-> UTG action
-> Box Phi = dV/dPhi - rho
-> Box sigma_ij = T_ij^TT
-> detector projection h_a(t)
-> residual R_e^W
-> Delta_e
-> C_e and M_e
-> S_e
-> p_C, p_M, Delta_phi_pi
-> |Psi_UTG,e>
-> I_e
-> four laws
```

## 19. No-Curvature Closure

No step requires curvature. UTG uses:

```text
fixed flat background
temporal-rate scalar field
symmetric interaction field
source density
interaction source tensor
detector projection
```

The four gravitational-wave laws are the detector-level consequences of this field structure.
