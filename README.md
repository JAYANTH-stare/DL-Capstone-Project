This project introduces a robust and invisible watermarking system built using convolutional autoencoders. It includes:

A Watermark Embedding Network (Hider) that hides a watermark inside a cover image while keeping the image visually unchanged.

A Watermark Recovery Network (Revealer) that reconstructs the hidden watermark from the watermarked image.

A Clean-Image Autoencoder trained to identify whether an image contains a watermark based on reconstruction error.

The system is fully blind, meaning it does not require access to the original cover image during detection.

⭐ Key Features

✔ Invisible watermark embedding (high PSNR & SSIM)

✔ Watermark recovery using a decoder

✔ Blind watermark detection using autoencoder reconstruction error

✔ Automatic threshold generation (mean + 2×std)

✔ Robustness evaluation (compression, noise, resizing, etc.)

✔ End-to-end pipeline from embedding to detection

🧠 System Architecture
1. Watermark Embedding & Recovery

Takes a cover image + watermark image

Produces a visually identical watermarked image

Recovers watermark using a decoder

2. Autoencoder-Based Detection

Trained only on clean images

Learns natural data distribution

During detection:

Clean images → low MSE

Watermarked images → high MSE

Decision = MSE > threshold ? watermarked : clean

🔍 Workflow Diagram
Cover Image + Watermark → Hider → Watermarked Image → Revealer → Recovered Watermark

Clean Images → Autoencoder (trained)
Test Image → Autoencoder → Reconstructed Image → Compare MSE → Detection

📂 Dataset

This project uses the CelebA dataset, which contains:

202,599 aligned face images

Consistent structure ideal for autoencoder training

Large volume helps the model learn reliable clean-image reconstruction

📊 Results
✔ Watermark Embedding

PSNR of watermarked vs. cover image: 28–35 dB

Watermarked images visually identical to cover images

Recovered watermark recognizable

✔ Detection Accuracy

Clean images: MSE ≈ 0.0008 – 0.0025

Watermarked images: MSE ≈ 0.0055 – 0.0118

Perfect separation with threshold ≈ 0.00304

100% detection in experiments

✔ Visual Results

(You can add your sample output images here)

🔮 Future Work

Improve watermark recovery quality

Add support for multiple watermarks

Extend system to video watermarking

Integrate blockchain for secure ownership tracking

Build a GUI/web interface for easier use
