# Quantum Convolutional Neural Networks with Hamiltonian Embedding and Ancillary Qubits

This repository presents a novel quantum machine learning framework for image classification, integrating Quantum Convolutional Neural Networks (QCNNs) with Hamiltonian embedding and ancillary qubit enhancement.

> “Quantum ML meets deep image understanding: This work brings together the physics-inspired Hamiltonian encoding and quantum convolution with ancilla qubits to push the limits of quantum image classification.”

---

## 📌 Overview

Traditional QCNNs often struggle with representing complex image data under NISQ constraints. This project addresses those limitations through:

- 🧠 Hamiltonian embedding: Encodes classical images into quantum states with enhanced spatial structure retention.
- ➕ Ancillary qubits: Increase representational capacity without significantly deepening circuits.
- 🧱 Quantum convolution: Localized quantum operations over qubit regions emulate classical convolutions.
- 📉 Adaptive pooling & hybrid training: Optimized quantum state reduction and classical gradient descent.
- ⚙️ Noise mitigation: Resilience to noise via simulated decoherence-aware training and shallow circuit design.

---

## 🧪 Datasets

Evaluated across 4 benchmark datasets:

| Dataset           | Image Size | Classes | Train | Val | Test |
|------------------|------------|---------|-------|-----|------|
| Kaggle CT Scans  | 32×32      | 2       | 75    | 5   | 20   |
| SKlearn Digits   | 8×8        | 8       | 1040  | 130 | 130  |
| MNIST (0–7)      | 32×32      | 8       | 45,790| 2410| 8017 |
| FashionMNIST (0–7)| 32×32     | 8       | 45,600| 2400| 8000 |

---

## 🏗️ Architecture

The model integrates the following modules:

1. Hamiltonian Embedding:
   - Constructs Hermitian matrices from images: 
     HM = (M + Mᵀ)/2
   - Applies unitary evolution: W(t;M) = e^{-iHM t/2}

2. Ancillary Qubit Enhancement:
   - Introduces |0⟩ ancilla qubits
   - Interacts with data qubits using controlled unitaries to expand Hilbert space

3. Quantum Convolution:
   - Applies Uj(θ) gates over localized qubit patches
   - Emulates classical convolution using quantum operations

4. Adaptive Pooling:
   - Measurement-based pooling reduces qubit usage while preserving key features

5. Hybrid Optimization:
   - Combines quantum evolution with classical training (cross-entropy loss, natural gradient descent, layer-wise pretraining)

---

## 🔬 Experimental Results

| Model                   | Kaggle CT | SKlearn | MNIST | Fashion |
|------------------------|-----------|---------|--------|---------|
| Classical CNN          | 85.0%     | 97.7%   | 98.9%  | 89.3%   |
| Standard QCNN          | 76.5%     | 92.3%   | 94.1%  | 82.5%   |
| QNN (no conv, no ancilla)| 72.0%    | 89.2%   | 91.8%  | 78.4%   |
| Hamiltonian-QNN        | 80.5%     | 94.6%   | 95.7%  | 84.1%   |
| Ours (Full Model)      | 82.5%     | 96.2%   | 97.2%  | 86.7%   |

✅ Our model consistently outperforms baseline quantum models while approaching classical CNN performance, especially on smaller datasets.

---

## 🔧 Implementation Details

- Quantum Libraries: Qiskit, PennyLane
- Classical Backend: PyTorch
- Hardware: IBM-Q Eagle 127-qubit processor (for smaller instances)
- Simulation: Device-calibrated noise models
- Batch Sizes: 16–32 samples
- Optimizer: Quantum Natural Gradient Descent
- Training: 100 epochs with early stopping

---

## 📈 Ablation Study

Key findings:

| Removed Component        | Accuracy Drop |
|-------------------------|----------------|
| No Convolution          | ↓ 5.7%         |
| No Hamiltonian Embedding| ↓ 3.1%         |
| No Ancillary Qubits     | ↓ 1.4%         |
| No Layer-wise Pretrain  | ↓ 0.8%         |

🧩 The convolutional structure and Hamiltonian embedding contribute most to performance gains.

---

## 🛡️ Noise Robustness

- Model shows only 5.2% degradation at 10⁻³ gate error rate (typical for NISQ)
- Outperforms other quantum models under same conditions
- Includes error detection circuits and noise-aware training

---

## 📚 Citations

If you use this work, please cite:

```bibtex
@article{talha2025quantumcnn,
  title={Quantum Convolutional Architectures for Image Classification: A Hamiltonian-Embedded Approach with Ancillary Qubits},
  author={Muhammad Talha Shaikh, Muhammad Hamza, Syed Bilal Ali, Sumaiyah Zahid, Muhammad Rafi},
  journal={FYP II Report, FAST-NUCES},
  year={2025}
}
```
##Structure
quantum_cnn_project/
├── ct-med-img/                # Preprocessed datasets
├── sklearn-digits-dataset/            # Qiskit & PennyLane circuit files
├── mnist/              # Architecture & training scripts
├── fashion-mnist/             # Experimental outputs & plots
├── README.md            # Project documentation


This project was conducted as a Final Year Project at FAST-NUCES Karachi.


