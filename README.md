# 🎗️ Breast Cancer Indicators

## Overview

This project applies machine learning to predict malignancy in breast tissue cells using biopsy data collected from female patients. Our goal was twofold:

1. Identify the best-performing model for predicting cell malignancy.
2. Determine the most informative features for predicting malignancy.

Using a combination of logistic regression and permutation feature importance testing, we developed a highly accurate predictive model, achieving **98% accuracy** on test data.

---

## 🔬 Dataset

- **Source:** [UCI Machine Learning Repository](https://doi.org/10.24432/C5HP4Z)
- **Creator:** Dr. William H. Wolberg, University of Wisconsin Hospitals
- **Timeframe:** 1989–1991
- **Samples:** 699 total
- **Missing Values:** 2.3% of values imputed using mean substitution
- **Malignant Cases:** ~34.5%
- **Features (all rated 1–10):**
  - Clump Thickness
  - Uniformity of Cell Size
  - Uniformity of Cell Shape
  - Marginal Adhesion
  - Single Epithelial Cell Size
  - Bare Nuclei
  - Bland Chromatin
  - Normal Nucleoli
  - Mitosis
- **Target Variable:** Class (2 = Benign, 4 = Malignant)

Some patients underwent multiple biopsies, but all records were retained due to variation in cell characteristics between samples.

---

## 🧪 Methodology

### 1. **Data Preparation**
- Train/Validation/Test Split: 80/10/10
- Missing values replaced with feature mean

### 2. **Model Selection**
- Evaluated Models:
  - Logistic Regression
  - RBF & Linear SVM
  - Decision Tree
  - K-Nearest Neighbors (K-NN)
- **Best Model:** Logistic Regression with **C = 0.01**
  - Chosen via Grid Search
  - Regularization minimized overfitting
  - Achieved **98% validation accuracy**

### 3. **Feature Selection**
- **Correlation Heatmap:** Showed high correlation between some features (e.g., cell size and shape)
- **Permutation Importance:** Identified most impactful features by shuffling each and measuring drop in R² score
- **Top 4 Features:**
  - Bare Nuclei
  - Clump Thickness
  - Bland Chromatin
  - Uniform Cell Shape

### 4. **Final Model Testing**
- Retrained model using top 4 features
- Scored on test data: **Accuracy = 0.98**

---

## ⚠️ Limitations

- **Dataset Age:** Data is from 1989–1991; biopsy techniques and measurement standards may have changed.
- **Dataset Size:** Relatively small sample size.
- **Predictive Scope:** Model only predicts malignancy of cells — not prognosis, metastasis, or other clinical outcomes.

---

## ✅ Key Takeaways

- Logistic regression is highly effective for this task when regularized appropriately.
- A minimal subset of features can yield near-optimal results.
- Bare Nuclei was the most influential predictor of malignancy.
- Simpler models can be both interpretable and powerful in medical diagnostics.

---

## 📚 References

- Akinnuwesi, B. A., Macaulay, B. O., & Aribisala, B. S. (2020). Breast cancer risk assessment and early diagnosis using Principal Component Analysis and support vector machine techniques. *Informatics in Medicine Unlocked*, 21, 100459. https://doi.org/10.1016/j.imu.2020.100459  
- Lopez, R. (2023, August 31). *Diagnose breast cancer using machine learning*. [Neural Designer](https://www.neuraldesigner.com/learning/examples/breast-cancer-diagnosis/)
- Wolberg, W. (1992). *Breast Cancer Wisconsin (Original)* [dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5HP4Z

---

## 🚀 Future Work

- Explore deep learning techniques with image-based biopsy data.
- Integrate additional clinical variables (e.g., age, genetic markers).
- Expand model to predict patient outcomes beyond malignancy (e.g., recurrence risk).

---

## 💡 Conclusion

By focusing on interpretable and impactful features, our logistic regression model offers a strong and accessible foundation for supporting medical decision-making in breast cancer detection. With further validation and updated data, this approach could aid in streamlining biopsy analysis and diagnosis.
