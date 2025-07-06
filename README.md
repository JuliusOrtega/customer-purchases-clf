# Online Shopper Revenue Prediction

## Project Overview

This repository showcases a data-science workflow for a large retail brand that wants to sharpen its online-sales strategy. Leveraging 12 months of Google Analytics session data—one row per customer visit—we develop and compare several classification models that estimate the probability a visitor will generate revenue during that session. The resulting probability scores are intended to help marketing and product teams:

Prioritise remarketing and personalisation efforts toward high-value visitors

Estimate campaign ROI before budget is committed

Monitor conversion behaviour as site features and promotions change

The notebook walks through data exploration, feature engineering, model training (logistic regression, neural network, and a tree-based classifier), hyper-parameter tuning, and threshold optimisation, all evaluated with cross-validated ROC-AUC. While the workflow runs end-to-end inside the notebook, it is designed as a reference implementation that can be adapted or expanded for production use.

## Objectives

The main goal is to build a complete end-to-end pipeline that includes data preprocessing, exploratory analysis, feature engineering, model selection, hyperparameter tuning, and performance evaluation.

## Workflow Outline

1. **Exploratory Data Analysis** – descriptive statistics, histograms, box-plots, and other business-oriented visualisations  
2. **Data Cleaning & Preparation**  
   - Missing-value and outlier handling  
   - Encoding of categorical features (one-hot, mapping, label encoding)  
   - Removal of irrelevant or redundant variables  
3. **Feature Scaling** – standardisation of numerical attributes  
4. **Dataset Split** – training / hold-out test partition  
5. **Model Development**  
   - Baseline linear classifier (e.g., logistic regression)  
   - Feed-forward neural network  
   - Comparative third approach (e.g., tree-based model)  
6. **Hyperparameter Optimisation** – grid search with cross-validation  
7. **Model Selection** – choose the best performer via cross-validated ROC-AUC  
8. **Threshold Optimisation** – select the probability cut-off that maximises ROC-AUC  
9. **Final Evaluation & Reporting** – generate test-set metrics and compile results in a single Jupyter Notebook

## Dataset Description

The dataset includes ten numerical and eight categorical attributes. It is publicly available from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset).

### Target Variable

- `Revenue`: Binary variable indicating whether a purchase was made during the session.

### Key Features

- **Administrative, Informational, ProductRelated & Durations**: Count and total duration of administrative, informational, and product-related pages visited.
- **BounceRate & ExitRate**: Metrics from Google Analytics that capture user behavior regarding exits and bounces.
- **PageValue**: The average value of a page visited prior to a transaction.
- **SpecialDay**: Proximity of the visit date to special shopping days (e.g., Valentine’s Day), with values ranging from 0 to 1 depending on proximity.
- **Categorical Attributes**: Include `OperatingSystems`, `Browser`, `Region`, `TrafficType`, `VisitorType` (New vs. Returning), `Weekend` (boolean), and `Month`.

## Notes

- The preprocessing pipeline is shared across all models.
- Code quality, interpretations, and justifications will be evaluated.
- Additional models and techniques covered during the course can be applied if well-motivated.

## Deliverable

A Jupyter Notebook containing all analyses, models, justifications, and visualizations, demonstrating an end-to-end data science solution.
