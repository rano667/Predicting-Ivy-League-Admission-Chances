# 🎓 Predicting Ivy League Admission Chances

> A data science project using linear regression and advanced modeling to predict the probability of graduate admissions into Ivy League universities based on academic metrics and research experience.

---

## 📌 Project Objective

Jamboree launched a platform feature to help students estimate their chances of getting into Ivy League graduate programs. This project develops a predictive model using statistical analysis and machine learning to identify admission-driving factors and provide reliable estimates from an Indian applicant perspective.

---

## 📁 Dataset

- **Source**: [Jamboree_Admission.csv](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/001/839/original/Jamboree_Admission.csv)
- **Size**: 500 student application records
- **Features**:
  - GRE Score (out of 340)
  - TOEFL Score (out of 120)
  - University Rating (1 to 5)
  - SOP Strength (1 to 5)
  - LOR Strength (1 to 5)
  - CGPA (out of 10)
  - Research Experience (0 or 1)
  - Chance of Admit (target: 0 to 1)

---

## 📊 Exploratory Data Analysis

- Most students scored high on SOP and LOR.
- CGPA showed strong correlation with admission chance.
- GRE and TOEFL showed moderate correlation.
- No multicollinearity (all VIFs < 5).

---

## ⚙️ Modeling Approach

### Linear Regression (Base Model)
- Scaled features using MinMaxScaler
- 80/20 Train-Test split

📈 Performance:
- R²: 0.8188
- RMSE: 0.0609
- MAE: 0.0427
- Adjusted R²: 0.8051

**Top Predictors**: CGPA, GRE, TOEFL, Research

---

## ✅ Model Assumption Testing

| Assumption            | Status   | Notes |
|------------------------|----------|-------|
| Mean of residuals ≈ 0  | ✅        | Mean = 3.9e-16 |
| Multicollinearity      | ✅        | All VIFs < 5 |
| Linearity              | ⚠️        | Mild non-linearity near fitted value = 1 |
| Homoscedasticity       | ⚠️        | Funnel shape suggests heteroscedasticity |
| Normality              | ⚠️        | Shapiro-Wilk p ≈ 7.7e-13, QQ plot slightly off |

---

## 🔁 Advanced Modeling

### Polynomial Regression (degree = 2)
- R²: 0.8265
- RMSE: 0.0596

### Ridge Regression (α = 0.001)
- R²: 0.8216

### Lasso Regression (α = 0.001)
- R²: 0.7035

---

## 🔍 Key Insights

- **CGPA** is the most influential factor for admission.
- **GRE and TOEFL** have moderate impact.
- **Research** experience increases chances.
- **SOP and LOR** are less impactful quantitatively.
- Ridge and Polynomial Regression (deg=2) offer the best tradeoff between interpretability and accuracy.

---

## 💼 Business Recommendations

- Guide students to focus on improving **CGPA, GRE**, and **Research output**.
- Integrate this model into Jamboree’s web app to give **real-time probability scores**.
- Add more features like **work experience**, **undergrad major**, **project quality** to enhance predictions.
- Explore **ensemble methods** in future for non-linear patterns.

---

## 📂 Report & Code

- 📄 [View Final Report (PDF)](./Jamboree.pdf)
- 📓 [Colab Notebook (Code)](https://colab.research.google.com/drive/1aeyKaE1o33bfOm-7sAFBzeg9b51yVNPs?usp=sharing)

---

## 👨‍💻 Author

**Ranjan Mondal**  
[LinkedIn](#) • [GitHub](#)

---

## 📜 License

This project is for academic use only. All rights reserved by Ranjan Mondal & Jamboree Education.

