# Garbage Classification and Softmax Confidence Analysis

This project evaluates a MobileNetV2 garbage classification model under two experimental protocols and investigates whether maximum softmax confidence can distinguish waste tiles from background tiles.

## Experiments

### 1. Baseline experiment
**Notebook:** `01_Baseline_Garbage_Classification.ipynb`

- Garbage classification using the original train/test split.
- Model evaluation using accuracy and macro-F1.
- TACO tile-based waste/background confidence analysis.

### 2. Duplicate-aware experiment
**Notebook:** `02_Duplicate_Aware_MobileNetV2_Evaluation.ipynb`

- Duplicate-aware dataset splitting.
- MobileNetV2 transfer learning and fine-tuning.
- Held-out test evaluation and inference latency.
- TACO tile-based waste/background confidence analysis.

## Preliminary findings

- Duplicate-aware model test accuracy: 95.41%.
- Duplicate-aware model test macro-F1: 0.9336.
- Correct-versus-wrong confidence AUROC: 0.938.
- TACO waste-versus-background confidence AUROC: 0.483 in the exploratory tile sample.

These results concern different evaluation tasks. The two dataset-splitting protocols should not be compared as a controlled improvement unless other experimental settings are kept consistent.

## Datasets

- [Garbage Classification — Kaggle](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)
- [TACO — Trash Annotations in Context](https://github.com/pedropro/TACO)

## Limitations

The TACO tile experiment uses a small manually labeled sample. Tiles from the same photograph may be correlated, and maximum softmax confidence is not a calibrated probability that a tile contains waste.
