# Heart Disease Prediction using Hybrid GWO and GAPSO Optimization

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.5+-red.svg)](https://xgboost.readthedocs.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This project implements a hybrid optimization approach for heart disease prediction using **Grey Wolf Optimizer (GWO)** and **Genetic Algorithm-Particle Swarm Optimization (GAPSO)** for feature selection, combined with **Random Forest (RF)** and **XGBoost (XGB)** classifiers. The work builds upon and extends the research by El-Shafey et al. (2022) by introducing GWO and comprehensive comparative analysis.

### Key Features:
- Hybrid GAPSO feature selection mechanism
- Grey Wolf Optimizer implementation
- Random Forest and XGBoost classifiers
- Comprehensive evaluation on Cleveland and Statlog datasets
- Hyperparameter tuning using GridSearchCV
- ROC curve analysis with AUC scores

## Objectives

1. Implement hybrid GAPSO and GWO for effective feature selection
2. Evaluate RF and XGBoost classifiers with optimized feature sets
3. Achieve higher prediction accuracy through optimization
4. Compare performance across multiple heart disease datasets

## 📊 Datasets

### Cleveland Dataset
- **Samples**: 303
- **Features**: 13 cardiac health indicators
- **Target**: Binary (0: Healthy, 1: Diseased)

### Statlog Dataset
- **Samples**: 270
- **Features**: 13 cardiac health indicators
- **Target**: Binary (0: Healthy, 1: Diseased)

**Features include**: age, sex, cp, trestbps, chol, fbs, restecg, thalach, exang, oldpeak, slope, ca, thal

## 🏗️ Methodology

### 1. Data Preprocessing
- Normalization using MinMaxScaler
- Target variable binarization
- Statistical analysis (T² metric calculation)
- Correlation analysis

### 2. Feature Selection

#### GAPSO Implementation
- **Genetic Algorithm**: Population initialization, single-point crossover, T2-based mutation
- **PSO**: Particle swarm optimization with velocity and position updates
- **Fitness Function**: 3-fold cross-validation accuracy

#### GWO Implementation
- Alpha, beta, delta wolves hierarchy
- Position updates based on hunting behavior
- Exploration and exploitation balance

### 3. Classification Models

#### Random Forest
- Ensemble learning with multiple decision trees
- Hyperparameter tuning via GridSearchCV

#### XGBoost
- Gradient boosting framework
- Optimized with learning rate and tree parameters

## 📈 Results

### Best Performance After Hyperparameter Tuning

| Dataset | Model | Accuracy | Selected Features |
|---------|-------|----------|-------------------|
| Cleveland | GAPSO + RF | **0.8579** | sex, cp, chol, fbs, restecg, oldpeak, slope, ca, thal (9 features) |
| Cleveland | GAPSO + XGB | 0.8315 | age, sex, cp, trestbps, chol, fbs, restecg, exang, oldpeak, slope, ca, thal (12 features) |
| Statlog | GAPSO + RF | **0.8667** | age, cp, fbs, restecg, exang, slope, ca, thal (8 features) |
| Statlog | GAPSO + XGB | 0.8185 | age, sex, fbs, restecg, exang, oldpeak, slope, ca, thal (9 features) |

### Key Findings
- Random Forest with GAPSO achieved highest accuracy (86.67% on Statlog)
- Significant dimensionality reduction while maintaining/improving accuracy
- Successful feature selection identified most discriminative attributes

## Installation and Usage

### Prerequisites
- Python 3.8+
- pip package manager

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/Heart-Disease-Prediction.git
cd Heart-Disease-Prediction
