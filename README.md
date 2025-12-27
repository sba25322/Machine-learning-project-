# Machine-learning-project-

# Academic Scores Analysis using Machine Learning

## Introduction
Machine learning aims to create self-learning computers that can analyze data, discover patterns, and automate decision-making by predicting unseen data using historical datasets (Jordan and Mitchell, 2015). With these capabilities, machine learning can enhance the performance of companies, organizations, and both private and public sectors.

In this project, a detailed analysis was conducted on the `academic_scores.csv` dataset, which focuses on students’ performance in mathematics. The target variable is the final grade (`G3`). The primary objective was to identify the key features that influence or predict `G3`.

---

## Exploratory Data Analysis (EDA)
The following steps were conducted for EDA:

- **Dataset Overview**
  - The dataset contains **399 columns and 6 rows**.
  - Checked for missing values: none were found; the dataset is clean.
  - Primary numeric variables of interest: `G1`, `G2`, and `G3`.

- **Descriptive Statistics**
  - `G1`, `G2`, and `G3` have similar averages, standard deviations, and maximum values, suggesting a possible linear relationship.
  
- **Visualizations**
  - **Histograms:** Showed a normal distribution of grades, with most students scoring between 7.5 and 15.
  - **Scatter Plots:** 
    - `G1` vs `G3` shows a moderate correlation.
    - `G2` vs `G3` shows a stronger correlation, consistent with the two-year progression between the grades.

- **Correlation Analysis**
  - `G2` vs `G3`: 0.9 (very strong)
  - `G1` vs `G3`: 0.8 (strong)

---

## Machine Learning Application

### Data Preparation
- Categorical variables (e.g., `School`, `Sex`) were encoded for numerical compatibility.
- Data was split into training and testing datasets with different `test_size` ratios.

### Models & Evaluation
- **Evaluation Metric:** R² score was used to measure predictive accuracy.
- **Techniques Used:** Linear Regression, Random Forest, Support Vector Machine (SVM), and Cross Validation.
- **Hyperparameter Tuning:** Applied to optimize model performance and reduce overfitting (Justus et al., 2024; Berrar, 2019).

### Results by Test Size

#### Test Size = 20%
- Linear Regression: 74.77%
- Random Forest: 0.44% (weak)
- SVM (linear kernel): 75%
- Cross Validation: 76%

#### Test Size = 15%
- Linear Regression: 83%
- Random Forest (n_estimators=100, max_depth=4, max_features=5, random_state=42): 76%
- SVM (C=10, kernel='linear'): 69%
- Cross Validation: 76%

#### Test Size = 10%
- Linear Regression (fit_intercept=True): 78%
- Random Forest (n_estimators=100, max_depth=5, random_state=0): 67%
- SVM (C=10, kernel='linear'): 66%
- Cross Validation: 76%

**Observations:**  
- Linear Regression consistently performed best, showing a clear linear relationship between features and target (`G3`).  
- Random Forest and SVM performed reasonably well but were outperformed by Linear Regression in this dataset.  

---

## Conclusion
- `G1` and `G2` are the strongest predictors of the final grade `G3`.
- Linear Regression achieved the highest accuracy across multiple test splits (70%-85%) and outperformed other models.
- Cross-validation confirmed that the results are generalizable and robust.
- Overall, **Linear Regression is the most suitable model for predicting students’ final grades** in this dataset.

---

## References
1. Jordan, M.I. and Mitchell, T.M., 2015. Machine learning: Trends, perspectives, and prospects. *Science*, 349(6245), pp.255-260.  
2. Berrar, D., 2019. Cross-validation.  
3. Ilemobayo, J., Durodola, O., Alade, O., Awotunde, J., Olanrewaju, T., Falana, A., Ogungbire, A., Osinuga, A., Ogunbiyi, D., Ifeanyi, A. and Odezuligbo, I., 2024. Hyperparameter tuning in machine learning: A comprehensive review. *Journal of Engineering Research and Reports*, 26(6), pp.388-395.
