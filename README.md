# 🚢 Titanic Dataset Preparation & Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626.svg?style=for-the-badge&logo=Jupyter&logoColor=white)

> **Course:** Unit I – Foundations & Data Preparation  
> **Activity:** Dataset Preparation Activity (5 Marks)

## 📖 Project Overview
This repository contains a complete data preparation and exploratory data analysis (EDA) pipeline for the classic **Titanic Dataset**. The objective of this project is to inspect a raw, real-world dataset, identify data-quality issues, handle missing values logically, visualize key trends, and engineer the data into a clean format suitable for a downstream machine learning workflow. 

*Note: As per the activity instructions, model training is not included in this phase.*

---

## 📊 Dataset Information
* **Dataset Name:** Titanic - Machine Learning from Disaster (Training Set)
* **Source Link:** [datasciencedojo/datasets/titanic.csv](https://github.com/datasciencedojo/datasets/raw/master/titanic.csv)
* **File Type:** `.csv`
* **Initial Dimensions:** 891 rows × 12 columns
* **Target Variable:** `Survived` (0 = Died, 1 = Survived)
* **Domain:** Historical / Transport

---

## 🛠️ Tech Stack
* **Environment:** Google Colab / Jupyter Notebook
* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`
* **Preprocessing:** `scikit-learn`

---

## ⚙️ Data Preparation Pipeline
The notebook (`Activity1_Dataset_Preparation.ipynb`) executes a structured 10-step data preparation process:

### 1. Inspection & Profiling
Loaded the dataset via URL and separated numerical (e.g., `Age`, `Fare`) from categorical (e.g., `Sex`, `Embarked`) features. The `PassengerId` was identified as a non-predictive identifier.

### 2. Missing Value Analysis
Identified missing data in three columns:
| Column | Missing Count | Percentage | Action Taken |
| :--- | :--- | :--- | :--- |
| `Cabin` | 687 | 77.1% | **Dropped** (Too sparse to impute reliably) |
| `Age` | 177 | 19.9% | **Median Imputation** (Robust to outliers) |
| `Embarked` | 2 | 0.2% | **Mode Imputation** (Most frequent category) |

### 3. Data Cleaning & Consistency
* Verified that **no duplicate rows** were present.
* Checked categorical labels (e.g., `Sex`, `Embarked`) for spelling inconsistencies and extra whitespace; none were found requiring correction.

### 4. Exploratory Data Analysis (EDA)
* **Univariate Analysis:** Generated a histogram to understand the distribution of passenger `Age` (post-imputation), revealing a right-skewed distribution peaking in the 20s.
* **Bivariate Analysis:** Created a grouped bar chart displaying survival rates by `Pclass` and `Sex`, confirming the historical "women and children first" protocol (females in 1st/2nd class had >90% survival, while males in 3rd class had ~13%).

### 5. Feature Engineering & Transformation
* **Encoding:** Applied **One-Hot Encoding** to nominal variables (`Sex`, `Embarked`), using `drop_first=True` to prevent multicollinearity (dummy variable trap).
* **Scaling:** Applied **StandardScaler** (Z-score normalization) to continuous features (`Age`, `Fare`, `SibSp`, `Parch`) to ensure uniform magnitude for distance-based ML algorithms. ID and target variables were explicitly excluded from scaling.

---

## 📁 Repository Contents
* `Activity1_Dataset_Preparation.ipynb`: The Jupyter Notebook containing the full Python code, Markdown explanations, and visual outputs.
* `titanic_prepared.csv`: The final, cleaned, encoded, and scaled dataset ready for machine learning.
* `README.md`: Project documentation.

---

## 🚀 How to Run the Project

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
