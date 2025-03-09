# Optimizing Quantum CNN Architectures for Efficient Image Classification

## Overview
This repository contains the code and data related to our research on **Hamiltonian-embedded Quantum Convolutional Neural Networks (QCNNs)** for image classification. The study builds on prior work involving Hamiltonian embedding in Quantum Neural Networks (QNNs) and explores enhancements through QCNN integration and ancillary qubit incorporation.

## Research Progress
### **Phase 1: Hamiltonian-Embedded QNNs**
- Investigated the impact of initialization strategies (Random, Beta, LeCun, He and Ensemble of Lecun and He) on classification performance.
- Evaluated across four datasets: Kaggle CT Medical Images, SKlearn Digits, MNIST, and FashionMNIST.
- Found that Beta initialization significantly improved optimization and generalization.

### **Phase 2: Hamiltonian-Embedded QCNNs**
- Designed and implemented a Quantum Convolutional Neural Network utilizing Hamiltonian embedding.
- Optimized quantum convolutional layers for feature extraction.
- Benchmarking against classical CNNs and Hamiltonian-embedded QNNs is ongoing.

### **Phase 3: Ancillary Qubit Integration**
- Introduced ancillary qubits to enhance state preparation and entanglement propagation.
- Initial results indicate improved classification accuracy.
- Further experiments are in progress to determine optimal configurations.

### **Phase 4: Model Comparison and Performance Evaluation**
- Conducting benchmarking of Hamiltonian-embedded QCNNs against classical CNNs and baseline quantum models.
- Validating improvements in accuracy, efficiency, and scalability across datasets.
- Finalizing documentation and preparing the codebase for public release.

## Repository Structure
```
├── ct-med-img/                # Kaggle CT Medical Images dataset
├── mnist/                     # MNIST dataset
├── fashion-mnist/             # Fashion-MNIST dataset
├── sklearn-digits-dataset/    # SKlearn Digits dataset
├── README.md                  # This document
```
Each dataset directory contains:
- **Code files** for training and evaluation
- **CSV files** with recorded model weights
- **Graphs** illustrating experimental results

## Citation
If you use this work in your research, please cite our paper:
```
@article{shaikh2025hamiltonian-qcnn,
  author    = {Muhammad Talha Shaikh, Muhammad Hamza, Syed Bilal Ali},
  title     = {Optimizing Quantum CNN Architectures for Efficient Image Classification},
  journal   = {Quantum Machine Learning Research},
  year      = {2025},
}
```

## License
This project is licensed under the MIT License.

## Acknowledgments
We acknowledge the support of FAST National University of Computer and Emerging Sciences (NUCES), Karachi, Pakistan, and the contributions of our research team.

