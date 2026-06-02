# 👤 Face Detection System

> Computer Vision pipeline for automatic face detection in images, built from scratch using only classical ML — no pre-trained models.

---

## 📌 Overview

This project tackles a core Computer Vision challenge: **detecting the presence of faces in arbitrary images** and returning the bounding box coordinates of each detected face. The key constraint that makes this project technically interesting is that **no pre-trained models were used** — the entire detector was trained from scratch with scikit-learn under limited computational resources.

---

## 🎯 Objective

Given an input image, the system must:

- Detect whether one or more faces are present
- Return the **bounding box coordinates** `(x, y, width, height)` for each detected face
- Return an **empty list** if no faces are found

---

## 🏗️ Pipeline

```
Input Image
     │
     ▼
Sliding Window (multi-scale scanning)
     │
     ▼
HOG / Pixel Feature Extraction per window
     │
     ▼
Classifier (trained from scratch, scikit-learn)
     │
     ▼
Face / Non-Face prediction
     │
     ▼
Non-Maximum Suppression (NMS)
     │
     ▼
Bounding Box Coordinates
```

---

## ⚠️ Constraints & Challenges

| Constraint | Detail |
|---|---|
| No pre-trained models | Classifier trained entirely from scratch |
| No dataset provided | Images self-collected and labeled |
| Limited compute | No GPU — CPU-only training |
| Framework | scikit-learn only (no TensorFlow/PyTorch) |

These constraints make the project a genuine exercise in classical Computer Vision, requiring manual feature engineering rather than relying on deep learning.

---

## 📁 Dataset & Images

Training and testing images are hosted in a dedicated public repository:

🔗 [face_detection_samples](https://github.com/NicoloDiscotto/face_detection_samples)

---

## 🛠️ Tech Stack

| Area | Tools |
|---|---|
| Image Processing | `opencv-python` |
| Machine Learning | `scikit-learn` |
| Numerical Computing | `numpy` |
| Visualization | `matplotlib` |
| Data Fetching | `requests` |

---

## 📊 Approach

### 1. Dataset Preparation
- Collection of positive samples (images with faces) and negative samples (images without faces)
- Manual annotation of bounding boxes
- Data augmentation (flips, crops) to increase diversity

### 2. Feature Extraction
- Sliding window approach at multiple scales
- Feature extraction per window (HOG descriptors or raw pixel features)
- Building a balanced training set of face / non-face patches

### 3. Classifier Training
- Binary classification: face vs. non-face
- Trained with scikit-learn on extracted features
- Hyperparameter tuning via cross-validation

### 4. Inference & Post-processing
- Multi-scale sliding window scan over the full image
- Non-Maximum Suppression (NMS) to merge overlapping bounding boxes
- Final bounding box output

---

## 📝 Notes

Developed as part of the **Master in Data Science @ ProfessionAI** (2025–2026).  
This project demonstrates classical Computer Vision techniques, deliberately avoiding deep learning to explore the capabilities and limits of traditional ML approaches for object detection.

---

## 📫 Author

**Nicolò Discotto** · [LinkedIn](https://www.linkedin.com/in/nicolo-discotto/) · [GitHub](https://github.com/NicoloDiscotto)
