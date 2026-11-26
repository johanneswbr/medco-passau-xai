# Passau MedCo · Employee Attrition and XAI

This project predicts whether an employee will leave and explains the predictions with LIME. It uses the [fictional IBM HR Analytics dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) for the fictional company Passau MedCo.

## Notebooks

1. [Exploratory analysis](01_eda.ipynb) describes the workforce and examines attrition by factors such as overtime and tenure.
2. One notebook per model, all with the same stratified 80/20 train-test split:
   - [XGBoost](02_modeling_xgboost.ipynb) tunes and evaluates the **final model**.
   - [Random forest](02_modeling_random_forest.ipynb) runs the same steps with a random forest. It is easier to explain but ranks employees clearly worse.
   - [Logistic regression](02_modeling_logistic_regression.ipynb) tunes a logistic regression with hand-built features. It serves as an interpretable reference.
3. LIME explanations of individual predictions (planned).

### Why XGBoost and not logistic regression?

On this data, a logistic regression ranks employees about as well as XGBoost. However, its coefficients can be read directly, so LIME would add little. The exercise asks us to explain a model with LIME, so we use XGBoost. Its ensemble of several hundred trees cannot be read directly.

## Run locally

With [uv](https://docs.astral.sh/uv/) installed, run `uv sync --locked` in the project root. Open the notebooks in VS Code and select the Python interpreter from `.venv` as the kernel. The dataset is included under [`data/`](data/).

On macOS, XGBoost also needs the OpenMP runtime: `brew install libomp`.
