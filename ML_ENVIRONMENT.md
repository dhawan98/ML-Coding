# Roblox classic-ML notebook environment

This workspace uses Python 3.11 in `.venv`. It contains the packages required by
the Titanic workbook plus a compact general-purpose classic-ML stack. It does
not include TensorFlow, PyTorch, or other deep-learning frameworks.

## Use it from Terminal

From this folder:

```sh
source .venv/bin/activate
jupyter lab
```

Open `Roblox_ML_Interview_Titanic_Guided.ipynb`. If Jupyter asks for a kernel,
choose **Python (Roblox Classic ML)**.

When finished:

```sh
deactivate
```

## Use it in VS Code or another notebook editor

Open any `.ipynb`, choose **Select Kernel**, then select either:

- **Python (Roblox Classic ML)**, or
- the interpreter at `.venv/bin/python`.

The selected kernel is saved in the notebook metadata. New notebooks can use
the same kernel; you do not need a new environment per notebook.

## Recreate or update the environment

The human-edited package list is `requirements-ml.in`; the generated lock file
is `requirements-ml.lock`. To recreate the exact environment:

```sh
uv venv --python 3.11 .venv
uv pip sync --python .venv/bin/python requirements-ml.lock
.venv/bin/python -m ipykernel install --sys-prefix \
  --name roblox-classic-ml --display-name "Python (Roblox Classic ML)"
```

After intentionally changing `requirements-ml.in`, regenerate and apply the
lock file:

```sh
uv pip compile requirements-ml.in -o requirements-ml.lock
uv pip sync --python .venv/bin/python requirements-ml.lock
```

To install one temporary package without changing the shared package list:

```sh
uv pip install --python .venv/bin/python PACKAGE_NAME
```

If the package should be part of the reusable environment, add it to
`requirements-ml.in` and regenerate the lock instead.

From inside a notebook, `%pip install PACKAGE_NAME` also installs into the
currently selected kernel. Treat that as temporary unless you also add the
package to `requirements-ml.in`.
