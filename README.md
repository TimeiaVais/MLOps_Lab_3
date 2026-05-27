# MLOps_Lab_3
# 🧠 CIFAR-10 DVC Machine Learning Pipeline

This project demonstrates a complete **Machine Learning pipeline with Data Version Control (DVC)** using the CIFAR-10 dataset.  
It includes data versioning, reproducible training, evaluation, and parameter-driven experiments.

---

# 📌 Project Goal

The goal of this project is to:

- Build a reproducible ML pipeline
- Use DVC for dataset and pipeline versioning
- Train a CNN model on CIFAR-10
- Evaluate model performance using multiple metrics
- Experiment with different dataset chunk configurations

---

# 📊 Dataset

We use the **CIFAR-10 dataset**, which contains:

- 60,000 images
- 10 classes (airplane, car, bird, cat, deer, dog, frog, horse, ship, truck)
- 32x32 RGB images

Dataset is automatically downloaded using `torchvision`.

---

# ⚙️ Pipeline Overview

The pipeline consists of 3 stages:

### 🔹 Stage 1: Data Download
- Downloads CIFAR-10 dataset
- Stores data in `data/raw/`
- Tracked by DVC

---

### 🔹 Stage 2: Training
- Loads dataset chunks dynamically
- Splits into train/validation sets based on `params.yaml`
- Trains CNN model
- Saves best model to `artifacts/`

---

### 🔹 Stage 3: Evaluation
- Loads trained model
- Evaluates on static test set
- Computes metrics:
  - Accuracy
  - Precision
  - Recall
  - F1-score
- Saves results to `metrics/metrics.json`

---

# 📦 Installation

```bash id="i9k2pw"
pip install torch torchvision scikit-learn pyyaml dvc numpy
