# Skin Disease Classification System

An end-to-end **machine learning–powered web application** for skin disease image classification, developed using a **Waterfall-style ML system development lifecycle**. ⋆｡‧˚ʚɞ˚‧｡⋆

The project emphasizes **robust data preparation, deep learning model training, explainable outputs, and secure deployment**, making it suitable for roles in **Machine Learning, Data Science, Software Engineering, and Full-Stack Development**.

---

## Project Overview

### Input
- User uploads a **skin lesion image**

### Output
- **Predicted skin condition** (10 classes)
- **Confidence score**
- **Human-readable explanation**, including:
  - What the condition is
  - Why it may occur (risk factors / associations)
  - General, non-medical guidance

### Disclaimer
This project is intended **strictly for educational and technical demonstration purposes** and **must not be used as a medical diagnostic tool**.

---

## System Architecture (High-Level)

```text
Frontend (React / Vercel)
        ↓
Backend API (FastAPI)
        ↓
Image Classification Model (CNN / Transformer)
        ↓
Prediction + Confidence
        ↓
Explanation Engine (Knowledge Base)
````

---

## Dataset Summary

* **Dataset Type:** Folder-per-class image dataset
* **Total Images:** ~**27,000**
* **Number of Classes:** **10 skin disease categories**
* **Data Split Strategy:**

  * **Training:** 70%
  * **Validation:** 15%
  * **Testing:** 15%

### Data Quality Assurance

* **0 corrupted images detected**
* **Stratified splitting** applied to prevent data leakage
* Class distribution analyzed prior to training

---

## Data Preparation & Feature Engineering

For image-based deep learning, **feature engineering is performed through data preparation**, not manual feature construction.

### Data Preparation Steps

* Image resizing to **224 × 224**
* Pixel normalization (ImageNet statistics)
* Data augmentation (training only):

  * Random horizontal flips
  * Random rotations
  * Color jitter
* Stratified train/validation/test splitting
* Class imbalance analysis

### Key Insight

Feature representations are **learned automatically** by deep learning models via **representation learning**, rather than handcrafted features.

---

## Model Strategy

A **progressive model selection strategy** is used to balance performance, modern ML practices, and deployment feasibility.

| Stage        | Model            | Purpose                                     |
| ------------ | ---------------- | ------------------------------------------- |
| Baseline     | EfficientNet     | Validate data pipeline & establish baseline |
| Modern       | Swin Transformer | Capture global image context                |
| Production   | ConvNeXt         | Balance accuracy and inference efficiency   |
| Experimental | CLIP-style       | Multimodal research extension               |

Model training is conducted using **GPU-enabled cloud environments (Kaggle)**.

---

## Security Considerations

* API key–protected inference endpoint
* Rate limiting to prevent abuse
* File type and file size validation
* CORS allowlist enforcement
* **No image storage**
* HTTPS enforced by hosting provider

---

## Waterfall Development Lifecycle

This project follows a **Waterfall-style ML system development process**, with clearly defined phases and deliverables.

### Phase 0 — Requirements & Scope Definition

* Define problem statement, constraints, and success criteria
* Clarify ethical and non-diagnostic boundaries

### Phase 1 — Data Acquisition & Validation

* Dataset inspection and profiling
* Corruption detection and removal
* Class distribution analysis

### Phase 2 — Dataset Preparation

* Stratified train/validation/test splitting
* Local CPU-based smoke testing to validate pipeline

### Phase 3 — Model Development (Cloud)

* GPU-based training using pretrained models
* Model comparison and selection
* Performance evaluation using validation metrics

### Phase 4 — Explanation Engine

* Knowledge base creation for each class
* Safe, non-medical explanatory outputs

### Phase 5 — Backend API Development

* Secure inference endpoint
* Model integration
* Input validation and error handling

### Phase 6 — Frontend Application

* Image upload interface
* Prediction visualization
* Explanation rendering

### Phase 7 — Deployment & Documentation

* Cloud deployment
* Security configuration
* Technical documentation and reporting

---

## Tech Stack

* **Machine Learning:** PyTorch, Torchvision
* **Backend:** FastAPI
* **Frontend:** React, Vercel
* **Training Environment:** Kaggle GPU
* **Deployment:** Render

---

## Final Disclaimer

This system does **not** provide medical diagnoses.
All predictions and explanations are intended for **educational demonstration purposes only**.

---

## Author

**May Mon Ko**
₊✩‧₊˚౨ৎ˚₊✩‧₊
