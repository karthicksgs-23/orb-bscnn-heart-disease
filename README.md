# ORB-BSCNN for Heart Disease Diagnosis

Code for the manuscript "Does Graph Structure Help Tabular Clinical
Prediction? A Controlled Evaluation of Binarized Simplicial Networks for
Heart Disease Diagnosis".

## Files

| Notebook | Reproduces | Runtime |
|---|---|---|
| `ORB_BSCNN_OptionB.ipynb` | Table 2 and Tables 8–11: Cleveland and cardiovascular-cohort results for all models (ORB-BSCNN node and edge-level variants, no-triangle ablation, random-graph and empty-graph controls, GCN, GAT, XGBoost, MLP, Random Forest, logistic regression), nested selection of τ, corrected resampled t-tests, and the parameter counts of the edge-level, GCN and GAT models in Table 5 | Cleveland: CPU, about 30–60 min. Cardiovascular cohort: NVIDIA T4 GPU, about 1–2 h |
| `ORB_BSCNN_Reproducible.ipynb` | Table 1 and Tables 3–7: sample records, hyperparameter sweep, correlation-threshold ablation, efficiency (Table 5), pooled four-site and leave-one-site-out evaluation, plus the component ablations in Section 4.2 | CPU |
| `PTBXL_ORB_BSCNN.ipynb` | Supplementary Section S1 (preliminary PTB-XL ECG experiment, Table S1 and Figure S1) | GPU recommended |

A fixed random seed is set for every model in every fold.

## How to run

1. Open a notebook in Google Colab and choose Runtime > Run all.
2. `ORB_BSCNN_OptionB.ipynb`:
   - For the cardiovascular cohort, select a T4 GPU (Runtime > Change
     runtime type) and upload a Kaggle API token (`kaggle.json`, from
     Kaggle > Settings > API > Create New Token) when the notebook asks.
   - `RUN_CLEVELAND` and `RUN_LARGE` let you run the two datasets in
     separate sessions. Set `QUICK_TEST = True` for a short end-to-end
     check.
   - Results are saved to `ORB_BSCNN_optionB_results.xlsx`.
3. `ORB_BSCNN_Reproducible.ipynb` saves its tables to
   `ORB_BSCNN_results.xlsx`.

## Data

The notebooks download the data directly; no data files are stored here.

- UCI Heart Disease (Cleveland and the four-site collection):
  https://doi.org/10.24432/C52P4X
- Cardiovascular Disease dataset (Kaggle, 70,000 records; 68,608 remain
  after the plausibility filters in the notebook):
  https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset
- PTB-XL: https://physionet.org/content/ptb-xl/1.0.3/

## Software versions used

Python 3.13, PyTorch 2.11.0 (CUDA 13.0 for the GPU runs), scikit-learn
1.6.1, XGBoost 3.4.1, NumPy 2.1.3, pandas 2.2.3, NetworkX 3.7, SciPy 1.16.3.

AUC values of the neural models can differ by up to about 0.01 across
library versions and platforms (CPU vs. GPU).
