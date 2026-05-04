# An Explainable ML & DL Framework for Malicious URL Detection

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Best%20Model-orange?style=for-the-badge)
![Accuracy](https://img.shields.io/badge/Accuracy-98.44%25-brightgreen?style=for-the-badge)
![Conference](https://img.shields.io/badge/ICMLDE-2025-blueviolet?style=for-the-badge)
![Status](https://img.shields.io/badge/Publication-Forthcoming-yellow?style=for-the-badge)

**Presented at ICMLDE 2025 · School of Computer Science, UPES, Dehradun**

[Paper (forthcoming)](#) · [Methodology](#-methodology) · [Results](#-results) · [Explainability](#-explainability-shap--lime)

</div>

---

## Overview

Cyberattacks are at an all-time high — global losses are projected to exceed **$10.5 trillion by 2025**, with **900 million+ phishing attempts** recorded in 2024 alone. A staggering **80% of malicious links are zero-day threats** that traditional, signature-based methods fail to catch.

Most existing approaches suffer from three critical gaps:
- **Black-box models** — high accuracy, zero transparency
- **Static feature sets** — no adaptation to evolving attack patterns
- **No real-time capability** — too slow for deployment

We address all three. This project presents a **hybrid ML/DL framework** that detects malicious URLs with high accuracy while remaining **transparent and interpretable** using SHAP and LIME — making the model accountable, not just accurate.

---

## Team
- Amitha Mahesh
- Nitheka A
- S Shivvanii
- C Vivethasri
- Dr. S Manimaran *(Mentor)* 

---

## Methodology

### Dataset
- Combined **Manu Siddhartha's Kaggle dataset** and **Hannousse et al.**
- Preprocessing pipeline: tokenization → normalization → outlier removal
- Starting feature space: **4000+ features**

### Feature Selection
We used **RFECV (Recursive Feature Elimination with Cross-Validation)** to adaptively select the optimal feature subset — addressing the static feature limitation common in prior work.

### Models Trained

| Model | Type |
|-------|------|
| Random Forest | Machine Learning |
| XGBoost | Machine Learning |
| Artificial Neural Network (ANN) | Deep Learning |
| Convolutional Neural Network (CNN) | Deep Learning |

### Explainability Layer

| Technique | Scope | Purpose |
|-----------|-------|---------|
| **SHAP** | Global | What features drive the model overall? |
| **LIME** | Local | Why did the model flag *this specific URL*? |

### Deployment
Real-time URL detection pipeline validated at **192ms latency** — fast enough for practical use.

---

##  Results

### Performance Metrics

| Model | Accuracy | F1 Score | Precision | Recall |
|-------|----------|----------|-----------|--------|
| **XGBoost**  | **0.9844** | **0.9734** | 0.9619 | **0.9852** |
| CNN | 0.9839 | 0.9725 | 0.9637 | 0.9814 |
| ANN | 0.9832 | 0.9711 | 0.9672 | 0.9750 |
| Random Forest | 0.9785 | 0.9636 | 0.9443 | 0.9836 |

> **XGBoost achieved the best overall performance**, outperforming the prior baseline (Hani et al., 95.49%) across all four metrics.

---

##  Explainability: SHAP + LIME

One of our core contributions is making the model **not just accurate, but interpretable**.

### SHAP — Global Feature Importance
SHAP values reveal which features consistently drive the model's decisions across the entire dataset.

> *(SHAP summary plot — attached with this repo)*

### LIME — Local Explanations
LIME builds a local surrogate model around individual predictions to explain *why* a specific URL was flagged.

**Top features identified by LIME for malicious URL predictions:**
1. `path_length` — strongest single indicator
2. `url_length` — second most influential
3. Token patterns: `://`, `.co`, `htt` — contribute significantly

> *(LIME explanation plot — attached with this repo)*

These explanations make the system **audit-ready** and **trustworthy** for real-world deployment.

---

## Key Contributions

- **Adaptive feature selection** via RFECV — no more static, hand-picked feature sets
- **Unified ML + DL comparison** on the same dataset and evaluation protocol
- **Full explainability** — SHAP for global understanding, LIME for per-prediction transparency
- **Real-time detection** validated at 192ms latency
- **Outperforms the baseline** across all four evaluation metrics

---

## Recognition

This paper was **presented and awarded** at the **International Conference on Machine Learning and Data Engineering (ICMLDE 2025)**, held November 6–8, 2025 at the School of Computer Science, UPES, Dehradun, India — in association with Amrita Vishwa Vidyapeetham, Tamil Nadu.

---

## Citation

> Paper presented at ICMLDE 2025. Full citation will be updated upon publication.

---

## Note on Source Code

This repository currently contains the README and results summary. Full source code will be made available upon paper publication.

---

## Tags

`Machine Learning` `Deep Learning` `Explainable AI` `Cybersecurity` `XGBoost` `SHAP` `LIME` `URL Detection` `Phishing` `RFECV` `Python` `ICMLDE2025` `Malicious URL` `Hybrid Framework`
