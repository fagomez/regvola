# regvola

# The Fog of War: Detecting Structural Regimes of Volatility in Long-Term Conflict Data

![Workflow](../assets/workflow.png)

This project proposes a methodological framework to detect **structural regimes of uncertainty**
in long-term internal armed conflict data. Rather than periodizing conflicts solely by changes
in violence intensity, the approach focuses on the **volatility of violence**, understood as the
temporal unpredictability of violent events.

---

## Project overview

**regvola** (regimes of volatility analysis) implements a dual-path decomposition framework
that separates the dynamics of violence into two complementary components:

- **Intensity of violence**: long-term deterministic trends reflecting escalation and de-escalation.
- **Uncertainty of violence**: stochastic volatility capturing short-term instability and tactical shocks.

By isolating the innovation process of violence time series, the method identifies periods
during which the stochastic structure of violence remains stable and detects transitions
between qualitatively distinct volatility regimes.

---

## Motivation

Most empirical approaches to conflict periodization rely on changes in aggregate levels
of violence. However, variations in intensity often mix strategic trends with tactical noise,
obscuring important qualitative differences in conflict dynamics.

This project addresses this limitation by explicitly modeling the **stochastic component**
of violence. Changes in volatility can signal transformations in coordination, control,
and tactical behavior, even when average levels of violence remain stable.

---

## Methodological framework

### Dual-path decomposition

**Path A — Intensity (trend analysis)**  
- Variance-stabilizing square-root transformation of monthly event counts  
- STL decomposition to extract long-term trends  
- Change-point detection on the trend to identify historical intensity phases  

**Path B — Uncertainty (volatility analysis)**  
- SARIMA filtering to remove deterministic temporal dependence  
- Extraction of innovation residuals  
- Change-point detection (PELT) on residual volatility  

### Regime classification

The results from both paths are combined to classify the evolution of the conflict into
states such as:

- High intensity / low uncertainty  
- High intensity / high uncertainty  
- Low intensity / high uncertainty (fragmented violence)  
- Low intensity / low uncertainty  

This joint classification reveals dynamics that are invisible to trend-based analyses alone.

---

## Example results

![Regimes](../assets/regimes.png)

(Replace these figures with outputs generated from the analysis notebooks.)

---

## Repository

The full code and data used in this project are available at:

https://github.com/fagomez/regvola

Repository structure:


## 📁 Repository Structure

The source code and the data is available at:  
[GitHub repository](https://github.com/fagomez/nbglm)

The project is organized as follows:

<pre>
nbglm/
├── notebooks/        # Analysis notebooks
├── data/             # Violence data
├── docs/             # Project webpage
│   └── index.md
├── assets/           # Figures used in the webpage
├── README.md
└── requirements.txt
</pre>


## 📄 Citation

This work is currently **under review at PLOS ONE**.

If you wish to cite this work while it is under review, please use:

<pre> 
@unpublished{Gomez2026VOLA,
  title   = {The Fog of War: Detecting Structural Regimes of Volatility in Long-Term Conflict Data},
  author  = {G{\'o}mez, Francisco and Hern{\'a}ndez-Romero, Freddy},
  year    = {2026},
  note    = {Manuscript under review}
}
</pre>

