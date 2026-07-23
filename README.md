## Project title

**Improving Temporal Dynamics in a Sora 2-Inspired Video Diffusion Model Using Physics-Consistency Auxiliary Loss**

**Module:** CMP030L043 Deep Learning and Generative AI  
 

## Purpose of this artefact


The project implements a reproducible proxy experiment for the Part 1 proposal. Because Sora 2 is proprietary and its full architecture, weights, training data and objective are not disclosed, this artefact does not reproduce Sora 2 directly. Instead, it evaluates the proposed **Physics-Consistency Auxiliary Loss (PCAL)** using a lightweight conditional video diffusion model trained on synthetic bouncing-ball videos.


## Main implementation details

- **Dataset:** Synthetic bouncing-ball video sequences.
- **Task:** Conditional future-frame video generation.
- **Baseline:** Conditional diffusion denoiser trained with standard noise-prediction loss.
- **Proposed extension:** PCAL temporal acceleration regulariser.
- **Objective:**

```text
L_total = L_noise + lambda * L_PCAL
```

- **Ablation values:** lambda = 0, 0.01, 0.05, 0.10, 0.25.
- **Evaluation:** future-frame MSE/MAE/PSNR, global SSIM proxy, position error, velocity error, acceleration error, boundary-violation rate, runtime.

## How to reproduce

1. Open `Part2.ipynb` in Google Colab.
2. Select **Runtime → Change runtime type → GPU**.
3. Run **Runtime → Run all**.
4. The notebook will generate the dataset, train all baseline/PCAL models, save CSV metrics, save figures and save checkpoints.

