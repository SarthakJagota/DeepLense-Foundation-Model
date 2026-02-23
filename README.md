# DeepLense Foundation Model

This repository presents a foundation-style learning pipeline for gravitational lensing image analysis using deep learning.  
The work explores how representation learning improves dark matter substructure detection by combining unsupervised and supervised objectives.

---

## 🔬 Overview

The project investigates three stages of representation learning:

1. **Autoencoder Pretraining**  
   A convolutional autoencoder is trained to learn structural features from lensing images.

2. **Supervised Baseline**  
   A ResNet18 classifier establishes a reference performance for lens classification.

3. **Multi-task Foundation Model**  
   A shared encoder is trained jointly for reconstruction and classification, improving representation quality and downstream performance.

The learned encoder is designed to be reusable for future astrophysical tasks such as regression and super-resolution.

---

## 📊 Key Results

- Autoencoder reconstruction achieves low loss but weak discriminative performance (~0.34 accuracy).
- Supervised baseline reaches ~0.62 validation accuracy.
- Multi-task foundation model improves performance (~0.68 accuracy).
- Macro AUC improves from ~0.81 → ~0.85.
- ROC analysis shows consistent gains across substructure classes.

These results indicate stronger learned representations through multi-task learning.

---

## 🧠 Representation Insight

- Reconstruction alone captures morphology but not class separability.
- Supervised learning improves discrimination.
- Multi-task learning balances structural preservation and classification, producing richer features.
- The shared encoder demonstrates characteristics of a reusable foundation model.

---

## 🚀 Future Directions

- Regression for estimating physical lens parameters
- Domain adaptation from simulations to real observations
- Unsupervised anomaly detection for theory-agnostic discovery
- Masked autoencoder and contrastive pretraining
- Transformer-based backbones for improved representation learning

---

## 🛠️ Tech Stack

- PyTorch
- ResNet18 backbone
- Autoencoder architectures
- ROC/AUC evaluation (scikit-learn)
- GPU training

---

## 📌 Motivation

Strong gravitational lensing provides a powerful probe of dark matter substructure.  
This project explores how foundation-style encoders can support multiple scientific tasks beyond classification.

---

## 📬 Contact

Created as part of the ML4Sci / DeepLense research exploration.

