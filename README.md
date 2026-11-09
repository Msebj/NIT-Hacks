# ForensiWrite: Hybrid Multi-Modal Siamese Feature Fusion for Writer Verification

> Developed for **NITSHACKS 9.0 — Problem Statement 3 (S.T.A.R.K. Initiative: Open Innovation)**  
> **Team:** UCEK  

---

## 📌 Overview
ForensiWrite is an automated offline forensic handwriting verification system designed to detect document forgery in high-stakes environments such as check clearing, legal land registries, and offline examination authentication.

The architecture combines global deep metric learning with local micro-stroke geometric descriptors:
- **Global Feature Extractor:** Siamese Convolutional Neural Network (CNN) trained with contrastive distance.
- **Local Geometric Extractor:** ORB (Oriented FAST and Rotated BRIEF) keypoint and junction matching.
- **Ensemble Classifier:** Multi-modal feature fusion layer paired with a Random Forest classifier.

---

## 📊 Performance Benchmarks
Evaluated on the **ICDAR CVL Handwriting Database** (~1,000 writers):
- **Verification Accuracy:** 75%
- **ROC-AUC Score:** 0.88
- **Inference Profile:** Lightweight CPU/GPU execution suitable for edge & server deployment.

---

## 📂 Repository Structure
```text
NIT-Hacks/
├── app.py                     # Streamlit forensic verification UI
├── model_improved.py          # Siamese CNN model architecture
├── extract_features.py        # Handcrafted & ORB feature extraction
├── fusion_train.py            # Feature fusion & Random Forest training
├── infer_single.py            # Single-pair CLI verification script
├── evaluate.py                # ROC-AUC and metrics evaluation
├── compute_threshold.py       # Threshold calibration for FAR/FRR
├── make_pairs.py              # Positive/negative sample pair generator
├── check_writer_contents.py   # Dataset validation utilities
├── requirements.txt           # Environment dependencies
└── demo_samples/              # Sample handwriting image pairs for instant testing
## ▶️ How to Run the Project

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
