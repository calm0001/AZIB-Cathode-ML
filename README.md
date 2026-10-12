# AZIB-Cathode-ML

## Project Overview

This repository accompanies the manuscript **"A Domain-Aware Machine-Learning Framework for Evidence-Backed Cathode Screening in Aqueous Zinc-Ion Batteries"**.

The study presents a domain-aware machine-learning framework for screening cathode materials for aqueous zinc-ion batteries (AZIBs). The workflow integrates predictive modeling, framework-aware validation, cross-ion transfer assessment, model interpretation, reliability analysis, literature verification, and structural screening.

The repository provides the computational source code, manuscript figures, and associated tables. The full research dataset is available from the corresponding author upon reasonable request.

## Repository Contents

- **src/reproduce_paper.py** — Integrated Python code for data processing, machine-learning analysis, screening, structural assessment, and figure generation.
- **figures/** — Figures associated with the manuscript.
- **tables/** — Tables and numerical results associated with the manuscript.
- **requirements.txt** — Python dependencies and recorded software versions.
- **README.md** — Project description, usage instructions, data availability, and reproducibility information.

The complete dataset is not included in the public repository because of file-size limitations.

## Dataset and Features

The study used 6,847 insertion-electrode records, including 6,413 non-Zn records and 434 Zn records, together with a separate screening library of 6,874 Zn-containing materials.

A common set of 53 numerical features was constructed from Materials Project properties, crystal symmetry, chemical composition, and working-ion descriptors.

The original materials information was obtained from the Materials Project. Relevant attribution and third-party data-use conditions apply.

## Machine-Learning Methods

Nine regression models were investigated: Ridge, Support Vector Regression, Decision Tree, Random Forest, Extra Trees, Gradient Boosting, XGBoost, CatBoost, and LightGBM.

Model evaluation included framework-group holdout validation, strict non-Zn-to-Zn transfer testing, and Zn-domain out-of-fold validation. Additional analyses included feature-group ablation, SHAP interpretation, ensemble disagreement, applicability-domain assessment, and evidence-based candidate screening.

## Main Results

- Framework-group holdout CatBoost R²: **0.8247** for voltage and **0.8372** for capacity.
- Strict non-Zn-to-Zn transfer R²: **−1.03** for voltage and **0.27** for capacity.
- Selected Zn-domain out-of-fold R²: **0.7025** for voltage and **0.7734** for capacity.
- Screening reduced 6,874 candidate materials to 13 experimental-priority finalists.
- Hodgkinsonite, Zn₂Mn(SiO₄)(OH)₂ (Materials Project ID: mp-aaacpfiq), was selected for structure-level assessment.

The structural analysis supports only a site-dependent partial de-zincation hypothesis. Electrochemical performance and aqueous stability have not been experimentally verified.

## Installation and Usage

The recorded computational environment used Python 3.14.5. Required Python packages are listed in `requirements.txt`.

Clone the repository and install the dependencies:

`git clone https://github.com/calm0001/AZIB-Cathode-ML.git`

`cd AZIB-Cathode-ML`

`python -m pip install -r requirements.txt`

**Dataset requirement:** The integrated database is not distributed through this repository. After obtaining the dataset from the corresponding author, place `azib_paper_dataset.sqlite` in the `input_data/` directory.

The main script provides two execution modes:

**Archived-result reproduction:**

`python src/reproduce_paper.py --mode reproduce --validate`

**Independent computation:**

`python src/reproduce_paper.py --mode full --validate`

These commands require access to the integrated database. A fresh clone of the public repository alone is insufficient for complete execution.

## Reproducibility and Limitations

The archived-result reproduction mode uses retained historical outputs, whereas the full computation mode performs new numerical calculations.

Complete historical per-fold preprocessing states were not independently recoverable. Therefore, exact reconstruction of every historical training execution is not claimed.

Literature-based candidate selection includes previously recorded human verification decisions. Structural screening uses unrelaxed topology and charge-balance approximations rather than experimental electrochemistry or first-principles vacancy and migration calculations.

## Data and Code Availability

The code used in this study is publicly available at:

https://github.com/calm0001/AZIB-Cathode-ML

The datasets generated and analyzed during this study are available from the corresponding author upon reasonable request, subject to applicable third-party data-access and redistribution conditions.

The complete dataset is not hosted in this repository due to file-size limitations.

## Citation

If the code or results are used in academic research, please cite the associated manuscript:

Cai, J., Lai, Q., Huang, J., et al. *A Domain-Aware Machine-Learning Framework for Evidence-Backed Cathode Screening in Aqueous Zinc-Ion Batteries.*

Publication information and DOI will be updated when available.

## Contact

**Corresponding author:** Qi Lai

**Affiliation:** Panzhihua University, China

**Email:** 49129834@qq.com
