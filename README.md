# Handwritten Character Recognition (HCR) Using Artificial Neural Networks

Welcome to the Handwritten Character Recognition (HCR) project! This repository contains a complete pipeline for recognizing handwritten English characters (both alphabets and digits) from images using state-of-the-art machine learning techniques. The project leverages both traditional Artificial Neural Networks (ANN) and Convolutional Neural Networks (CNN) to achieve robust recognition accuracy, with a focus on practical implementation and clarity.

---

## 📖 Table of Contents

- [Introduction](#introduction)
- [Objectives](#objectives)
- [Methodology](#methodology)
  - [Dataset](#dataset)
  - [Model Architectures](#model-architectures)
- [System Design](#system-design)
  - [Preprocessing](#preprocessing)
  - [Segmentation](#segmentation)
  - [Feature Extraction](#feature-extraction)
  - [Classification](#classification)
- [Implementation](#implementation)
  - [Data Preparation](#data-preparation)
  - [Model Training](#model-training)
  - [Image Prediction Pipeline](#image-prediction-pipeline)
- [Testing & Results](#testing--results)
- [Conclusion & Future Scope](#conclusion--future-scope)
- [Requirements](#requirements)
- [References](#references)

---

## Introduction

Optical Character Recognition (OCR) is the technology that enables machines to convert images of text (handwritten or printed) into machine-readable digital text. Within OCR, **Handwritten Character Recognition (HCR)** is a challenging subset due to the diversity and variability of human handwriting. This project addresses the problem of recognizing handwritten English alphabets (A-Z, a-z) and digits (0-9) using machine learning, specifically neural networks.

---

## Objectives

- **Recognize all English alphabets and digits** in a given input image.
- **Automate the process** of converting handwritten text into digital form, reducing manual data entry and enabling fast retrieval.
- **Develop a robust pipeline** that includes preprocessing, segmentation, feature extraction, and classification.
- **Achieve high accuracy** using both ANN and CNN models.

---

## Methodology

### Dataset

- **Source:** [EMNIST ByClass](https://www.nist.gov/itl/products-and-services/emnist-dataset)
- **Content:** 814,255 images, 62 classes (10 digits + 26 uppercase + 26 lowercase English letters)
- **Format:** 28x28 grayscale images
- **Splits:** Training (697,932), Testing (116,323)

### Model Architectures

#### 1. **Artificial Neural Network (ANN)**
- **Input:** Flattened 28x28 (784) pixel vector
- **Hidden Layers:** Three layers with 512, 256, and 128 neurons (ReLU activation)
- **Output Layer:** 62 neurons (Softmax activation for multiclass classification)
- **Optimizer:** Gradient Descent
- **Loss:** Cross-Entropy

#### 2. **Convolutional Neural Network (CNN)**
- **Convolutional Layers:** Two layers (32 and 64 filters, 3x3 kernel, ReLU)
- **Pooling:** Max pooling after each convolution
- **Dense Layer:** 512 neurons (ReLU)
- **Output Layer:** 62 neurons (Softmax)
- **Optimizer:** Adadelta
- **Loss:** Categorical Cross-Entropy

---

## System Design

The recognition pipeline is divided into the following phases:

### Preprocessing

- **Grayscale Conversion:** Converts input images to grayscale.
- **Noise Removal:** Uses Gaussian blur to remove artifacts and improve image quality.
- **Binarization:** Applies thresholding to convert images to black-and-white.
- **Normalization:** Scales pixel values to[1] range.

### Segmentation

- **Line, Word, and Character Segmentation:** Uses histograms and contour detection to break down the image into individual characters.
- **Resizing:** Each character is resized to 28x28 pixels for model compatibility.

### Feature Extraction

- **Flattening:** Converts each 28x28 image into a 784-dimensional vector (for ANN).
- **Tensor Representation:** Prepares data as tensors for neural network input.

### Classification

- **Model Prediction:** The trained neural network predicts the class (character/digit) for each segmented image.

---

## Implementation

### Data Preparation

- **Downloading:** Uses `urllib` to fetch the EMNIST dataset.
- **Unzipping:** Extracts files using `zipfile`.
- **Loading:** Reads images and labels into NumPy arrays.
- **Visualization:** Uses Matplotlib to display sample images.

### Model Training

- **ANN Model:** Built and trained using TensorFlow, with weights and biases initialized from a normal distribution.
- **CNN Model:** Built using Keras/TensorFlow, trained with categorical cross-entropy loss.
- **Training Metrics:** Accuracy and loss are tracked and visualized for both models.

### Image Prediction Pipeline

- **Input Image Handling:** Reads user-provided images, preprocesses, and segments them into individual characters.
- **Character Prediction:** Each character image is passed through the trained model to predict its class.
- **Output:** Recognized text is displayed and optionally saved to a text file.

---

## Testing & Results

- **ANN Model:** ~87% training accuracy, ~85.2% test accuracy.
- **CNN Model:** ~87% training accuracy, ~85% test accuracy.
- **Visualization:** Includes confusion matrices and sample prediction outputs for qualitative assessment.

---

## Requirements

**Software:**
- Python 3.x
- TensorFlow 1.3+
- NumPy
- OpenCV
- Pandas
- Matplotlib
- Google Colab (recommended for GPU support)

**Hardware:**
- OS: Windows 10, Linux, or MacOS
- Processor: Intel Core i3 or higher
- RAM: 2GB or more

---

**Feel free to explore, use, and extend this project. Contributions and suggestions are always welcome!**

---
