# 🖼️ DCT-Based Image Compression Using MATLAB

> A MATLAB-based image compression application that uses the **2-D Discrete Cosine Transform (DCT)** and frequency-domain thresholding to reduce image data while evaluating the trade-off between compression ratio and reconstructed image quality.

**Completed:** 2025
**Project Type:** Academic / Digital Signal Processing
**Language:** MATLAB
**Course:** Digital Signal Processing
**Department:** Computer Engineering


---

## 📌 Overview

This project implements an image compression system using the **Two-Dimensional Discrete Cosine Transform (2-D DCT)**.

The system transforms an image from the spatial domain into the frequency domain, processes the resulting DCT coefficients using thresholding, and reconstructs the image using the **Inverse DCT (IDCT)**.

The project investigates how changing the compression threshold affects:

* Image quality
* Mean Squared Error (MSE)
* Peak Signal-to-Noise Ratio (PSNR)
* Compression ratio

The MATLAB test image **`cameraman.tif`** was used for the experiments.

---

## 🎯 Objectives

The main objectives of the project were to:

* Implement 2-D DCT-based image compression
* Transform image data from the spatial domain to the frequency domain
* Reduce image information using coefficient thresholding
* Reconstruct the compressed image using inverse transformation
* Measure reconstruction quality using MSE and PSNR
* Calculate compression ratios at different threshold levels
* Analyse the trade-off between compression and image quality
* Visualise compression errors using error maps

---

## 🔄 System Architecture

The compression process follows a three-stage pipeline:

```text
Original Image
      ↓
Convert to Double Precision
      ↓
2-D Discrete Cosine Transform
      ↓
DCT Coefficient Thresholding
      ↓
Remove Small Frequency Components
      ↓
Inverse DCT (IDCT)
      ↓
Reconstructed Image
      ↓
Performance Evaluation
```

---

## 🧠 Discrete Cosine Transform

The **Discrete Cosine Transform (DCT)** converts image information from the spatial domain into frequency-domain coefficients.

For natural images, a large amount of the important visual information is concentrated in lower-frequency coefficients. Smaller high-frequency coefficients can therefore be reduced or discarded to achieve compression.

The project uses a 2-D DCT to process the image matrix.

The transformation can be represented as:

```text
D = T × A × Tᵀ
```

where:

* `A` represents the original image matrix
* `T` represents the DCT transformation matrix
* `D` represents the resulting DCT coefficient matrix

MATLAB's DCT-related functionality and transformation matrices were used during implementation.

---

## ⚙️ Compression Method

The project uses **hard thresholding** to reduce the number of significant DCT coefficients.

A threshold `t` is applied to the transformed coefficients. Coefficients below the selected threshold are discarded or reduced, resulting in a sparser representation of the image.

```text
DCT Coefficients
       ↓
Compare with Threshold
       ↓
Small coefficients → Discard
Large coefficients → Keep
       ↓
Inverse DCT
       ↓
Compressed / Reconstructed Image
```

Increasing the threshold produces greater compression but also introduces more reconstruction error.

---

## 🖼️ Test Image

The experiments were performed using MATLAB's standard:

**`cameraman.tif`**

Image dimensions:

```text
256 × 256 pixels
```

The image was converted to double precision before performing the DCT processing.

---

## 📊 Performance Evaluation

Three main metrics were used to evaluate the compression system.

### Mean Squared Error (MSE)

MSE measures the average squared difference between the original and reconstructed images.

A lower MSE indicates that the reconstructed image is closer to the original.

### Peak Signal-to-Noise Ratio (PSNR)

PSNR measures reconstructed image quality based on the MSE.

A higher PSNR generally indicates better reconstruction quality.

### Compression Ratio

The compression ratio compares the amount of original image data with the compressed representation.

A higher compression ratio indicates greater data reduction.

---

## 📈 Experimental Results

The threshold was varied to investigate the relationship between compression and image quality.

| Threshold |      MSE | PSNR (dB) | Compression Ratio |
| --------: | -------: | --------: | ----------------: |
|      0.01 | 0.000089 |     40.52 |            3.82:1 |
|      0.02 | 0.000205 |     36.92 |            5.41:1 |
|      0.05 | 0.000743 |     32.33 |            9.87:1 |
|      0.08 | 0.001561 |     28.11 |           15.75:1 |
|      0.10 | 0.002411 |     26.24 |           20.11:1 |

