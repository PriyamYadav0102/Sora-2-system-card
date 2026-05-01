# Sora 2 Physics-Consistency Auxiliary Loss

This project implements a small video prediction model in PyTorch and evaluates whether a Physics-Consistency Auxiliary Loss (PCAL) can improve temporal smoothness in predicted frame sequences.

## Overview

The notebook trains two ConvLSTM-based models on a synthetic Moving MNIST-style dataset:
- a **baseline model** trained with reconstruction loss only,
- a **proposed model** trained with reconstruction loss plus PCAL.

The goal is to compare motion quality, temporal consistency, and reconstruction performance between the two models [file:189].

## Requirements

Install the required packages with:

```bash
pip install torch numpy pandas matplotlib
```

## Dataset

The notebook uses a synthetic Moving MNIST-style dataset generated inside the notebook itself, so no external dataset download is required [file:189].

## Notebook Workflow

1. Install packages.
2. Set imports and random seeds.
3. Generate the synthetic motion dataset.
4. Define the ConvLSTM model.
5. Define reconstruction loss and PCAL.
6. Train the baseline model.
7. Train the proposed model.
8. Compare results.
9. Visualise predicted sequences.
10. Save outputs [file:189].

## Model

The model is a ConvLSTM-based video predictor that takes the first 5 frames of each sequence as input and predicts the next 5 frames [file:189].

## Loss Functions

The notebook uses:
- **Reconstruction loss**: Mean Squared Error.
- **PCAL**: A temporal acceleration-based penalty that discourages abrupt motion changes [file:189].

## Training Setup

- Sequence length: 10 frames.
- Input length: 5 frames.
- Prediction length: 5 frames.
- Batch size: 16.
- Learning rate: 1e-3.
- Epochs: 1 in the notebook run shown.
- PCAL weight: 0.0 for baseline, 0.1 for proposed model [file:189].

## Outputs

The notebook saves:
- `baseline_results.csv`
- `proposed_results.csv`
- `baseline_model.pt`
- `proposed_model.pt` [file:189].

It also visualises predicted frame sequences for both models [file:189].

## Results Comparison

The notebook reports lower training and validation loss for the proposed model, with slightly different temporal consistency and motion smoothness values compared with the baseline [file:189].

## How to Run

Open the notebook in Google Colab and run the cells in order. The final cells train both models, compare results, and save the outputs [file:189].

## Notes

- The dataset is synthetic and generated within the notebook.
- The project is intended as a proof of concept.
- You can increase `lambda_pcal` to strengthen the physics-consistency penalty [file:189].
