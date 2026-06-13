# 🏎️ Formula 1 Race Outcome Prediction & Driver Clustering

A comprehensive Data Mining and Machine Learning project built on the complete historical Formula 1 dataset.

This project combines predictive analytics, feature engineering, ensemble machine learning, and unsupervised clustering to analyze Formula 1 race performance and predict whether a driver will finish in the points (Top 10).

---

## 📌 Project Overview

Formula 1 is a highly data-driven sport where race outcomes depend on multiple factors including qualifying performance, starting grid position, team strength, pit stop efficiency, and race pace.

This project constructs a unified analytical data warehouse by merging **14 relational Formula 1 datasets** and applies machine learning techniques to:

- Predict Top 10 race finishes
- Compare classification algorithms
- Discover driver performance archetypes using clustering
- Perform temporal validation on the latest season

---

## 🎯 Objectives

- Merge 14 relational F1 datasets into a single analysis-ready warehouse
- Engineer race-performance and telemetry-based features
- Predict Top 10 race finishes using machine learning
- Compare multiple classification models
- Discover driver archetypes through clustering
- Validate predictions using real-world season data

---

## 🗂 Dataset Architecture

The project utilizes 14 interconnected Formula 1 datasets:

| Dataset |
|----------|
| circuits |
| races |
| results |
| drivers |
| constructors |
| status |
| driver_standings |
| constructor_standings |
| constructor_results |
| qualifying |
| lap_times |
| pit_stops |
| sprint_results |
| seasons |

### Pre-Aggregated Features

Telemetry tables were aggregated before merging:

| Feature | Description |
|----------|------------|
| lap_variance | Standard deviation of lap times |
| total_pit_stops | Total pit stops in race |
| avg_pit_duration | Average pit stop duration |
| sprint_points | Sprint race points |

---

## 🧹 Data Cleaning

Data preprocessing included:

- Replacing `\N` values with `NaN`
- Numeric type conversion
- Missing value imputation
- Outlier removal
- Telemetry completeness filtering
- Feature scaling using `StandardScaler`

---

## 🎯 Target Variable

```python
Points_Finish = 1 if positionOrder <= 10 else 0
```

Binary classification problem:

- **1 → Driver finishes in points**
- **0 → Driver finishes outside points**

---

## 🔧 Feature Engineering

Final model features:

| Feature | Description |
|----------|------------|
| grid | Starting grid position |
| position_quali | Qualifying position |
| lap_variance | Race consistency indicator |
| avg_pit_duration | Pit crew efficiency |
| fastestLapSpeed | Peak pace metric |
| sprint_points | Sprint race performance |
| team_encoded | Constructor strength |

---

## 📊 Exploratory Data Analysis

### 1. Starting Grid Position Distribution
- Nearly uniform distribution across historical races.
- Slight concentration among front-row starters.

### 2. Pit Stop Duration Analysis
- Significant variation across constructors.
- Operational efficiency impacts race outcomes.

### 3. Correlation Analysis
Strongest predictors:

- Grid Position
- Qualifying Position
- Fastest Lap Speed

### 4. Grid Position vs Outcome
Key observation:

- Positions 1–5 have >70% probability of scoring points.
- Positions 11+ show significantly lower Top-10 conversion rates.

---

## 🤖 Machine Learning Models

Four classification models were trained and evaluated.

### Logistic Regression
```python
class_weight='balanced'
```

### Decision Tree
```python
max_depth=8
class_weight='balanced'
```

### Random Forest
```python
n_estimators=200
max_depth=12
class_weight='balanced'
```

### Gradient Boosting ⭐
```python
n_estimators=200
learning_rate=0.1
max_depth=5
```

Selected as the final production model.

---

## 📈 Model Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|---------|----------|-----------|---------|----------|
| Logistic Regression | ~0.71 | ~0.68 | ~0.66 | ~0.67 |
| Decision Tree | ~0.74 | ~0.71 | ~0.70 | ~0.70 |
| Random Forest | ~0.78 | ~0.76 | ~0.74 | ~0.75 |
| **Gradient Boosting** | **~0.81** | **~0.79** | **~0.77** | **~0.78** |

🏆 **Best Model: Gradient Boosting Classifier**

---

## 🔍 Driver Performance Clustering

K-Means clustering was applied to identify natural driver-race performance groups.

### Clustering Features

- fastestLapSpeed
- avg_pit_duration
- lap_variance

### Results

| Cluster | Interpretation |
|-----------|---------------|
| Cluster 0 | Normal race conditions |
| Cluster 1 | Unusual pace events |
| Cluster 2 | Extreme telemetry outliers |

### Silhouette Score

```text
0.9375
```

Indicating excellent cluster separation.

---

## ⏳ Temporal Validation

To simulate real-world deployment:

### Training Data
```text
All seasons before target year
```

### Test Data
```text
Most recent F1 season
```

The model predicts Top 10 finishers race-by-race and evaluates real-world predictive performance.

---

## 📚 Tech Stack

### Languages
- Python

### Libraries
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

### Machine Learning
- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- K-Means Clustering
- PCA

---

## 🚀 Key Findings

### Predictive Modeling

- Grid position is the strongest predictor of points finishes.
- Qualifying performance heavily influences race outcome.
- Ensemble methods outperform linear models.
- Gradient Boosting delivers the best overall results.

### Clustering

- F1 race telemetry naturally separates into distinct archetypes.
- Extreme events such as safety cars and mechanical failures form unique clusters.
- Log-transformed clustering improves interpretability.

---

## 📂 Project Structure

```text
Formula1-Data-Mining/
│
├── data/
│   ├── circuits.csv
│   ├── races.csv
│   ├── results.csv
│   └── ...
│
├── notebooks/
│   ├── data_cleaning.ipynb
│   ├── eda.ipynb
│   ├── modeling.ipynb
│   └── clustering.ipynb
│
├── visualizations/
│
├── models/
│
├── reports/
│
├── requirements.txt
│
└── README.md
```

---

## 👨‍💻 Authors

**Yuvraj Shrirame**  
**Raj Wagh**

---

## 📜 License

This project is licensed under the MIT License.

---

### ⭐ If you found this project useful, consider giving it a star!
