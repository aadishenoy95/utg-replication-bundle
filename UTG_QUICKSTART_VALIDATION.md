# UTG Quickstart Validation

**Citable record:** [https://doi.org/10.5281/zenodo.19491557](https://doi.org/10.5281/zenodo.19491557)

**Repository:** [https://github.com/aadishenoy95/utg-replication-bundle](https://github.com/aadishenoy95/utg-replication-bundle)

If you only want the fastest route to checking UTG, use this file.

## What This Lets You Do

This is not a full theory walkthrough. It is the shortest path to:

- understand what is being claimed
- run the frozen bundle
- compare your output to the expected output

## Fastest Reading Order

1. `UTG_FULL_REFERENCE.md`
2. `UTG_OUTSIDER_AUDIT.md`
3. `utg_external_replication_bundle.zip`

## What You Need

You need:

- the UTG repository or the replication bundle
- Python
- the GWOSC `.hdf5` data files used by the frozen event sets

## Fastest Validation Route

From the replication bundle folder, run:

```powershell
powershell -ExecutionPolicy Bypass -File .\RUN_ALL_UTG_LAWS.ps1 -DataDir "<path-to-gwosc-data>" -PythonExe python
```

That runs all 4 frozen laws.

## Expected Outputs

### Law 1. Two-Channel Source Law

- `rho = 8.736264e-01`
- `p = 1.499925e-04`

### Law 2. Phase-Morphology Law

- `rho = 6.648352e-01`
- `p = 9.599520e-03`

### Law 3. Phase-Strength Law

- `rho = -5.172932e-01`
- `p = 1.049948e-02`

### Law 4. Quantum Interference Law

- `rho = -8.956044e-01`
- `p = 4.999750e-05`

## What Counts As A Real Criticism

Good criticism:

- your rerun gives different outputs
- you find a bug in the code
- you find leakage in the event handling
- you show a simpler baseline that matches or beats the frozen laws
- you find an invalid assumption in the way the laws are defined

Weak criticism:

- "this sounds weird"
- "this looks AI-generated"
- "code passing isn’t science"

Those may be fair reactions, but they do not by themselves test the frozen package.

## Best Single File To Read

If you only open one explanatory file, open:

- `UTG_FULL_REFERENCE.md`

If you only open one skeptical file, open:

- `UTG_OUTSIDER_AUDIT.md`

## Current Outside-World Caveat

The strongest current missing piece is still:

- replication by a different human analyst or team

So the current package should be judged as:

- a frozen reproducible evidence package
- not yet final outside-world closure
