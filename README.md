# Passau MedCo · Employee Attrition and XAI

This project explores patterns in employee attrition and compares models that predict whether an employee will leave, using the [fictional IBM HR Analytics dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset).

- [Exploratory analysis](eda.ipynb) examines how attrition varies by factors such as overtime and tenure.
- [Prediction and XAI](model_xai.ipynb) compares logistic regression and random forest against a baseline. Local and global model explanations are planned.

## Run locally

With [uv](https://docs.astral.sh/uv/) installed, run `uv sync --locked` in the project root. Open the notebooks in VS Code and select the Python interpreter from `.venv` as the kernel. The dataset is included under [`data/`](data/).
