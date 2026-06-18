# Chalcogen Barriers in 2D Materials: Reproducible Machine Learning Workflow

This repository contains the complete dataset and Jupyter notebook used in the study:

**"Chalcogen Impurity Barriers in 2D Systems via Semi-Empirical/Machine Learning Modeling: A Survey over 4000 Materials"**

The goal of this repository is to provide a fully reproducible workflow for the machine learning analyses presented in the manuscript. All calculations, model training procedures, correlation analyses, feature importance evaluations, and SHAP interpretability results can be reproduced directly from the provided notebook.

---

## Overview

In this work, adsorption energy barriers for three chalcogen impurities:

* Sulfur (S)
* Selenium (Se)
* Tellurium (Te)

were investigated across more than 4,000 two-dimensional materials from the C2DB database.

The adsorption barriers were initially estimated through a semi-empirical Extended Hückel Method (EHM) workflow. The resulting dataset was then combined with physicochemical descriptors and machine learning techniques to identify the main factors governing impurity mobility on 2D surfaces.

The notebook included in this repository reproduces the analyses reported in the manuscript, including:

* Data preprocessing
* Feature selection
* Correlation analysis
* Machine learning model training
* Hyperparameter optimization
* SHAP interpretability analysis
* Generation of figures and performance metrics

---

## Repository Structure

```text
.
├── Barrier.ipynb
│
├── features_S.csv
├── features_Se.csv
├── features_Te.csv
│
├── correlationS.csv
├── correlationSe.csv
├── correlationTe.csv
│
├── requirements.txt
└── README.md
```

---

## Input Files

### Feature Datasets

The files

* `features_S.csv`
* `features_Se.csv`
* `features_Te.csv`

contain the machine learning datasets used for each adsorbed impurity.

Each file includes:

* adsorption barrier values (target variable);
* physicochemical descriptors extracted from C2DB;
* manually calculated compositional descriptors;
* configurational and structural descriptors generated with the Matminer library.

These datasets correspond to the Full Set of Descriptors (FSD) discussed in the manuscript.

The descriptors include quantities such as:

* average valence electron count;
* average atomic number;
* average electronegativity;
* heat of formation;
* band gap;
* thickness;
* unit-cell area;
* coordination-environment descriptors;
* Matminer-derived structural and compositional features.

---

### Correlation Datasets

The files

* `correlationS.csv`
* `correlationSe.csv`
* `correlationTe.csv`

contain the reduced datasets employed for the Pearson correlation analyses.

These files were generated independently from the Matminer descriptor workflow and allow direct evaluation of the relationships between the adsorption barriers and selected physicochemical quantities.

They are used in the notebook to reproduce the correlation matrices and statistical analyses presented in the manuscript.

---

## Jupyter Notebook

### `Barrier.ipynb`

This notebook contains the complete analysis workflow used in the study.

The notebook performs:

### Data Loading

* Import of feature datasets for S, Se, and Te.
* Import of correlation datasets.

### Data Processing

* Cleaning and preparation of the datasets.
* Feature filtering.
* Train/test splitting.

### Machine Learning Models

The following supervised learning models are evaluated:

1. Linear Regression
2. Neural Network (MLP)
3. Decision Tree Regressor
4. XGBoost Regressor

### Hyperparameter Optimization

The XGBoost model is optimized using:

* Optuna

The optimization procedure searches for the best hyperparameter combination used in the final predictive models.

### Model Evaluation

Performance metrics include:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* Coefficient of Determination (R²)

### Interpretability Analysis

The notebook reproduces the SHAP analyses reported in the paper, allowing identification of the most influential descriptors governing adsorption barrier predictions.

### Correlation Analysis

Pearson correlation matrices are generated from the correlation datasets to compare statistical relationships with the feature importance rankings obtained from SHAP.

---

## Reproducing the Results

### 1. Clone the Repository

```bash
git clone https://github.com/USERNAME/chalcogen-barriers-c2db.git
cd chalcogen-barriers-c2db
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter

```bash
jupyter notebook
```

Open:

```text
Barrier.ipynb
```

and execute all cells sequentially.

---

## Requirements

Main Python packages:

* numpy
* pandas
* scipy
* matplotlib
* seaborn
* scikit-learn
* xgboost
* optuna
* shap
* jupyter

The complete list is provided in `requirements.txt`.

---

## Reproducibility

This repository was created to ensure full reproducibility of the machine learning analyses presented in the manuscript.

All required input datasets are provided, and no external database queries are necessary to reproduce the reported results.

Running the notebook with the supplied files reproduces:

* model training;
* model evaluation;
* feature importance rankings;
* SHAP analyses;
* correlation analyses;
* figures and statistics reported in the study.

---

## Citation

If you use this repository, please cite:

*Chalcogen Impurity Barriers in 2D Systems via Semi-Empirical/Machine Learning Modeling: A Survey over 4000 Materials.*



