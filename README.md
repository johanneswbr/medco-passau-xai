# Passau MedCo · Employee Attrition and XAI

This project explores patterns in employee attrition and compares models that predict whether an employee will leave, using the [fictional IBM HR Analytics dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset).

- [Exploratory analysis](eda.ipynb) describes the workforce and examines attrition by factors such as overtime and tenure.
- [Model comparison](model_comparison.ipynb) compares logistic regression, random forest, and histogram gradient boosting.
- [Logistic regression](logistic_regression.ipynb) presents the selected model for Task 2, including the train/test split, settings, and results.

## Run locally

With [uv](https://docs.astral.sh/uv/) installed, run `uv sync --locked` in the project root. Open the notebooks in VS Code and select the Python interpreter from `.venv` as the kernel. The dataset is included under [`data/`](data/).
