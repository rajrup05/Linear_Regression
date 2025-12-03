# Linear_Regression

This project processes and analyzes an employee dataset using preprocessing, visualization, and classification methods implemented inside `notebook.ipynb`.
It supports execution in **Google Colab**, **locally**, and **VS Code with a Colab backend**.

---

## Features

* Load and prepare employee dataset
* Handle categorical & numerical attributes
* Normalize features
* Train classification models
* Notebook-driven workflow

---

## Repository Structure

```
.
├── notebook.ipynb
├── requirements.txt
└── data/
    └── Employee_Data.csv
```

---

# 1. Running in Google Colab (Recommended)

Colab runs remotely and therefore **cannot access files on your local machine**.
Your CSV must be uploaded manually, placed in Google Drive, or stored inside your GitHub repo.

You have three options:

---

## Option A — Manual Upload

Upload the CSV each session:

```python
from google.colab import files
uploaded = files.upload()
```

Then:

```python
import pandas as pd
df = pd.read_csv('Employee_Data.csv')
```

---

## Option B — Use Google Drive

Place your file here:

```
My Drive/datasets/Employee_Data.csv
```

Mount Drive:

```python
from google.colab import drive
drive.mount('/content/drive')

df = pd.read_csv('/content/drive/MyDrive/datasets/Employee_Data.csv')
```

---

## Option C — Clone Your GitHub Repo (Best for VS Code + Colab as well)

If you add your CSV to the repo:

```
data/Employee_Data.csv
```

Then in Colab:

```python
!git clone https://github.com/<your-username>/<your-repo>.git
%cd <your-repo>

df = pd.read_csv('data/Employee_Data.csv')
```

This completely avoids Drive and repeated uploads.

---

# 2. Running Locally (Jupyter or VS Code)

Local execution **can** access files on your machine normally.

## Install dependencies

```bash
pip install -r requirements.txt
```

Or:

```
pandas
numpy
scikit-learn
matplotlib
seaborn
```

## Launch Jupyter

```bash
jupyter notebook
```

Open `notebook.ipynb` and run normally.

Your file path can simply be:

```python
df = pd.read_csv('data/Employee_Data.csv')
```

---

# 3. Running in VS Code Using a Google Colab Server

This lets you code in VS Code while using Colab’s compute resources (CPU/GPU/TPU).

Even though the UI is VS Code, the runtime is **still Colab**, meaning:

**Colab cannot access your local machine’s files.**

You must provide the dataset via:

* Google Drive
* Manual upload
* GitHub repo (recommended)

---

## Steps

1. Install VS Code extension: **Google Colab**
2. Open `notebook.ipynb`
3. Command Palette → **Connect to Google Colab**
4. Authenticate
5. Choose runtime (CPU / GPU / TPU)
6. Run cells with Colab as backend

You get Colab hardware acceleration without leaving VS Code, **but local file access is not available**.

Expected location (recommended):

```
data/Employee_Data.csv
```

This structure ensures Colab + GitHub cloning works cleanly.

---
