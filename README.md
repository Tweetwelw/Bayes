# Why a 95% Accurate Signal Can Still Be Wrong Most of the Time

**Bayes theorem, base rates, and rare-event detection in analytics & iGaming**

---

## Overview

This repository demonstrates why high signal quality (e.g. *“95% accuracy”*)
is often misleading when the underlying event is rare.

Using **Bayes’ theorem** and **Monte-Carlo simulation**, the notebook shows how
**event prevalence (base rate)** dominates **Positive Predictive Value (PPV)**,
even when sensitivity and specificity are very high.

Although the example is framed as a diagnostic test, the same logic applies
directly to **iGaming, fintech, and risk-heavy products** where rare-event
detection is the norm.

---

## What this notebook does

The notebook:

- Simulates outcomes at individual-user level for a large population
- Validates empirical results against the analytical Bayes formula
- Explores PPV behavior across different prevalence levels
- Visualizes PPV as:
  - a 2D surface (prevalence × signal quality)
  - PPV curves for different test qualities

The goal is not to optimize a model, but to **build correct intuition** about
what model outputs actually mean in rare-event settings.

---

## Why this matters in iGaming

Rare-event detection is everywhere in iGaming:

- fraud and chargeback prevention  
- bonus abuse detection  
- AML monitoring  
- risk segmentation  
- “suspicious behavior” rules  

When true positive events are rare, even very good models and rulesets can
produce **more false positives than true ones**.

This has real business consequences:

- unnecessary player friction  
- trust erosion  
- increased support and compliance noise  
- hidden revenue loss from wrongly blocked users  

**PPV is not a property of your model alone.  
It is a property of your model *and* the world it operates in.**

Ignoring base rates leads to confident but systematically wrong decisions.

---

## Assumptions used in examples

- Population size: **1,000,000**
- Event prevalence range: **0.5% – 5%**
- Sensitivity & specificity range: **90% – 99%**
- Symmetric case assumed: **sensitivity = specificity** (for clarity)

All parameters can be easily adjusted to simulate other domains
(e.g. fraud, payments, churn, medical screening).

---

## How to run

1. Clone the repository  
2. Open `Bayes.ipynb`  
3. Run cells top to bottom  

**Dependencies:**
- numpy
- pandas
- matplotlib
- seaborn
- plotly

---

## Notes

- The simulation is intentionally individual-level for transparency.
  For production use, the same logic can be implemented using aggregate counts
  (TP / FP / FN / TN) without material loss of insight.
- This notebook is intended as an **intuition-building tool**, not a
  production-ready system.

---

## Feedback

Discussion and feedback are welcome — especially around real-world cases
where model quality was optimized while base rates were ignored.
