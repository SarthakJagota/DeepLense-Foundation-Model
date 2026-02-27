DeepLense Foundation Model

This repository presents a foundation-style learning pipeline for gravitational lensing image analysis using deep learning.
The work explores how representation learning improves dark matter substructure detection by combining unsupervised and supervised objectives and evaluating transfer to downstream scientific tasks.

🔬 Overview

The project investigates three stages of representation learning:

Autoencoder Pretraining
A convolutional autoencoder is trained to learn structural features from lensing images.

Supervised Baseline
A ResNet18 classifier establishes a reference performance for lens classification.

Multi-task Foundation Model
A shared encoder is trained jointly for reconstruction and classification, improving representation quality and downstream performance.

Experiments demonstrate that the learned encoder transfers effectively to downstream regression tasks, supporting its role as a reusable scientific representation.

📊 Key Results

Autoencoder reconstruction achieves low loss but weak discriminative performance (~0.34 accuracy).

Supervised baseline reaches ~0.62 validation accuracy.

Multi-task foundation model improves performance (~0.68 accuracy).

Macro AUC improves from ~0.81 → ~0.85.

ROC analysis shows consistent gains across substructure classes.

These results indicate stronger learned representations through multi-task learning.

📈 Downstream Regression & Representation Transfer

To evaluate whether the learned encoder generalizes beyond classification, it was transferred to a multi-parameter regression task using the DeepLense regression dataset.

Ablation experiments compared:

A frozen pretrained multitask encoder

A randomly initialized frozen encoder

Findings

The pretrained encoder substantially improves prediction accuracy across key physical parameters including Einstein radius, source position, ellipticity, and shear magnitude.

The largest performance gap appears in complex parameters such as shear angle, indicating that learned representations capture meaningful lens morphology while highlighting limitations related to periodic parameter estimation.

This demonstrates that multitask pretraining produces reusable scientific features rather than task-specific classification features.

📊 Pretrained vs Random Encoder

The figure below shows per-parameter Mean Absolute Error (MAE):

<img width="714" height="434" alt="Screenshot 2026-02-27 213419" src="https://github.com/user-attachments/assets/5b584ec7-9ec1-4c1d-b052-bb88f66b404b" />

Pretraining consistently reduces error across all parameters, confirming effective representation transfer.

**🧠 Representation Insight

Reconstruction alone captures morphology but not class separability.

Supervised learning improves discrimination.

Multi-task learning balances structural preservation and classification, producing richer features.

Transfer experiments confirm the encoder learns physically meaningful representations useful for parameter estimation.**

⚠ Limitations

Pretraining objectives are not explicitly aligned with physical parameter estimation.

Orientation/shear angle prediction exhibits periodic ambiguity.

Simulation-to-real domain gaps remain an open challenge.

🚀 Future Directions

Physics-aware pretraining for regression of lens parameters

Domain adaptation from simulations to real observations

Unsupervised anomaly detection for theory-agnostic discovery

Masked autoencoder and contrastive pretraining

Transformer-based backbones for improved representation learning

🛠️ Tech Stack

PyTorch

ResNet18 backbone

Autoencoder architectures

Multi-task learning

Regression evaluation (MAE)

ROC/AUC evaluation (scikit-learn)

GPU training

📌 Motivation

Strong gravitational lensing provides a powerful probe of dark matter substructure.
This project explores how foundation-style encoders can support multiple scientific tasks beyond classification, enabling reusable representations for astrophysical discovery.

📬 Contact

Created as part of ML4Sci / DeepLense research exploration.
Author: Sarthak Jagota
