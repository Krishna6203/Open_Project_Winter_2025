# Open Project Winter 2025  
## Machine Learning Quantum State Tomography (ML-QST)

---

## 📌 Project Overview

This project explores **Machine Learning based Quantum State Tomography (ML-QST)** for reconstructing quantum density matrices from measurement outcomes.  
The repository consolidates work completed across multiple assignments into a structured and reproducible research workflow.

The objective is to evaluate:

- Reconstruction fidelity
- Trace distance accuracy
- Runtime scaling behaviour

The project focuses primarily on **single-qubit quantum state reconstruction** under different noise channels.

---

## 🧠 Problem Statement

Traditional Quantum State Tomography scales poorly with system size due to exponential measurement requirements.  
This work investigates whether supervised machine learning models can learn mappings from measurement vectors to density matrices efficiently.

Key goals:

- Improve reconstruction efficiency
- Evaluate performance under noisy quantum channels
- Study scalability trends

---

## ⚙️ Methodology

### 1️⃣ Dataset Preparation

Datasets are located inside:


Each quantum state includes:

- Measurement outcomes (`*_meas.json`)
- True density matrices (`*_rho.npz`)
- Metadata and processed numpy arrays

Noise channels used:

- Ideal measurements
- Amplitude damping (ad0.2)
- Depolarizing noise (depol0.1)

---

### 2️⃣ Training Pipeline

Core source code is implemented in:


Main modules:

generate_data.py → Dataset preparation
model.py → ML reconstruction model
train.py → Training pipeline
test.py → Evaluation
generate_vcd.py → Additional result generation


---

### 3️⃣ Experiments and Notebooks

Experiment notebooks:

notebooks/Assignment_1.ipynb
notebooks/Assignment_3.ipynb


These notebooks perform:

- Model training
- Evaluation
- Ablation studies
- Plot generation

---

### 4️⃣ Models

Stored in:

models/


Included checkpoints:

model_demo_2.pkl
task2_model_2q.pkl
model_weights.pt


---

### 5️⃣ Evaluation Metrics

#### Fidelity
Measures similarity between reconstructed density matrix and ground truth.

#### Trace Distance
Quantifies reconstruction error.

#### Runtime Scaling
Evaluates computational cost with increasing complexity.

---

## 📊 Results

All plots are stored in:

results/plots/


Key visualizations:

- fidelity_vs_qubits.png
- runtime_vs_qubits.png
- ablation_fidelity_vs_k.png
- ablation_runtime_vs_k.png

Tables are stored in:

results/tables/

Including:

single_qubit_summary.csv
validation_report.csv

---

## 📂 Repository Structure

Open_Project_Winter_2025/
│
├── data/ Quantum datasets
├── models/ Trained ML-QST checkpoints
├── notebooks/ Assignment notebooks
├── src/ Modular Python pipeline
├── results/
│ ├── plots/
│ └── tables/
├── docs/ Reports and replication guide
├── AI_usage.md
├── requirements.txt
└── README.md

---

## ▶️ Reproducibility

Install dependencies:

```bash
pip install -r requirements.txt

python src/train.py

python src/test.py

## 🧠 Reflection

During scaling experiments, runtime increased non-linearly with system size, indicating computational bottlenecks in density matrix reconstruction. While fidelity remained high for single-qubit datasets, extending to higher-dimensional systems will require optimized architectures and possibly hybrid quantum-classical approaches.

Future improvements:
- Transformer-based reconstruction models
- Dimensionality reduction of measurement vectors
- Efficient training pipelines for multi-qubit states
