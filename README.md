# 🏎️ Formula 1 Race Outcome Prediction

A Machine Learning and Data Mining project that predicts whether a Formula 1 driver will finish in the points (Top 10) using historical race data, qualifying results, telemetry, pit stop statistics, and championship standings.

## 📌 Overview

This project combines 14 Formula 1 datasets into a unified analytical warehouse and applies machine learning techniques to:

* Predict Top 10 race finishes
* Compare multiple classification models
* Analyze race-performance factors
* Discover driver performance patterns through clustering

## 🎯 Project Goals

* Build a complete F1 data warehouse from multiple datasets
* Engineer predictive race-performance features
* Train and compare classification models
* Identify key factors influencing race outcomes
* Validate predictions on unseen season data

## 📊 Dataset

Source:

* Kaggle: https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020

The dataset contains historical Formula 1 data including:

* Drivers
* Constructors
* Race Results
* Qualifying Sessions
* Lap Times
* Pit Stops
* Championship Standings
* Sprint Results
* Circuits & Seasons

## 🤖 Models Used

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier
* Gradient Boosting Classifier

### Best Performing Model

**Gradient Boosting Classifier**

Approximate Performance:

| Metric    | Score |
| --------- | ----- |
| Accuracy  | ~81%  |
| Precision | ~79%  |
| Recall    | ~77%  |
| F1 Score  | ~78%  |

## 🔍 Clustering

K-Means clustering was applied to identify driver-race performance archetypes using telemetry-based features.

## 🛠️ Tech Stack

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn

## 📂 Project Structure

```text
├── data/
├── notebooks/
├── reports/
├── visualizations/
├── models/
├── README.md
```

## 📄 Report

A detailed project report containing methodology, feature engineering, EDA, model evaluation, clustering analysis, and conclusions is included in the repository.

## 👨‍💻 Authors

* Yuvraj Shrirame
* Raj Wagh

## 📜 License

This project is licensed under the MIT License.

