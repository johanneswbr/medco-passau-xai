# Passau MedCo · Employee Attrition and XAI

This project predicts whether an employee will leave and explains the predictions with LIME. It uses the [fictional IBM HR Analytics dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) for the fictional company Passau MedCo.

## Notebooks

1. [Exploratory analysis](01_eda.ipynb) describes the workforce and examines attrition by factors such as overtime and tenure.
2. [Model training and evaluation](02_modeling.ipynb) tunes and evaluates the final **XGBoost** model.
3. LIME explanations of individual predictions (planned).

### Why XGBoost and not logistic regression?

On this data, a logistic regression ranks employees about as well as XGBoost. However, its coefficients can be read directly, so LIME would add little. The exercise asks us to explain a model with LIME, so we use XGBoost. Its ensemble of several hundred trees cannot be read directly.

### Comparisons and earlier experiments

These notebooks are not the final model and are kept for reference:

- [Random forest](02_modeling_random_forest.ipynb) runs the same steps as `02_modeling.ipynb` with a random forest. A random forest is easier to explain but ranks employees clearly worse.
- [Model comparison](model_comparison.ipynb) compares logistic regression, random forest and histogram gradient boosting with nested cross-validation.
- [Logistic regression](logistic_regression.ipynb) tunes a logistic regression with hand-built features. It serves as an interpretable reference.

## Run locally

With [uv](https://docs.astral.sh/uv/) installed, run `uv sync --locked` in the project root. Open the notebooks in VS Code and select the Python interpreter from `.venv` as the kernel. The dataset is included under [`data/`](data/).

On macOS, XGBoost also needs the OpenMP runtime: `brew install libomp`.
