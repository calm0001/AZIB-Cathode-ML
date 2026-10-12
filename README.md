# AZIB-Cathode-ML

## Project Overview

This repository accompanies the manuscript **“A Domain-Aware Machine-Learning Framework for Evidence-Backed Cathode Screening in Aqueous Zinc-Ion Batteries”**.

The research integrates machine-learning prediction, framework-aware validation, applicability-domain analysis, model disagreement, literature verification, and structure-level assessment to prioritize candidate cathode materials for aqueous zinc-ion batteries.

## Dataset and Features

The study includes 6,847 insertion-electrode records, including 434 zinc-ion records, and a separate screening library of 6,874 zinc-containing materials. A common set of 53 numerical features was used for model development.

## Methods

Nine regression models were investigated: Ridge, SVR, Decision Tree, Random Forest, Extra Trees, Gradient Boosting, XGBoost, CatBoost, and LightGBM.

The workflow includes framework-group holdout validation, non-Zn-to-Zn transfer testing, zinc-domain out-of-fold validation, SHAP interpretation, feature ablation, applicability-domain assessment, and candidate screening.

## Main Results

- Framework-group holdout CatBoost R²: 0.8247 (voltage) and 0.8372 (capacity).
- Strict non-Zn-to-Zn transfer R²: −1.03 (voltage) and 0.27 (capacity).
- Selected zinc-domain out-of-fold R²: 0.7025 (voltage) and 0.7734 (capacity).
- Screening reduced 6,874 candidates to 13 experimental-priority finalists.
- Hodgkinsonite, Zn₂Mn(SiO₄)(OH)₂, was selected for structure-level assessment.

## Reproducibility and Limitations

The repository distinguishes archived-result reproduction from independent model retraining. Complete historical per-fold preprocessing states were not independently recoverable, and exact replay of all historical model fits is not claimed.

The hodgkinsonite assessment supports only a site-dependent partial de-zincation hypothesis. Electrochemical reversibility and aqueous stability remain unverified.

## Data Source

The original insertion-electrode and materials records were obtained from the Materials Project. Source attribution and any applicable data redistribution conditions should be preserved.

## Citation

Please cite the associated manuscript when publication details become available.
