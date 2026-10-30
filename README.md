# ML Coding Practice

Classic machine-learning coding practice for interview preparation. The first
workbook is a guided Titanic binary-classification exercise covering:

- NumPy and pandas data manipulation
- exploratory analysis and missing values
- train/validation splitting and leakage prevention
- scikit-learn preprocessing pipelines
- logistic regression and random forests
- accuracy, precision, recall, F1, ROC AUC, and confusion matrices
- feature engineering, cross-validation, inference, and model persistence

No deep-learning frameworks are included.

## Quick start

This project uses Python 3.11 and `uv` for a reproducible local environment.

```sh
git clone https://github.com/dhawan98/ML-Coding.git
cd ML-Coding
uv venv --python 3.11 .venv
uv pip sync --python .venv/bin/python requirements-ml.lock
.venv/bin/python -m ipykernel install --sys-prefix \
  --name roblox-classic-ml --display-name "Python (Roblox Classic ML)"
source .venv/bin/activate
jupyter lab
```

Open `Roblox_ML_Interview_Titanic_Guided.ipynb` and choose the
**Python (Roblox Classic ML)** kernel.

See `ML_ENVIRONMENT.md` for editor setup, new-notebook usage, and dependency
maintenance.

## Data

The workbook downloads and locally caches a public Titanic CSV on its first
run. Alternatively, place Kaggle's Titanic `train.csv` in `data/` or beside the
notebook. Generated data and model artifacts are intentionally excluded from
Git.
