# Assignment 3 – Surrogate Model Scalability and Ablation

## 1. Overview
This assignment studies the scalability and design trade-offs of a surrogate quantum state model. We focus on model serialization, extensibility to n-qubit systems, scalability evaluation, and ablation studies.

## 2. Model and Serialization (Task 1–2)
A reusable surrogate model was implemented to support arbitrary numbers of qubits. Model checkpoints are serialized using Python pickle, storing parameters and metadata such as qubit count and creation time. Atomic writes ensure safe checkpointing.

## 3. Scalability Study (Task 3–4)
Scalability was evaluated by measuring fidelity and runtime as a function of the number of qubits. Fidelity remains constant in a controlled setup, while runtime reflects the exponential growth of the Hilbert space (dimension 2^n). Visualizations summarize these trends.Runtime growth is consistent with the exponential increase in state dimension, even though absolute values remain small for the qubit range tested.

## 4. Ablation Study (Task 5)
An ablation study was performed by varying the effective parameter budget using a low-rank surrogate representation. Results show a clear trade-off between expressivity and computational cost: increasing parameter budget improves fidelity but increases runtime.The ablation isolates representational capacity effects by fixing the target state and varying only the latent dimension.

## 5. Limitations
Experiments were limited to modest qubit counts due to exponential scaling. Runtime trends become more pronounced at higher qubit numbers, and numerical conditioning effects influence least-squares performance.

## 6. Future Work
Future extensions include training-based optimization, classical shadow techniques for scalable measurement, and validation on real quantum hardware or noisy simulators.

