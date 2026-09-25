# Cancer Detection from DNA-Fragment Data

**Machine Learning Project (IT1244)** · Jun 2026 – Present

## Problem
Detect cancer from cell-free DNA-fragment data across three settings — early-stage, screening-stage, and general cancer — from a dataset of **3,227 samples × 350 features**.

## Approach
- Built and benchmarked **6 scikit-learn classifiers**.
- **Dimensionality reduction**: cut features from **350 → 18–24** using **RFE**, **Lasso**, and **PCA**, keeping only the most informative signal.
- **Class imbalance**: addressed with **SMOTE** so the minority (positive) class wasn't drowned out.

## Result
Reached **0.95 precision**.

## Stack
Python · scikit-learn · RFE · Lasso · PCA · SMOTE
