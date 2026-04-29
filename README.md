<div align="center">

# ALPHA-AM  
## Active Learning for Process-Optimized High-Performance Alloy Discovery in Additive Manufacturing

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Status](https://img.shields.io/badge/Status-Reproducible-success.svg)]()

**Physics-informed active learning framework for accelerated discovery of printable, high-performance alloys for additive manufacturing**

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
data/initial_training_dataset.csv
data/featurized_dataset.csv
```

> The featurized dataset is provided explicitly to ensure direct reproducibility of model training and feature selection.

---

## Active Learning Generations
Includes all six active learning generations proposed and experimentally evaluated through ALPHA-AM:

- Generation 1–6 candidate compositions  
- Predicted acquisition rankings  
- Experimental validation results  
- Hardness responses  
- Crack outcomes

**Included as:**
```text
data/alpha_am_generations.csv
```

These compositions represent the alloy candidates discovered through the ALPHA-AM acquisition strategy.

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

Example training notebooks and scripts are provided in:

```text
models/
notebooks/
```

---

## Active Learning Acquisition Strategy

ALPHA-AM uses **Constrained Expected Improvement (CEI)** as the acquisition function:

$begin:math:display$
CEI\(x\)\=P\_\{safe\}\(x\)\\Big\[\(\\mu\(x\)\-f\_\{best\}\)\\Phi\(Z\)\+\\sigma\(x\)\\phi\(Z\)\\Big\]
$end:math:display$

where:

- $begin:math:text$P\_\{safe\}\(x\)$end:math:text$ = probability of crack-free printing  
- $begin:math:text$\\mu\(x\)$end:math:text$ = predicted hardness  
- $begin:math:text$\\sigma\(x\)$end:math:text$ = predictive uncertainty  
- $begin:math:text$f\_\{best\}$end:math:text$ = best observed hardness

This balances:

- exploitation of high-performing regions  
- uncertainty-driven exploration  
- manufacturability constraints

Acquisition examples and optimization workflows are included in:

```text
active_learning/
```

---

# Reproducing the Workflow

## 1. Train surrogate models
Use the 27-alloy featurized dataset to train:

- GPR hardness surrogate  
- GPC cracking classifier

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

This repository complements those materials by providing:

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
