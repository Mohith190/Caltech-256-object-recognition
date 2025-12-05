Caltech-256: Supervised & Unsupervised Learning

This project compares two image learning approaches on the Caltech-256 dataset: Fractal-Regularized Latent Manifold Learning (FRLM) and a highly optimized ResNet-50 supervised baseline.

🧠 Approach 1: Unsupervised Learning (FRLM)
Model: Custom Convolutional Autoencoder (AE).
Goal: Learn high-quality feature representations by enforcing a specific fractal dimension (D_target = 2.5) in the latent space.
Key Innovation: Uses a Differentiable Fractal Loss based on a soft-counted correlation sum, combined with standard MSE Reconstruction Loss.
Evaluation: The quality of the learned features is assessed via linear probing (training a linear classifier on the frozen AE encoder output).

💻 Approach 2: Supervised Learning (Baseline)
Model: ResNet-50 (trained end-to-end).
Goal: Establish the performance ceiling for full 256-class classification accuracy using state-of-the-art training techniques.
Optimization Details - The ResNet-50 training was optimized for performance and stability using the following techniques:FixRes (Fixed-Resolution Training): The model was trained at one resolution and fine-tuned/evaluated at a slightly higher one for improved generalization.Mixed Precision Training: Utilized half-precision floating-point numbers (FP16) for faster training and reduced memory consumption.
Loss Function: Optimized using Cross-Entropy Loss with Label Smoothing to prevent over-confidence and improve robustness.

