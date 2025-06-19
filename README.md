# 🛣️ Driver Alertness Recognition Using Multimodal Dataset

This repository contains the source code for my Final Year Project, which focuses on building a multimodal machine learning and deep learning system for detecting driver alertness using physiological signals, behavioral (PVT) data, and driving behavior metrics. The project aims to improve prediction accuracy while ensuring model interpretability using SHAP and Quantus.

---

## 📁 Project Structure

```text
Source Code/
├── Driving/                  # Models trained on driving data only
├── Driving + PVT/           # Models trained on driving and behavioral (PVT) data
├── Physio/                  # Models trained on physiological signals only
├── Physio + Driving/        # Combined physiological and driving data
├── Physio + Driving + PVT/  # Full multimodal input (main experiment focus)
├── Physio + PVT/            # Combined physiological and behavioral data
├── PVT/                     # Behavioral (reaction time) data only
└── Exp4/                    # Dataset folder (Meteier et al. 2023 subset used in this project)
```



Each folder (excluding `Exp4`) contains multiple Jupyter notebooks (`.ipynb`) with experiments for various models.

---

## 🧠 Models Implemented

The following models are trained and evaluated across different modality combinations:

- **Traditional Machine Learning:**
  - Decision Tree
  - Random Forest
  - XGBoost
  - LightGBM
  - CatBoost

- **Deep Learning:**
  - Neural Network (FCNN)
  - Convolutional Neural Network (CNN)
  - Causal CNN
  - Recurrent Neural Network (RNN)

- **Transformer-Based:**
  - SAINT
  - TabTransformer

---

## 📊 Evaluation Metrics

All models are evaluated using:
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

Interpretability is addressed using:
- **SHAP (SHapley Additive exPlanations)** for feature importance
- **Quantus** for explanation evaluation (faithfulness, robustness, complexity, etc.)

---

## 📈 Results Summary

| **Modality Combination**         | **Best Model**   | **Accuracy** | **Precision** | **Recall** | **F1-Score** |
|----------------------------------|------------------|--------------|---------------|------------|--------------|
| Driving                          | Random Forest    | 0.88         | 0.87          | 0.85       | 0.86         |
| PVT                              | LightGBM         | 0.85         | 0.84          | 0.83       | 0.83         |
| Physio                           | XGBoost          | 0.91         | 0.90          | 0.89       | 0.89         |
| Physio + Driving                 | LightGBM         | 0.94         | 0.93          | 0.92       | 0.93         |
| Physio + PVT                     | Neural Network   | 0.93         | 0.91          | 0.92       | 0.92         |
| Driving + PVT                    | Random Forest    | 0.90         | 0.89          | 0.88       | 0.88         |
| **Physio + Driving + PVT**       | **XGBoost**      | **0.96**     | **0.95**      | **0.96**   | **0.96**     |

📌 The **Physio + Driving + PVT** combination using **XGBoost** achieved the highest performance across all metrics.

---

---

## 📂 Dataset

The dataset is based on the **Exp4 subset** from the study by **Meteier et al. (2023)**. It includes:
- **Physiological Signals**: ECG, EDA, RESP
- **Driving Metrics**: Takeover reaction time, steering, braking
- **PVT (Psychomotor Vigilance Test)**: Reaction times to stimuli
- Conditions: Sleep-deprived vs. non-sleep-deprived, urban vs. rural driving simulation

---

## 🎯 Project Objectives

- Implement and compare ML and DL models for driver alertness detection
- Evaluate performance across different combinations of input modalities
- Apply SHAP for interpretable AI in safety-critical scenarios
- Contribute toward safer intelligent transportation systems

---

## 💻 Installation

Install the required libraries:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn xgboost lightgbm catboost tensorflow keras torch shap quantus
```
You can run the Jupyter notebooks using:
```bash
jupyter notebook
```
📜 License
This project is developed for academic purposes.
© 2025 Universiti Multimedia Sdn. Bhd. All rights reserved.

🙏 Acknowledgements
Supervisor: Dr. Siti Fatimah Abdul Razak
Faculty of Information Science & Technology, Multimedia University
Dataset from Meteier et al. (2023)
