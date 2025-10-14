# 📘 StudentPerformanceFactors – Stage 1

### 🎯 Objective  
This project aims to **analyze factors influencing students’ exam performance** and build predictive regression models to estimate `Exam_Score` based on multiple academic, social, and personal attributes.

---

## 📂 Project Overview

| **Stage** | **Description** |
|------------|-----------------|
| **Stage 1** | Dataset Selection, Initial EDA, Data Preprocessing, Feature Engineering, and Regression Model Building |
| **Dataset Source** | Kaggle Datasets (Indian Students, 2025) |
| **Problem Type** | Regression |
| **Language / Tools** | Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn |

---

## 📊 Dataset Description

**Target Feature:**  
- `Exam_Score` – Final exam score (numeric)

**Input Features:**  
| Feature | Description |
|----------|-------------|
| Hours_Studied | Number of hours spent studying per week |
| Attendance | Percentage of classes attended |
| Parental_Involvement | Level of parental involvement (Low / Medium / High) |
| Access_to_Resources | Availability of resources (Low / Medium / High) |
| Extracurricular_Activities | Participation in extracurricular activities (Yes / No) |
| Sleep_Hours | Average number of hours of sleep per night |
| Previous_Scores | Scores from previous exams |
| Motivation_Level | Student's motivation level (Low / Medium / High) |
| Internet_Access | Availability of internet access (Yes / No) |
| Tutoring_Sessions | Number of tutoring sessions per month |
| Family_Income | Family income level (Low / Medium / High) |
| Teacher_Quality | Quality of teachers (Low / Medium / High) |
| School_Type | Type of school (Public / Private) |
| Peer_Influence | Influence of peers (Positive / Neutral / Negative) |
| Physical_Activity | Average number of hours of physical activity per week |
| Learning_Disabilities | Presence of learning disabilities (Yes / No) |
| Parental_Education_Level | Highest education level of parents |
| Distance_from_Home | Distance to school (Near / Moderate / Far) |
| Gender | Male / Female |

---

## 🧹 Data Preprocessing Summary

| Step | Description |
|------|--------------|
| **Missing Values** | Filled missing values with mode for `Teacher_Quality`, `Parental_Education_Level`, and `Distance_from_Home`. |
| **Duplicates** | No duplicates found. |
| **Outliers** | Outliers removed using IQR method for key numerical columns. |
| **Encoding** | Label Encoding applied to all categorical variables. |
| **Feature Scaling** | StandardScaler applied to numerical features. |
| **Final Dataset Shape** | 5,957 rows × 20 columns |

---

## 🔍 Exploratory Data Analysis (EDA)

### Key Observations
- **Hours_Studied** and **Attendance** show strong positive correlation with `Exam_Score`.
- **Sleep_Hours** and **Physical_Activity** are normally distributed.
- **Most common categories:**  
  - `Gender`: Male students dominate the dataset.  
  - `Parental Education`: High School most frequent.  
  - `Learning Disabilities`: Mostly "No".  
- **No severe skewness** (all features have skewness values within ±0.5).

### Visualization Highlights
- **Univariate:** Count plots for categorical features, histograms, boxplots, and KDE plots for numeric features.  
- **Bivariate:** Scatter plots (e.g., Hours_Studied vs Exam_Score), line plots, and bar plots reveal positive relationships.  
- **Multivariate:**  
  - Correlation heatmap shows `Hours_Studied` and `Attendance` as key predictors.  
  - Pairplots illustrate strong linear trends.

---

## ⚙️ Feature Engineering

**Feature Selection (SelectKBest):**  
Top 13 features selected for modeling:
['Hours_Studied', 'Attendance', 'Parental_Involvement',
'Access_to_Resources', 'Extracurricular_Activities', 'Previous_Scores',
'Internet_Access', 'Tutoring_Sessions', 'Teacher_Quality',
'Peer_Influence', 'Learning_Disabilities',
'Parental_Education_Level', 'Distance_from_Home']

yaml
Copy code

---

## 🤖 Model Building & Evaluation

### Algorithms Used
- **Linear Regression**
- **Decision Tree Regressor**
- **Random Forest Regressor**
- **KNeighbors Regressor**

### Data Split
- **Training Set:** 80% (4,765 samples)  
- **Test Set:** 20% (1,192 samples)

---

## 📈 Model Performance Comparison

| Model | MAE | RMSE | R² Score |
|--------|------|-------|-----------|
| **Random Forest Regressor** | 0.874 | 1.092 | 0.873 |
| **Linear Regression** | 0.913 | 1.117 | 0.867 |
| **KNN Regressor** | 1.707 | 2.176 | 0.496 |
| **Decision Tree Regressor** | 1.982 | 2.457 | 0.358 |

---

## 🧠 Interpretation

- **Top Predictors:** `Hours_Studied`, `Attendance`, and `Previous_Scores` strongly influence `Exam_Score`.  
- **Model Insights:**  
  - Random Forest performed best overall.  
  - Linear Regression gave near-similar accuracy, indicating linear relationships in data.  
  - KNN and Decision Tree models underperformed, suggesting overfitting or insufficient complexity capture.

---

## ✅ Conclusion

- **Best Model:** Random Forest Regressor  
- **Best R² Score:** 0.873  
- **Best RMSE:** 1.09  
- **Key Takeaway:**  
  Student performance is most affected by **study time**, **attendance**, and **previous academic record**. Random Forest provides the most reliable exam score predictions.

---
