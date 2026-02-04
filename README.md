# Conflict Volatility Regime Detection

This repository contains the code and data associated with the study:

**The Fog of War: Detecting Structural Regimes of Volatility in Long-Term Conflict Data**

Francisco Gómez, Freddy Hernández-Romero  
Universidad Nacional de Colombia

---

## Project Overview

This repository implements a **dual-path decomposition framework** for the analysis of long-term internal armed conflict dynamics.

Rather than periodizing conflict solely based on levels of violence, the proposed approach explicitly distinguishes between:

- **Intensity of violence** (deterministic trend)
- **Uncertainty of violence** (stochastic volatility)

The core contribution is the identification of **structural regimes of volatility** by isolating the innovation process of violence time series and detecting changes in its variance.

---

## Methodological Summary

The workflow consists of three main steps:

1. **Variance stabilization**
   - Square-root transformation of monthly event counts.

2. **Dual-path decomposition**
   - **Path A – Intensity**
     - STL decomposition to extract long-term trends.
     - Binary Segmentation to identify historical phases of escalation and de-escalation.
   - **Path B – Uncertainty**
     - SARIMA filtering to remove deterministic temporal dependence.
     - Extraction of innovation residuals.
     - Change-point detection (PELT) on residual volatility.

3. **Regime classification**
   - Joint interpretation of intensity regimes and volatility regimes to characterize conflict dynamics.

---

## 📂 Repository Structure

---

### Main analysis notebook

notebooks/regimes_of_volatility.ipynb

### Data used in this analysis

data/monthlyViolenceColombia.xlsx

## 📄 Citation

This work is currently **under review at PLOS ONE**.

If you wish to cite this work while it is under review, please use the following reference:

<pre>
@unpublished{Gomez2026NBGLM,
  title   = {The Fog of War: Detecting Structural Regimes of Volatility in Long-Term Conflict Data},
  author  = {G{\'o}mez, Francisco and Hern{\'a}ndez-Romero, Freddy},
  year    = {2026},
  note    = {Manuscript under review}
}
</pre>