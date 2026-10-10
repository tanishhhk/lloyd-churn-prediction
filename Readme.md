# Customer Churn Prediction

A customer-level churn modeling workflow using the supplied multi-sheet Excel dataset. The focus is on getting the data model and validation design right before interpreting scores.

## Why this project exists

The workbook combines customer demographics, transaction history, customer-service interactions, online activity, and churn labels. Transactions and service interactions are repeated events, not independent customer records. Joining them directly on `CustomerID` creates a many-to-many row multiplication and can make a row-level train/test split misleading.

The notebook now:
- Aggregates transactions and service interactions into customer-level features.
- Validates the one-row-per-customer invariant before modeling.
- Excludes customer and event identifiers from the features.
- Splits customers before fitting preprocessing.
- Uses scikit-learn pipelines for imputation, scaling, and one-hot encoding.
- Compares logistic regression and random forest with ROC-AUC, average precision, balanced accuracy, and churn-class precision/recall/F1.

## Repository contents

- `Lloyd Customer Churning.ipynb`: the leakage-aware modeling workflow.
- `Customer_Churn_Data_Large.xlsx`: the dataset workbook.

## Run locally

Python 3.10 or newer is recommended.

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
jupyter lab
```

Open `Lloyd Customer Churning.ipynb` from the repository root and run all cells.

## Evaluation notes

The notebook calculates metrics from a stratified customer-level 80/20 holdout when it is run. Results from the original row-level workflow are not used as verified results.

The churn label has no documented outcome timestamp in the workbook, so this notebook does **not** claim temporal validation. A production-oriented next step would define a prediction snapshot date and a time-forward validation split. Also select an operational decision threshold using intervention costs rather than assuming 0.5 is optimal.

## Data and modeling limitations

- The notebook expects the five workbook sheets: `Customer_Demographics`, `Transaction_History`, `Customer_Service`, `Online_Activity`, and `Churn_Status`.
- Churn labels are expected to be binary `0/1`. The notebook fails explicitly if the dataset differs rather than silently coercing labels.
- This is a portfolio modeling project, not a deployed churn service or a claim that churn can be causally prevented by any particular feature.
