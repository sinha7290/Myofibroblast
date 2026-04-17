# Stromal State Analysis in IBD using COMPASS

This repository contains analysis workflows used to quantify and evaluate stromal myofibroblast states in inflammatory bowel disease (IBD).

---

## Overview

We identify two opposing stromal programs:

- **CXCL14⁺ inflammatory myofibroblasts (IMF)**
- **CD36⁺ quiescent myofibroblasts (QMF)**

These states define a biologically interpretable axis of stromal activation associated with disease severity and outcomes.

---

## Methodological Framework

### COMPASS (COMPosite Activity Scoring System)

Gene signature activity is quantified using **COMPASS**, a deterministic, threshold-based scoring framework: https://compass.precsn.com/

Score = (expression − (threshold + 0.5)) / (3 × SD)

- Thresholds derived using StepMiner  
- Scores aggregated across genes to generate sample-level activity  
- Preserves gene directionality  
- No dependence on permutations or gene ontologies  

This enables **reproducible, interpretable digital biomarkers** across datasets.

---

## Analyses Included

- **Dot plot analysis**  
  Visualizes signature activity, directionality, and classification strength (AUC)

- **Univariate (UV) analysis**  
  Association testing using t-test or OLS regression  

- **Multivariate (MV) analysis**  
  Covariate-adjusted modeling using statsmodels  

- **ROC–AUC evaluation**  
  Classification performance assessed using scikit-learn  

---

## Files

- `MF_dot_plots.ipynb` → Signature visualization  
- `UV_MV_analysis.ipynb` → Statistical modeling (UV + MV)  
- `MF_15gene_test.txt` → Example dataset  

---

## Input Format

- Rows: genes  
- Columns: samples  
- Values: normalized expression (e.g., TPM)  

Optional metadata can be included for group labels and clinical variables.

---

## Usage

Run analyses directly from notebooks:

1. Open `MF_dot_plots.ipynb` → run all cells  
2. Open `UV_MV_analysis.ipynb` → run all cells  

---

##  Reproducibility

- Deterministic scoring (COMPASS)  
- Explicit thresholding (StepMiner)  
- No stochastic steps  
- Fully reproducible from provided data  

---

## Interpretation

- High IMF score → inflammatory, disease-associated state  
- High QMF score → quiescent, homeostatic state  

This framework enables biologically grounded patient stratification and hypothesis generation.

---

## Requirements

- Python ≥ 3.8  
- pandas  
- numpy  
- scipy  
- matplotlib  
- seaborn  
- scikit-learn  
- statsmodels  
- StepMiner (for threshold calculation, if not precomputed)

---

## Contact

Saptarshi Sinha  
UC San Diego  
