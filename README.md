# Chalcogen Barriers in 2D Materials

This repository contains the data and Jupyter notebook used in the paper

"Chalcogen Impurity Barriers in 2D Systems via Semi-Empirical/Machine Learning Modeling: A Survey over 4000 Materials"

## Contents

- S adsorption barriers
- Se adsorption barriers
- Te adsorption barriers
- XGBoost models
- Optuna hyperparameter optimization
- SHAP analysis
- Pearson correlation analysis

## Input files

Place the following files in the `data/` directory:

- features_S.csv
- features_Se.csv
- features_Te.csv
- correlationS.csv
- correlationSe.csv
- correlationTe.csv

## Reproducing the analysis

```bash
pip install -r requirements.txt
