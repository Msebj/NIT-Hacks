# ForensiWrite: Hybrid Multi-Modal Siamese Feature Fusion for Writer Verification

> **NITSHACKS 9.0 — Problem Statement 3: S.T.A.R.K. Initiative (Open Innovation)**  
> **Team:** UCEK  

---

## 📌 Project Overview

Manual verification of offline signatures and handwriting is slow, subjective, and susceptible to fraud in high-stakes environments such as bank check clearances, legal deed registrations, and examination authentication. 

**ForensiWrite** is an automated offline forensic handwriting verification engine that compares two handwriting samples and determines whether they originate from the same writer. It integrates global deep visual representations with local micro-stroke geometric features into a unified multi-modal classification pipeline.

---

## 🚀 Key Features

* **Dual-Sample Preprocessing:** Automated Otsu adaptive binarization, grayscale standardization, noise reduction, and stroke-width normalization.
* **Siamese CNN Architecture:** Twin convolutional neural network branches sharing weights to extract deep latent embeddings and compute cosine/contrastive similarity.
* **ORB Geometric Matching:** Oriented FAST and Rotated BRIEF (ORB) keypoint detection to analyze micro-stroke junctions, loops, and curvature dynamics.
* **Multi-Modal Feature Fusion:** Merges deep neural metrics with handcrafted structural features to train a Random Forest ensemble classifier.
* **Interactive Forensic Dashboard:** Streamlit-powered user interface displaying real-time match verdicts, confidence percentages, ROC curves, and confusion matrices.
* **CLI Inference Support:** Rapid single-pair evaluation script for batch backend workflows.

---

## 📊 Performance Benchmarks

Trained and evaluated on the **ICDAR CVL Handwriting Database** (~1,000 writers):

| Metric | Score | Notes |
| :--- | :--- | :--- |
| **Verification Accuracy** | **75.0%** | Tested across unseen test split pairs |
| **ROC-AUC Score** | **0.88** | Strong discriminative threshold capability |
| **Inference Footprint** | Lightweight | Runs seamlessly on standard CPU and GPU environments |

---

## 🧠 System Architecture & Methodology

```text
               +-------------------------------------------+
               |  Input Handwriting / Document Image Pair  |
               +-------------------------------------------+
                                     |
                                     v
                       [ OpenCV Preprocessing Pipeline ]
                     (Binarization, Denoising, Normalization)
                                     |
                 +-------------------+-------------------+
                 |                                       |
                 v                                       v
     [ Siamese Twin CNN ]                    [ ORB Keypoint Extractor ]
  (Deep Visual Latent Embedding)           (Micro-Stroke & Loop Descriptors)
                 |                                       |
                 +-------------------+-------------------+
                                     |
                                     v
                       [ Multi-Modal Feature Fusion ]
                                     |
                                     v
                        [ Random Forest Classifier ]
                                     |
                 +-------------------+-------------------+
                 |                                       |
                 v                                       v
      [ Match / No-Match Verdict ]              [ Forensic Analytics ]
    (Confidence Percentage & Scores)          (ROC-AUC, Confusion Matrix)
---

