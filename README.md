# Jailbreaking Deep Models: Adversarial Attacks on ImageNet Classifiers

This project explores the vulnerability of deep neural networks to adversarial attacks. We implement and evaluate three types of $L_\infty$ attacks (FGSM, PGD, and Patch-PGD) against a pre-trained ResNet-34 model on a subset of ImageNet. We also investigate the transferability of these attacks to a DenseNet-121 model.

## Summary of Results

**ResNet-34 (White-box Attacks):**
-   **Original:** Top-1: 76.00%, Top-5: 94.20%
-   **FGSM ($\varepsilon=0.02$):** Top-1: 26.40%, Top-5: 50.60%
-   **PGD ($\varepsilon=0.02$, 10 steps):** Top-1: 0.40%, Top-5: 6.80%
-   **Patch-PGD ($\varepsilon=0.5$, $32 \times 32$ patch, 20 steps):** Top-1: 16.40%, Top-5: 39.20%

**DenseNet-121 (Transfer Attacks from ResNet-34):**
-   **Original:** Top-1: 74.80%, Top-5: 93.60%
-   **On FGSM samples:** Top-1: 42.40%, Top-5: 66.40%
-   **On PGD samples:** Top-1: 39.20%, Top-5: 64.00%
-   **On Patch-PGD samples:** Top-1: 43.00%, Top-5: 67.20%

The results demonstrate that iterative attacks like PGD are highly effective in white-box settings but show limited transferability compared to single-step FGSM. Localized patch attacks can also significantly degrade performance even with a larger perturbation budget confined to a small area.
