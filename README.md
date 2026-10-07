# ORB-BSCNN for Heart Disease Diagnosis

Code for the manuscript "Efficient Heart Disease Diagnosis in Healthcare
Environments through an Optimized Adaptive Residual Binarized Simplicial
Convolutional Neural Network for Clinical Decision Support".

## Files

- `ORB_BSCNN_Reproducible.ipynb`: reproduces all UCI Heart Disease results
  in the paper (repeated 5-fold cross-validation, ablations, significance
  tests, threshold and hyperparameter analyses, pooled multi-site and
  leave-one-site-out evaluation). A fixed random seed is set for every
  model in every fold.
- `PTBXL_ORB_BSCNN.ipynb`: preliminary PTB-XL ECG experiment.

## How to run

1. Open `ORB_BSCNN_Reproducible.ipynb` in Google Colab.
2. Choose Runtime > Run all. The notebook runs on CPU.
3. All tables are saved to `ORB_BSCNN_results.xlsx`.

## Data

The notebooks download the data directly; no data files are stored here.

- UCI Heart Disease: https://doi.org/10.24432/C52P4X
- PTB-XL: https://physionet.org/content/ptb-xl/1.0.3/

## Software versions used

Python 3.13, PyTorch 2.11.0, scikit-learn 1.6.1, NumPy 2.1.3,
pandas 2.2.3, NetworkX 3.7, SciPy 1.16.3.
