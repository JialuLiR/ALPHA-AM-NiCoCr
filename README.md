<div align="center">

# ALPHA-AM  
## Active Learning for Process-Optimized High-Potential Alloy Discovery in Additive Manufacturing

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)]()
[![Status](https://img.shields.io/badge/Status-Reproducible-success.svg)]()

**Physics-informed active learning framework for accelerated discovery of printable, high-potential alloys for additive manufacturing**

---

</div>

## Overview

This repository contains the data and computational framework supporting **ALPHA-AM**, an active learning workflow integrating:

- CALPHAD-informed alloy design  
- High-throughput additive manufacturing experiments  
- Feature-based machine learning surrogate modeling  
- Probabilistic hot cracking classification  
- Constrained expected improvement (CEI) driven active learning acquisition

The framework is designed to identify alloys that simultaneously optimize:

- Mechanical performance  
- Manufacturability  
- Crack resistance  

while minimizing experimental burden through iterative model-guided exploration.

---

## Repository Contents

This repository includes all datasets and code required to reproduce the machine learning and active learning framework reported in this work, including:

### Initial Training Dataset (27 Alloy Dataset)
Contains the complete **27-point experimental dataset** used for initial model development, including:

- Alloy compositions  
- All **21 selected descriptors/features** used in surrogate modeling  
- Experimental hardness labels  
- Hot cracking classifications  

**Included as:**
```text
gp_features.csv
```

---

## Active Learning Generations
Includes all six active learning generations proposed and experimentally evaluated through ALPHA-AM:

- Generation 1–6 candidate compositions   
- Experimental validation results  
- Hardness responses  

**Included as:**
```text
Hardness_Repo.csv
```
---

## Machine Learning Framework
Code is provided for reproducing surrogate model development, including:

### Regression Surrogate
Gaussian Process Regression (GPR) for hardness prediction

- Feature filtering workflow  
- Model training  
- Cross validation  
- Uncertainty quantification

### Classification Surrogate
Gaussian Process Classification (GPC) for crack susceptibility

- Probabilistic crack-free likelihood  
- Safety constraint estimation  
- Manufacturability screening
---

## Active Learning Acquisition Strategy

ALPHA-AM uses **Constrained Expected Improvement (CEI)** as the acquisition function:

```math
CEI(x)=P_{safe}(x)\Big[(\mu(x)-f_{best})\Phi(Z)+\sigma(x)\phi(Z)\Big]
```

where:

- $P_{safe}(x)$ = probability of crack-free printing  
- $\mu(x)$ = predicted hardness  
- $\sigma(x)$ = predictive uncertainty  
- $f_{best}$ = best observed hardness  
- $Z=\dfrac{\mu(x)-f_{best}}{\sigma(x)}$

This balances:

- exploitation of high-performing regions  
- uncertainty-driven exploration  
- manufacturability constraints

Please note, acquisition strategies will vary based on the users task. 

---

# Reproducing the Workflow

## 1. Train surrogate models
Use the 27-alloy featurized dataset to train:

- GPR hardness surrogate  
- GPC cracking classifier

Please follow the code outlined in the included jupyter notebook

```text
gp_training.ipynb
```
---

## 2. Run active learning acquisition
Evaluate candidate composition space using the aqcquisition policy of your choice:

---

## 3. Compare with experimentally validated generations


to compare model-selected candidates with experimentally validated alloy outcomes.

---

# Data Included for Reproducibility

✔ Full 27-point initial training dataset  
✔ Full 21-feature featurized dataset  
✔ Hardness labels and crack classifications  
✔ Six ALPHA-AM generation compositions  
✔ Experimental validation results  
✔ Surrogate model training code  

---

# Methodological Notes
Detailed methodology, experimental procedures, descriptor definitions, and feature selection rationale are documented in the main manuscript and Supplementary Information.

---

## Citation
If using this repository, please cite:

```bibtex
title={Active learning for the accelerated discovery of complex concentrated NiCoCr alloys in additive manufacturing},
author={Talbot, Ajay, et. al},
journal={TBD},
year={2026}
}
```

---

<div align="center">

### Accelerating alloy discovery through physics-informed active learning

</div>
