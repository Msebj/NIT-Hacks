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

```

---
```text
## 📂 Project Structure


Handwriting-Recognition-System/
│
├── app.py
├── preprocessing.py
├── model.py
├── fusion.py
├── features.py
├── utils.py
├── requirements.txt
├── README.md
├── dataset/
├── outputs/
└── images/
```

---
## 📊 Dataset Used

The project was trained and evaluated using the **CVL Handwriting Dataset**, which contains handwriting samples from approximately 1000 writers.

Dataset Reference:

F. Kleber, S. Fiel, M. Diem, and R. Sablatnig,
“CVL-Database: An Off-line Database for Writer Retrieval, Writer Identification and Word Spotting,” ICDAR, 2013.

---

### How to Run the Project

### Step 1: Clone Repository

```bash
git clone https://github.com/yourusername/handwriting-recognition-system.git
```

### Step 2: Open Project Folder

```bash
cd handwriting-recognition-system
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run Streamlit Application

```bash
streamlit run app.py
```

---

## 📷 Output

The system displays:

* Similarity Score
* Match / No Match Result
* CNN Similarity
* Fusion Probability
* ROC Curve
* Confusion Matrix

---

## 📚 References

1. E. Rublee et al., “ORB: An efficient alternative to SIFT or SURF,” ICCV, 2011.
2. F. Kleber et al., “CVL-Database,” ICDAR, 2013.
3. Y. LeCun et al., “Deep Learning,” Nature, 2015.
4. J. Bromley et al., “Signature verification using a Siamese neural network,” 1994.
5. OpenCV Documentation – [https://opencv.org](https://opencv.org)
6. Streamlit Documentation – [https://streamlit.io](https://streamlit.io)

---

