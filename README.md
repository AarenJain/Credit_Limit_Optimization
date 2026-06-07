# Predictive Credit Limit Optimization Engine

## 💰 Business Impact Summary

- **Total Portfolio Value Generated:** $83,477.39 (Annualized)
- **Risk Capital Insulated (Loss Prevention):** $71,775.00
- **Projected Annual Swipe Revenue Unlocked:** $11,702.39
- **Portfolio Action Distribution:** 2,243 Limit Increases | 70 Limit Slashes | 6,637 Maintained

---

## 📋 Project Overview

This repository contains a production-ready, end-to-end data stack that transforms a raw, uncalibrated portfolio of ~9,000 credit card accounts into an automated capital optimization engine.

Instead of relying on rigid, hardcoded rules or basic binary predictions, this system implements a **Supervised Machine Learning Classification Pipeline** to score continuous default probabilities. A custom business logic layer then maps these probabilities to dynamic credit limit adjustments—simultaneously maximizing transactional interchange fees for safe spenders and minimizing credit exposure for high-risk accounts.

---

## 🛠️ Technical Architecture & Data Stack

The entire project is structured into an optimized, unified pipeline across a single production environment:

1. **Data Engineering & Quality Assurance (Python / Pandas):**
   - Implemented robust data cleansing pipelines to eliminate structural anomalies, drop identical server logging duplicates, and handle missing values via column medians.
   - Handled formatting distortions by regularizing transactional fields into absolute positive values.

2. **Machine Learning Operations (Scikit-Learn Classifier):**
   - Engineered a custom banking risk target variable mimicking credit default indicators.
   - Purged feature sets of driving metrics to eliminate **Data Leakage** and ensure real-world model credibility.
   - Trained a **100-Tree Random Forest Classifier** to navigate heavily imbalanced portfolio data and extract granular, continuous mathematical risk probabilities (`model.predict_proba`).

3. **Explainability & Governance (Matplotlib / Seaborn):**
   - Extracted model feature importances to satisfy banking regulatory clarity requirements, proving that cash-advance borrowing and baseline utilization metrics dictated risk scores.
   - Compiled an executive graphical dashboard charting portfolio action allocations, risk curves, and capital boundary shifts.

4. **Data Persistence & Relational Verification (SQL / SQLite3):**
   - Instantiated an in-memory relational SQL engine and built a structured schema complete with strategic indexing.
   - Streamed dataframes directly into the database and wrote relational group-by aggregation queries to audit and verify portfolio capital shifts.

---

## 📊 Core Portfolio Optimization Logic

The analytical engine executes capital adjustments based on three distinct behavioral cohorts:

| Customer Segment          | Criteria Constraints       | Model Probability | Optimization Action         |
| :------------------------ | :------------------------- | :---------------- | :-------------------------- |
| **High-Value Spenders**   | Purchases > $1,000         | Risk Prob < 15%   | **Increase Limit (+30%)**   |
| **High-Risk Volatiles**   | Over-utilizing limits      | Risk Prob > 50%   | **Slash Limit (-50%)**      |
| **Stable Core Portfolio** | Standard activity balances | 15% to 50%        | **Maintain Baseline Limit** |

---

## 🚀 How To Run the Production Pipeline

### Prerequisites

Ensure your local environment runs Python 3.x via Anaconda with the following libraries configured:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```
