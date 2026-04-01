# Spatial-filtering-chest-xray
Spatial filtering for medical image enhancement – implementing Sobel, Laplacian, and smoothing filters on chest X‑rays

# Spatial Filtering for Medical Image Enhancement

[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/opencv-4.x-green.svg)](https://opencv.org/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sania-abid/spatial-filtering-chest-xray/blob/main/spatial_filtering.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project explores **spatial filtering** techniques for enhancing chest X‑ray images to aid pneumonia detection. It implements both **sharpening filters** (Sobel, Laplacian) and **smoothing filters** (mean, median, mode) and evaluates their effectiveness in edge enhancement and noise reduction.

---

## Problem Statement

Chest X‑rays are often affected by noise and low contrast, making it difficult to detect subtle abnormalities like pneumonia. Spatial filtering can help:
- **Sharpening** – highlight edges and fine details (e.g., lung boundaries, blood vessels)
- **Smoothing** – reduce noise without sacrificing diagnostic features

This project systematically applies first‑ and second‑order derivative filters, as well as smoothing filters, and analyzes their impact.

## Dataset

The **Chest X‑Ray Images (Pneumonia)** dataset from Kaggle is used. It contains 5,863 X‑ray images, split into **Normal** and **Pneumonia** classes. Images are grayscale JPEGs with varying resolutions, and many exhibit inherent noise and low contrast.

## Methodology

### Sharpening Filters
- **Sobel (First‑order derivative)** – calculates gradient magnitude to highlight edges.
- **Laplacian (Second‑order derivative)** – detects rapid intensity changes, producing stronger responses to fine details.

### Smoothing Filters
- **Mean (Averaging) Filter** – replaces each pixel with the average of its neighborhood.
- **Median Filter** – replaces each pixel with the median of its neighborhood.
- **Mode Filter** – replaces each pixel with the mode (most frequent value) of its neighborhood.

All filters are implemented using **OpenCV** and **NumPy**, with convolution kernels explicitly defined.

## Results

Visual results (original images, filtered outputs, and comparative analyses) are available in the accompanying Google Colab notebook and the assignment report.

*Sobel highlights edges with less noise amplification; Laplacian produces finer detail but is more sensitive to noise.*  
*Median filter best removes salt‑&‑pepper noise while preserving edges. Mean and mode filters cause blurring and artifacts, respectively.*  
*Applying median smoothing before Sobel edge detection significantly reduces noise in the output, improving the clarity of edges.*

## Getting Started

### Prerequisites
- Python 3.8+
- Install dependencies:
  ```bash
  pip install -r requirements.txt
