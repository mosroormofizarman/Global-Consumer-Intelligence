# AGENTS.md — Global Consumer Intelligence ML Pipeline

## Project Overview
End-to-end machine learning proof-of-concept for telecom smart-plan upsell prediction and customer propensity modeling (University of Tokyo Matsuo-Iwasawa Lab GCI Program).

## Environment & Tech Stack
- Language: Python 3.10+
- Core Libraries: `pandas`, `numpy`, `scikit-learn`, `lightgbm`, `matplotlib`, `seaborn`
- Execution: Jupyter Notebooks (`.ipynb`) and modular Python preprocessing scripts

## Agent Instructions & Conventions
- **Data Integrity:** Never modify raw dataset files directly. Always write feature transformations as idempotent functions that return a new DataFrame copy.
- **Data Leakage Prevention:** Ensure all scalers, imputers, and target encoders are fitted strictly on the training split inside cross-validation folds.
- **Code Style:** Follow PEP 8 conventions, use type hints for all feature engineering utilities, and document ROC-AUC / PR-AUC evaluation metrics before committing changes.

## Verification Workflow
- Before finalizing any refactoring task, verify that all notebook cells execute sequentially without `KeyError` or shape mismatch exceptions.
- Summarize feature importance shifts and validation score deltas in the pull request or commit description.
