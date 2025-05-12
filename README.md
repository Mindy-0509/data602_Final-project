# data602_Final-project
Predicting whether a crime is solved
# Crime Case Solvability Classification 

This project is my final submission for the **UMBC DATA602 (Introduction to Machine Learning)** course.  
The goal is to build a classification model to predict whether a reported crime case in Los Angeles is likely to be solved.

---

## Project Objective

**Business Question**:  
Based on available features such as the time of occurrence, victim characteristics, location, and the delay between crime and report,  
can we predict whether a crime case will be solved (i.e., lead to an arrest or closure)?

---

## Dataset

- **Source**: [Los Angeles Open Data Portal](https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8)
- **Size**: Over 1 million crime records (2020–present)
- **Features used**:
  - Date/Time of crime and report
  - Victim age, sex, descent
  - Crime description, premise type, police area
  - Derived features: weekday, hour, time period, report delay

---

## EDA and Feature Engineering

Key steps:
- Removed redundant or high-missing-value columns
- Created `Occ_Year`, `Occ_Month`, `Occ_Weekday`, and `Time_Period`
- Calculated `Report_Delay_Days` (difference between DATE OCC and Date Rptd)
- Labeled the target variable `is_solved` based on case status

---

## Models Compared

| Model               | Accuracy | Precision (class 1) | Recall (class 1) | F1-score (class 1) | ROC AUC |
|--------------------|----------|----------------------|------------------|--------------------|---------|
| Logistic Regression| 0.840    | 0.663                | 0.412            | 0.508              | 0.849   |
| Decision Tree      | 0.834    | 0.677                | 0.328            | 0.441              | 0.774   |
| Random Forest      | 0.845    | 0.679                | 0.429            | 0.526              | 0.858   |

**Final Model Selected**: **Random Forest**, based on its strong ROC AUC and balanced precision-recall performance.

---

## Key Visuals

- Top 20 crime types by frequency
- Crimes by weekday and hour
- ROC curves of all models
- Bar chart comparing ROC AUC across models

---

## Future Improvements

- Apply hyperparameter tuning (GridSearchCV) for optimal model performance
- Incorporate spatial clustering or neighborhood-level features
- Address class imbalance with SMOTE or class weights
- Experiment with XGBoost or LightGBM for performance boost

---

## Project Structure

/data602-crime-classification/
├── data/
│ └── Crime_Data_from_2020_to_Present.csv
├── notebook/
│ └── Data_602_Final_Project.ipynb
├── slides/
│ └── final_presentation.pptx
├── README.md

---

## Author

Min-Yi "Mindy" Shang  
Master of Professional Studies in Data Science  
University of Maryland, Baltimore County (UMBC) @ Shady Grove

