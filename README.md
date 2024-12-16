# PM2.5 Concentration Analysis and Prediction in Beijing

## Overview
This project analyzes and predicts PM2.5 concentrations in Beijing using machine learning models. The dataset includes hourly measurements from 2010 to 2014, featuring PM2.5 levels and meteorological conditions. The project demonstrates robust data preprocessing, exploratory data analysis, and advanced model development.

## Features
- Time-series data preprocessing, including feature engineering (e.g., rolling statistics, lag features)
- Predictive modeling using:
  - Lasso Regression (baseline)
  - Ridge Regression
  - Random Forest
  - XGBoost
- Feature importance analysis with SHAP values
- Comprehensive evaluation using RMSE as the primary performance metric
- Uncertainty quantification across different temporal splits

## Repository Structure

├── data/
│   ├── raw/               # Original dataset
│   └── processed/         # Preprocessed dataset
├── notebooks/            # Jupyter notebooks for analysis
│   ├── 01_data_prep.ipynb
│   ├── 02_modeling.ipynb
│   └── 03_evaluation.ipynb
├── figures/              # Generated visualizations
├── results/             # Model outputs and metrics
├── src/                 # Source code
│   ├── init.py
│   ├── data_processing.py
│   ├── feature_engineering.py
│   ├── modeling.py
│   └── evaluation.py
├── environment.yml      # Conda environment file
├── requirements.txt     # Pip requirements file
├── LICENSE             # MIT License
└── README.md           # This file

## Environment Setup

### Using Conda (Recommended)

conda env create -f environment.yml
conda activate pm25_prediction

pip install -r requirements.txt

Dependencies
The project requires Python 3.8+ and the following packages:
python==3.8.12
pandas==1.3.4
numpy==1.21.4
scikit-learn==1.0.1
xgboost==1.5.0
shap==0.40.0
matplotlib==3.4.3
seaborn==0.11.2
jupyter==1.0.0

Data
The dataset (PRSA_data_2010.1.1-2014.12.31.csv) can be downloaded from the UCI Machine Learning Repository [here.](https://archive.ics.uci.edu/dataset/381/beijing+pm2+5+data)

Usage

Clone the repository:

git clone https://github.com/selinertekin/DATA1030-Semester-Project
cd Semester Project

conda env create -f environment.yml
conda activate pm25_prediction
python src/main.py


Results

Model performance (RMSE μg/m³):

XGBoost: 61.13 ± 4.27
Random Forest: 64.64 ± 4.09
Ridge: 66.14 ± 4.07
Lasso: 66.34 ± 4.00



Contributing
Feel free to open issues or submit pull requests with improvements.

License

This project is licensed under the MIT License - see the LICENSE file for details.
Acknowledgments

Dataset: US Embassy in Beijing PM2.5 data
Course: DATA1030 at Brown University
Libraries: scikit-learn, XGBoost, SHAP

And here's the corresponding `environment.yml`:

```yaml
name: pm25_prediction
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.8.12
  - pandas=1.3.4
  - numpy=1.21.4
  - scikit-learn=1.0.1
  - xgboost=1.5.0
  - shap=0.40.0
  - matplotlib=3.4.3
  - seaborn=0.11.2
  - jupyter=1.0.0
  - pip=21.3.1
  - pip:
    - jupyter-contrib-nbextensions==0.5.1

