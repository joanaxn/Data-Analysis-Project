# Crime Data Analysis & Machine Learning (Maryland, USA)

End-to-end data science project developed for the **Laboratory of Data Analysis (Informatics Engineering, 2024/2025)**.  
Using **200,000+ real crime records** from **Maryland (USA)** (2016–2020), the project covers **data cleaning**, **exploratory and statistical analysis**, **visualization**, and **machine learning** (classification, regression, PCA, and clustering), plus an **interactive Streamlit dashboard** for predictions.

---

## Dataset

- Scope: Maryland (USA), **July 2016 → December 2020**
- Size: **200k+ records**, ~30 features
- Examples of features: crime category (Crime Name1/2/3), police district, city/zip code, victims, timestamps, latitude/longitude, etc.

---

## Project Goals

- Explore crime patterns across **time** (year/month/hour/period) and **space** (city/district/zip/coordinates)
- Identify hotspots and trends through **EDA + visual analytics**
- Build predictive models:
  - **Classification:** predict main crime category (**Crime Name1**)
  - **Regression:** estimate operational outcomes (e.g., response time, crime duration)
- Evaluate whether **PCA** can reduce dimensionality without performance loss
- Provide a simple **Streamlit UI** for model-based prediction and evaluation viewing

---

## Data Preprocessing

Main steps applied:

- Filtered dataset to keep only records from **Maryland (MD)**
- Converted timestamp columns to `datetime`
- Extracted temporal features:
  - **Year**, **Month**, **Hour**
  - **Period of day** (Morning / Afternoon / Night)
- Encoded categorical variables (e.g., Police District, Crime Name1)
- Normalized continuous features using **StandardScaler**
- Prepared a modeling dataset with selected predictive features

---

## Exploratory & Statistical Analysis

The analysis includes:

- Descriptive statistics (mean, median, variance, quartiles, ranges)
- Frequency distributions (most common crime categories, cities, districts, places, street types)
- Covariance and Pearson correlation studies between key variables
- Visual exploration of:
  - Crime type distribution and subtypes
  - Crime evolution over years and months
  - Hourly patterns and time-of-day behavior
  - Geographic hotspots (cities, zip codes, districts, lat/long density)
  - Victim distribution per crime category
  - Police response time differences by city and crime type

**Key EDA findings (high level):**
- **Crime Against Property** is the dominant category.
- Crime activity shows clear **time-of-day** and **seasonal** patterns.
- Hotspots repeatedly appear around cities like **Silver Spring, Gaithersburg, Rockville**.

---

## Machine Learning

### Classification: Predicting Crime Category (Crime Name1)

Models tested:

- Decision Tree
- Random Forest
- Gradient Boosting ✅ (best overall)
- K-Nearest Neighbors
- Support Vector Classifier (SVC)
- Naive Bayes
- Neural Network (MLP)

Evaluation metrics:

- Accuracy, Precision, Recall, F1-score
- Confusion Matrix

**Best classification model:** **Gradient Boosting Classifier** (~**66% accuracy**)  
Random Forest achieved similar performance and was also a strong option.

---

### Regression: Response Time / Crime Duration Estimation

Models tested:

- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor ✅ (best)
- KNN Regressor
- Neural Network Regressor
- Ridge Regression
- Lasso Regression
- Support Vector Regressor (SVR)

Metrics used:

- MAE, MSE
- R²

**Best regression model:** **Gradient Boosting Regressor** (R² ≈ **0.76**)

---

### PCA (Dimensionality Reduction)

- PCA reduced feature space (5 → 4 components).
- Gradient Boosting with PCA maintained similar classification performance, showing PCA can preserve results while reducing dimensionality.

---

### Clustering

- Applied **KMeans** and **Agglomerative Clustering**
- Used **Elbow Method** and **Silhouette Score**
- Chosen configuration: **4 clusters**
- Clustered crimes using **Crime Duration** and **Hour** to observe behavior patterns across the day.

---

## Streamlit Dashboard

A Streamlit interface is included to:

- Input feature values and predict **Crime Name1**
- Toggle PCA-enabled predictions
- Visualize model evaluation:
  - Confusion matrix
  - Classification report

---

## Tech Stack

- **Python**
- **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**
- **Scikit-learn**
- **Streamlit**

---

## How to Run

> Make sure you have Python installed (3.9+ recommended).

1) Install dependencies:
```bash
pip install -r requirements.txt