### Observed relationship

As the threshold increases:

```text
Threshold ↑
    ↓
More coefficients discarded
    ↓
Compression ratio ↑
    ↓
MSE ↑
    ↓
PSNR ↓
    ↓
Image quality ↓
```

This demonstrates the fundamental **compression-quality trade-off** in lossy image compression.

---

## 🖼️ Visual Results

### Low Threshold — t = 0.02

At a threshold of `0.02`, the reconstructed image remains visually close to the original.

The measured performance was:

```text
PSNR:              36.92 dB
Compression Ratio: 5.41:1
```

Only relatively small visual differences are introduced.

### High Threshold — t = 0.08

At a threshold of `0.08`, significantly more frequency components are removed.

The measured performance was:

```text
PSNR:              28.11 dB
Compression Ratio: 15.75:1
```

The reconstructed image shows more noticeable degradation and loss of high-frequency detail.

---

## 🔍 Error Map Analysis

The project also uses an **absolute error map** to visualise differences between the original and reconstructed images.

```text
Original Image
      +
Reconstructed Image
      ↓
Absolute Difference
      ↓
Error Map
```

At lower thresholds, the error map contains relatively small differences.

At higher thresholds, the error becomes more visible because more frequency information has been discarded.

---

## 🧪 Compression Experiment

The project demonstrates how different threshold values affect system performance.

```text
Low Threshold
    ↓
Less information discarded
    ↓
Higher image quality
    ↓
Lower compression

High Threshold
    ↓
More information discarded
    ↓
Lower image quality
    ↓
Higher compression
```

This makes the threshold an important parameter when balancing storage efficiency against reconstructed image quality.

---

## 🛠️ Technologies Used

* **MATLAB**
* 2-D Discrete Cosine Transform (DCT)
* Inverse Discrete Cosine Transform (IDCT)
* Image processing
* Matrix operations
* Frequency-domain analysis
* Thresholding
* MSE
* PSNR
* Compression-ratio analysis

---

## 📂 Repository Contents

```text
Image-Compression-MATLAB/
│
├── README.md
├── Report.pdf
└── screenshots/
    ├── original-image.png
    ├── low-threshold-compression.png
    ├── low-threshold-error-map.png
    ├── high-threshold-compression.png
    ├── high-threshold-error-map.png
    └── performance-results.png
```

> The repository contains the project documentation and screenshots available from the original academic project.

---

## 💡 Key Concepts Demonstrated

This project demonstrates practical knowledge of:

* Digital signal processing
* Image compression
* Transform coding
* Discrete Cosine Transform
* Frequency-domain processing
* Matrix transformations
* Thresholding
* Lossy compression
* Image reconstruction
* Error analysis
* MSE and PSNR
* Compression-ratio evaluation
* MATLAB programming

---

## 📚 References

The project report references work on image quality assessment, JPEG compression, DCT-based image coding, and MATLAB's DCT functionality.

Key references include:

* Wang, Z., Bovik, A. C., Sheikh, H. R., & Simoncelli, E. P. (2004). *Image quality assessment: From error visibility to structural similarity.*
* Wallace, G. K. (1991). *The JPEG still picture compression standard.*
* Santa-Cruz, D., & Ebrahimi, T. (2000). *A study of JPEG 2000 still image coding versus other standards.*
* MathWorks — Discrete Cosine Transform documentation.

---

## 🚀 Future Improvements

Possible improvements include:

* Implementing block-based 8×8 DCT processing
* Adding JPEG-style quantisation matrices
* Supporting user-selected input images
* Adding adjustable compression controls
* Displaying compression results interactively
* Adding PSNR/MSE graphs
* Comparing DCT with DFT and Wavelet-based compression
* Adding side-by-side original and reconstructed image comparison
* Exporting compressed images automatically

---

## 👩‍💻 Project Author

**Naivete Thandiwe Makobe**
BSc Computer Engineering
Computer Engineering Department
