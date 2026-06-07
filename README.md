# Credit Limit Optimization Engine

## Overview
This project builds a data pipeline that uses machine learning to dynamically optimize credit card limits. Using a Random Forest model, it calculates continuous risk probabilities for each account. This allows a bank to safely increase credit limits for high-value spenders to capture more transactional revenue, while proactively cutting limits for high-risk accounts to prevent default losses.

## Pipeline Steps
1. **Data Cleaning:** Removed duplicate rows, handled missing values via column medians, and corrected absolute formatting errors.
2. **Target Engineering:** Defined a custom credit risk flag based on high card utilization and low payment activity.
3. **Machine Learning:** Trained a Random Forest Classifier to output continuous default probabilities, intentionally removing leaking features to prevent data cheating.
4. **Optimization Engine:** Ran a custom Python loop to dynamically scale limits up by 30% for high-value safe spenders, slash them by 50% for high-risk flags, or maintain baseline levels.
5. **SQL Ingestion & Audit:** Loaded the final results directly into an in-memory SQLite database table to run structured group-by queries, verifying data consistency between the Python pipeline and the database layer.

## Quantifiable Results
* **Total Portfolio Value Generated:** $83,477.39 (Annualized)
* **Risk Capital Saved (Loss Prevention):** $71,775.00
* **New Annual Swipe Revenue Unlocked:** $11,702.39
* **Portfolio Actions:** 2,243 Increases | 70 Slashes | 6,637 Maintained
