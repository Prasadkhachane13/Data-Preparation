#Titanic Dataset Preparation & Exploratory Data Analysis

📌 Project Overview
This repository contains the  Dataset Preparation Activity ( Foundations & Data Preparation). The objective of this project is to inspect a raw tabular dataset, identify data-quality issues, handle missing values, perform basic exploratory data analysis (EDA), and prepare the data for a future machine learning workflow.


📊 Dataset Information
Dataset Name: Titanic - Machine Learning from Disaster (Training Set)

Source Link: datasciencedojo/datasets/titanic.csv

File Type: CSV

Initial Dimensions: 891 rows × 12 columns

Target Variable: Survived (0 = Died, 1 = Survived)

Domain: Historical / Transport

🛠️ Tools & Libraries Used
Environment: Google Colab / Jupyter Notebook

Language: Python

Libraries:

pandas (Data manipulation and cleaning)

numpy (Numerical operations)

matplotlib & seaborn (Data visualization)

scikit-learn (Feature scaling)

⚙️ Data Preparation Steps
The notebook (Activity1_Dataset_Preparation.ipynb) follows a structured 10-step process:

Dataset Selection & Loading: Loaded the raw CSV file directly from the provided GitHub URL.

Inspection: Examined the shape, data types, and basic statistics of the dataset.

Missing Value Analysis: Identified missing data in three columns:

Cabin: 687 missing (77.1%)

Age: 177 missing (19.9%)

Embarked: 2 missing (0.2%)

Missing Value Handling:

Dropped the Cabin column entirely due to extreme sparsity (too much missing data to impute reliably).

Imputed missing Age values using the median (robust to outliers/skewness).

Imputed missing Embarked values using the mode (most frequent category).

Duplicate & Consistency Check: Verified no duplicate rows existed and confirmed categorical labels (e.g., 'male'/'female') were consistent.

Exploratory Data Analysis (EDA): Generated visualizations including an Age distribution histogram and a bar chart showing survival rates by passenger class and sex.

Categorical Encoding: Applied One-Hot Encoding to nominal features (Sex and Embarked) using drop_first=True to avoid multicollinearity.

Feature Scaling: Applied StandardScaler (Z-score normalization) to continuous numerical features (Age, Fare, SibSp, Parch) so they share a uniform scale for distance-based ML algorithms. Excluded PassengerId and the target Survived.

Final Verification: Confirmed zero remaining missing values and exported the cleaned dataframe.

📁 Repository Contents
Activity1_Dataset_Preparation.ipynb: The main Jupyter Notebook containing all code, explanations, and visual outputs.

titanic_prepared.csv: The final, cleaned, encoded, and scaled dataset ready for machine learning.

README.md: Project documentation (this file).
