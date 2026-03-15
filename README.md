# HEPSIM Evaluation Task — GSoC 2026
### ML4SCI – HEP Simulation | Quark & Gluon Jet Analysis

---

## Summary

Analysis of 500,000 quark and gluon jets from the Pythia 8 dataset using vectorized NumPy operations. The notebook covers data exploration, jet observable computation, Lorentz boost to the jet center-of-mass frame, and binary classification using a Random Forest. Best AUC achieved: **86.51** (lab frame, `max_depth=10`, `n_estimators=500`), with **Multiplicity** identified as the most discriminating feature.

---

## Dataset

**Pythia 8 Quark and Gluon Jets** — Komiske, Metodiev & Thaler (2019)  
DOI: [10.5281/zenodo.3164691](https://zenodo.org/records/3164691)

The notebook automatically downloads the 5 required files (`QG_jets.npz` through `QG_jets_4.npz`) from Zenodo on first run. No manual download needed.

---

## Structure

```
.
├── JET_PARTICLES.ipynb   # Main submission notebook
├── requirements.txt      # Python dependencies
└── README.md
```

---

## Notebook Sections

| Section | Description |
|---|---|
| **(a)** Data Loading & Exploration | Loading, zero-padding, multiplicity & leading constituent distributions |
| **(b)** Jet Observables | Jet mass, width, and pT dispersion — quark vs. gluon comparisons |
| **(c)** Lorentz Boost | Vectorized boost to jet rest frame, verification, scatter plots |
| **(d)** Classification | Random Forest classifier, ROC/AUC, confusion matrix, feature importance |

---

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook JET_PARTICLES.ipynb
```

Run all cells top to bottom. The dataset will be downloaded automatically (~2.5 GB total). Tested under Python 3.11+.

---

## Key Results

- **Lab Frame AUC:** ~0.865
- **Rest Frame AUC:** ~0.858
- **Most discriminating feature:** Multiplicity
- Working in the rest frame removes production-spectrum kinematic bias, yielding a more physically robust but marginally harder classification problem.
