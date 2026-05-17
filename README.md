# Machine-Learning Prediction of AlGaN Bandgaps Using Only DFT Structural Descriptors

This repository contains the dataset, machine-learning workflows, and analysis scripts used for the prediction of DFT-calculated bandgaps of AlxGa1−xN alloys using structural and computational descriptors collected from first-principles studies.

The work was developed as part of the manuscript:

> “Machine-Learning Prediction of AlGaN Bandgaps Using Only DFT Structural Descriptors”

---

# Overview

The objective of this project is to develop a machine-learning framework capable of predicting the electronic bandgap of AlGaN alloys directly from descriptors commonly available in density functional theory (DFT) simulations.

The compiled dataset contains heterogeneous first-principles calculations reported in the literature together with additional FP-LAPW calculations performed using WIEN2k.

The framework is intended as a surrogate model for DFT-level bandgap estimation and rapid materials screening.

---

# Dataset

The dataset consists of 240 samples including:

- 213 DFT-based calculations
- 24 GW-based calculations
- 3 semi-empirical EPM entries

No experimental data were included.

The dataset spans both:
- Zinc-blende (ZB)
- Wurtzite (WZ)

crystal phases across the full compositional range:

0 ≤ x ≤ 1

---

# Included Descriptors

The dataset includes the following descriptors:

- Alloy composition (x)
- Crystal phase
- Unit-cell volume
- Space group
- Lattice constants (a, b, c)
- Bulk modulus (B)
- Pressure derivative (B′)
- Dielectric constants (εxx, εzz)
- Computational method
- Approximation type
- Exchange-correlation functional

Target variable:
- Electronic bandgap (eV)

---

# Machine-Learning Models

The repository includes implementations of several regression models, including:

- Gradient Boosting Regressor
- Random Forest
- XGBoost
- LightGBM
- Extra Trees
- AdaBoost
- Support Vector Regression (SVR)
- Ridge Regression
- Lasso Regression
- KNN Regression
- HistGradientBoosting

---

# Validation Strategy

To ensure statistically reliable evaluation, model performance was assessed using:

- Conventional train/test splitting
- 5-fold cross-validation
- Repeated 5-fold cross-validation (10 repetitions)

The final reported results are based primarily on repeated cross-validation to reduce dependence on a specific data partition.

Best model:
- Gradient Boosting Regressor

Typical performance:
- R² ≈ 0.88
- MAE ≈ 0.31 eV

---

# Repository Structure

```text
ML-AlGaN-Bandgap-Prediction/
│
├── dataset/
│   └── AlGaN_dataset.csv
│
├── notebooks/
│   ├── Bandgap_Prediction.ipynb
│   └── Bandgap_Prediction.html
│
├── figures/
│
├── requirements.txt
├── LICENSE
└── README.md 


	
	
