# 🏥 Diabetes Prediction & EDA Analysis

A complete Data Science project covering Exploratory Data Analysis (EDA),
data cleaning, feature engineering, visualization, and machine learning
model comparison on the Pima Indians Diabetes Dataset.

---

## 📌 Project Overview

The goal of this project is to analyze health indicators and predict
whether a patient has diabetes or not using supervised machine learning.
This project follows a complete Data Science workflow — from raw data
cleaning to model evaluation.

---

## 📂 Dataset

- **Name:** Pima Indians Diabetes Database
- **Source:** [Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
- **Size:** 768 rows × 9 columns
- **Target Variable:** `Outcome` (0 = No Diabetes, 1 = Diabetes)

### Features:
| Column | Description |
|--------|-------------|
| Pregnancies | Number of pregnancies |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skin fold thickness (mm) |
| Insulin | 2-Hour serum insulin (mu U/ml) |
| BMI | Body Mass Index |
| DiabetesPedigreeFunction | Diabetes pedigree function (genetic score) |
| Age | Age in years |
| Outcome | Target variable (0 or 1) |

---

## 🔧 Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python | Programming language |
| Pandas | Data loading & manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Advanced visualization |
| Scikit-learn | ML models & evaluation |
| Google Colab | Development environment |

---

## 🗺️ Project Workflow

### 1. 🧹 Data Cleaning
- Identified medically impossible zero values in columns like
  Glucose, Insulin, BMI, BloodPressure, and SkinThickness
- Replaced zeros with NaN (treated as missing values)
- Detected real outliers using boxplots (IQR method)
- Applied **Winsorization (IQR capping)** on Insulin, SkinThickness,
  and BMI — columns with medically unrealistic extreme values
- Kept BloodPressure outliers as they represent real conditions
  like hypertension
- Filled remaining NaN values with **median** to avoid skewing
  from outliers

### 2. ⚙️ Feature Engineering
- Created **BMI Category** column:
  - Underweight (BMI < 18.5)
  - Normal (18.5 ≤ BMI < 25)
  - Overweight (25 ≤ BMI < 30)
  - Obese (BMI ≥ 30)
- Created **Age Group** column:
  - Young (Age < 30)
  - Middle (30 ≤ Age < 50)
  - Senior (Age ≥ 50)

### 3. 📊 Exploratory Data Analysis (EDA)
- **Countplots** — Diabetes distribution by Age Group and BMI Category
- **Correlation Heatmap** — Feature relationships with Outcome
- **Violin Plots** — Feature distributions for diabetic vs non-diabetic
- **Pairplot** — Combined feature interactions colored by Outcome

### 4. 🤖 ML Modeling & Comparison
- Applied **StandardScaler** for feature scaling
- Trained and compared 4 models:
  - Logistic Regression
  - K-Nearest Neighbors (KNN)
  - Decision Tree
  - Random Forest
- Evaluated using Accuracy, Precision, Recall, F1-Score
- Visualized **Confusion Matrices** for all 4 models

---

## 📈 Key EDA Findings

- **Glucose** is the strongest predictor of diabetes (0.49 correlation)
- **BloodPressure** is the weakest predictor (0.17 correlation)
- Diabetes risk nearly **doubles after age 30**
- **Obese patients** show a 46% diabetes rate vs 9% for Normal BMI
- Glucose + Age combination provides the clearest visual separation
  between diabetic and non-diabetic patients

---

## 🏆 Model Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | **0.753** | 0.667 | 0.618 | 0.642 |
| KNN | 0.727 | 0.603 | **0.691** | 0.644 |
| Decision Tree | 0.695 | 0.569 | 0.600 | 0.584 |
| Random Forest | 0.740 | 0.627 | 0.673 | **0.649** |

### 🎯 Model Selection Conclusion

> In medical datasets, **Recall is more important than Accuracy.**
> Missing a diabetic patient (false negative) is far more dangerous
> than a false alarm (false positive).

- **Best Accuracy** → Logistic Regression (0.753)
- **Best Recall** → KNN (0.691) — best for catching all diabetic cases
- **Best Overall Balance** → Random Forest (F1: 0.649)

For a medical use case focused on catching all positive cases,
**KNN or Random Forest** would be the recommended model.

---

## 📁 Project Structure

```
Diabetes_EDA_Project/
│
├── Diabetes_EDA_Project.ipynb   # Main notebook
└── README.md                     # Project documentation
```

---

## 🚀 How to Run

1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
2. Open `Diabetes_EDA_Project.ipynb` in Google Colab
3. Upload `diabetes.csv` when prompted
4. Run all cells from top to bottom

---

## 👨‍💻 Author

**Laxmi B**
- GitHub: [@Laxmib123](https://github.com/Laxmib123)

---

## 📚 Skills Demonstrated

- Medical data cleaning & domain-aware outlier handling
- Feature engineering from raw data
- EDA storytelling with visualizations
- Multi-model comparison and evaluation
- Understanding of medical metrics (Recall vs Accuracy)
