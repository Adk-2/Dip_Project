# Dip_Project

Here's a clean, professional, and informative **README.md** file for your project:

---

# 🧠 Medical,satelight Image Denoising using Python

This project demonstrates the application of **advanced image denoising techniques** on real noisy medical images (e.g., X-rays with motion blur, Gaussian noise, and quantum noise). It compares multiple algorithms for effectiveness on different types of noise.

## 📂 Project Overview

Medical, satelite images are often degraded due to various types of noise—**Gaussian**, **quantum**, or **motion blur**—which can negatively impact diagnostic accuracy. This Python script showcases four denoising techniques applied to real noisy medical X-ray images:

* 🧩 **Non-Local Means (NLM)** – Great for quantum/random noise.
* 🔍 **BM3D** – State-of-the-art for Gaussian noise.
* 🌊 **Wavelet Denoising** – Preserves fine structures.
* 🚗 **Wiener Filtering** – Effective for motion blur.

---

## 🧪 Denoising Techniques Used

### 1. 📍 Non-Local Means (NLM)

* Works by averaging similar patches across the image.
* Suitable for random/quantum noise.
* Parameters:

  * `patch_size=5`
  * `patch_distance=6`
  * `h = 1.15 * sigma_est` (noise strength)

### 2. 📍 BM3D (Block-Matching and 3D Filtering)

* One of the most powerful denoising methods for Gaussian noise.
* Uses collaborative filtering in a transform domain.
* Profiled using `BM3DProfile()`

### 3. 📍 Wavelet Denoising

* Uses wavelet transforms to remove noise while retaining image edges.
* Performs well with low noise and structured content.
* Mode: `soft` thresholding

### 4. 📍 Wiener Filtering

* Works based on frequency domain filtering.
* Ideal for **motion blur** artifacts.
* Uses a simple point spread function (PSF) as a motion kernel.

---

## 🖼 Example Input Images

The code handles three types of noisy medical X-ray images:

* `xray_motion_blur.png`
* `xray_gaussian_noise.png`
* `xray_quantum_noise.png`

> All images are resized to **256x256** and normalized to `[0, 1]` for processing.

---

## 📦 Requirements

Install the required packages before running the script:

```bash
pip install opencv-python numpy matplotlib scikit-image bm3d
```

---

## 🚀 How to Run

Each denoising script processes a specific image:

```bash
# For motion blur image
python denoise_motion_blur.py

# For Gaussian noise image
python denoise_gaussian.py

# For quantum/random noise image
python denoise_quantum.py
```

> Replace the filenames as needed or use the unified script.

---

## 📊 Output

Each script displays:

1. Original noisy image
2. Denoised versions using:

   * NLM
   * BM3D
   * Wavelet
   * Wiener

Sample visualization (output via `matplotlib`):

```
+------------------+----------------+-----------------+-------------------+-------------------+
| Original Image   | NLM Denoised   | BM3D Denoised   | Wavelet Denoised  | Wiener Filtered   |
+------------------+----------------+-----------------+-------------------+-------------------+
```

---

## 📌 Notes

* **Noise Estimation** is done using `estimate_sigma()` from `skimage`.
* `psf = np.ones((1, 15)) / 15` is used to simulate horizontal motion blur for Wiener filtering.
* Wiener filtering may not perform well on Gaussian/quantum noise.
* BM3D typically gives the best results for **Gaussian** noise.

---

## 📁 Folder Structure

```
├── denoise_motion_blur.py
├── denoise_gaussian.py
├── denoise_quantum.py
├── xray_motion_blur.png
├── xray_gaussian_noise.png
├── xray_quantum_noise.png
└── README.md
```

---

## 🤝 Acknowledgements

* [scikit-image](https://scikit-image.org/)
* [OpenCV](https://opencv.org/)
* [BM3D Python package](https://pypi.org/project/bm3d/)

---

## 📬 Contact

For questions or collaboration, feel free to open an issue or reach out via email.

---

Would you like me to generate a version with sample outputs using your images (if you upload them)?
