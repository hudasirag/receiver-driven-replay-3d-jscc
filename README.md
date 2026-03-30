# Receiver-Driven Replay Protocol for 3D Point Cloud JSCC

This repository contains the implementation of a receiver-driven replay protocol for learned 3D point cloud joint source-channel coding (JSCC). The framework performs round-0 base decoding, self-consistency-based replay decision, and round-1 replay residual refinement.

## Overview

The proposed protocol operates in three stages:

1. **Round-0 base decoding**  
   A mandatory base subset of latent tokens is transmitted to obtain an initial reconstruction.

2. **Replay decision**  
   A receiver-side self-consistency estimator predicts a replay score and triggers a one-bit ACK/NACK decision.

3. **Round-1 replay residual refinement**  
   If replay is requested, additional replay information is used to refine the round-0 reconstruction through residual correction.

## Repository Structure

```text
receiver-driven-replay-3d-jscc/
├── models/          # Teacher model, replay model, SC-head
├── utils/           # Utility functions and evaluation helpers
├── scripts/         # Training and evaluation scripts
├── configs/         # Optional configuration files
├── figures/         # Optional figures for documentation
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
└── CITATION.cff
Environment

The codebase is implemented in Python with PyTorch.
Main dependencies
- Python 3.9+
- PyTorch 1.13.0
- NumPy
- SciPy
- Open3D
- Matplotlib
- h5py
- tqdm
- scikit-learn

Install dependencies with:

pip install -r requirements.txt

Datasets
Experiments in the paper use:
- ShapeNet
- ShapeNetPart
- KITTI
- 8iVFB
