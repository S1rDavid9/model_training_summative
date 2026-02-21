# 🎓 CodeSensAI: Learning Style Prediction

An end-to-end machine learning project that predicts student learning styles using traditional ML and deep learning approaches. Built as the technical foundation for **CodeSensAI** — an adaptive learning platform designed to personalise STEM education for young learners.

---

## 📌 Project Overview

Most educational platforms treat all learners the same way. CodeSensAI aims to change that by predicting a student's dominant learning style from their behavioural and academic patterns, enabling personalised content delivery and adaptive feedback.

This notebook investigates the feasibility of that prediction task through **15 systematic experiments** across 4 algorithm families.

---

## 📂 Repository Structure

```
├── CodeSensAI_LearningStyle_Prediction.ipynb   # Main notebook
├── student_performance.csv                      # Dataset
├── models/                                      # Saved models (joblib / .keras)
├── viz_*.png                                    # Generated visualisations
└── README.md
```

---

## 📊 Dataset

**Source:** [Student Performance and Learning Style — Kaggle](https://www.kaggle.com/datasets/adilshamim8/student-performance-and-learning-style)

| Property | Detail |
|---|---|
| Records | 14,003 |
| Features | 15 (behavioural + academic) |
| Target | `LearningStyle` (0=Visual, 1=Auditory, 2=Read/Write, 3=Kinesthetic) |
| Class Balance | ~25% each — balanced |
| Missing Values | None |

---

## 🧪 Experiments Summary

| Rank | Experiment | Type | Test Accuracy |
|---|---|---|---|
| 1 | RF_Exp1_Baseline | Random Forest | **90.90%** |
| 2 | RF_Exp2_DepthControl | Random Forest | 90.61% |
| 3 | RF_Exp3_AggressiveReg | Random Forest | 88.68% |
| 4 | DL_Exp6_Champion | Deep Learning | 57.94% |
| 5 | SVM_Exp2_RBF_C10 | SVM | 48.84% |
| ... | ... | ... | ... |
| 15 | SVM_Exp3_Linear | SVM | 27.49% |

> Random baseline (4-class) = **25.00%**. Full results table in the notebook.

---

## ⚙️ How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/codesensai-learning-style.git
cd codesensai-learning-style
```

**2. Install dependencies**
```bash
pip install pandas numpy scikit-learn tensorflow matplotlib seaborn joblib
```

**3. Launch the notebook**
```bash
jupyter notebook CodeSensAI_LearningStyle_Prediction.ipynb
```

> All experiments use `random_state=42` — results are fully reproducible.

---

## 🛠️ Tech Stack

- **Python 3.10+**
- **scikit-learn** — Random Forest, SVM, Logistic Regression, preprocessing, evaluation
- **TensorFlow / Keras** — Sequential deep learning models
- **pandas / numpy** — Data manipulation
- **matplotlib / seaborn** — Visualisation
- **joblib** — Model persistence

---

## 🔑 Key Findings

- Random Forest with default settings achieved **90.90% accuracy** with balanced F1 ≈ 0.91 across all four learning style classes — making it the recommended production classifier.
- Deep learning peaked at **57.94%**, confirming that tree-based ensembles outperform neural networks on medium-sized tabular datasets.
- Linear models (Logistic Regression, Linear SVM) clustered near **28%** — barely above random chance — confirming that class boundaries are fundamentally non-linear.

---

## 📄 License

This project was developed as an academic submission. Dataset credit: Adil Shamim via Kaggle.