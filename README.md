# Flight Price Prediction (R)

**Predicting airline ticket prices using regression models**, feature interactions, and regularized techniques in R.  
This project delivers both **data-driven insights** into pricing factors and a **reproducible ML pipeline**.


---

## Overview
Airline ticket pricing is highly dynamic and influenced by multiple factors: airline, route, class, stops, flight duration, and booking window.  
The goal of this project is to:
- Analyze historical flight pricing data
- Train multiple regression models
- Identify the most reliable predictors for **price estimation**

---

## 📊 Dataset
- **Source:** [Kaggle – Flight Price Prediction Dataset](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction)  
- **File Required:** `data/raw/Clean_Dataset.csv`  
- **Features:**
  - `airline` – Airline name  
  - `source_city` / `destination_city` – Origin & destination  
  - `class` – Economy / Business  
  - `stops` – Number of stops  
  - `duration` – Flight duration (hours)  
  - `days_left` – Days before departure  
  - `price` – Target variable  



---

## 🔎 Exploratory Data Analysis (EDA)

Some highlights from the dataset exploration:

### Price Distribution
![Price Distribution](reports/figures/price_distribution.png)

### Flights by Airline
![Flights by Airline](reports/figures/count_by_airline.png)

### Ticket Prices by Class
![Ticket Prices by Class](reports/figures/price_by_class.png)

### Average Flight Duration by Source City
![Avg Duration by Source City](reports/figures/avg_duration_by_source.png)

### Stops Distribution
![Stops Pie Chart](reports/figures/stops_pie.png)

### Correlation Plot
![Correlation Matrix](reports/figures/correlation_plot.png)

---

## 🤖 Models Implemented
1. **Linear Regression** (baseline)  
2. **Interaction Model** (captures route & time interactions)  
3. **Polynomial Regression** (quadratic term for duration)  
4. **Lasso Regression** (L1 regularization)  
5. **Ridge Regression** (L2 regularization)  
6. **Subset Selection** (forward search for best predictors)  

---

## 📈 Results (Test Set)

| Model                  | RMSE   | R²     | Adj. R² |
|------------------------|--------|--------|---------|
| Linear Regression      | ~6790  | ~0.911 | ~0.911 |
| **Interaction Model**  | **~6698** | **~0.913** | **~0.913** |
| Polynomial Regression  | ~6772  | ~0.911 | ~0.911 |
| Lasso Regression       | ~6792  | ~0.911 | ~0.910 |
| Ridge Regression       | ~7072  | ~0.909 | ~0.909 |
| Subset Selection       | ~6800+ | ~0.910 | ~0.910 |

✅ **Best Model:** Interaction Regression — route & time interactions significantly improve predictions.

---

## 📊 Actual vs Predicted (Sample Plots)

### Interaction Model
![Actual vs Predicted (Interaction)](reports/figures/actual_vs_pred_interaction.png)

### Polynomial Regression
![Actual vs Predicted (Poly)](reports/figures/actual_vs_pred_poly.png)

### Lasso Regression
![Actual vs Predicted (Lasso)](reports/figures/actual_vs_pred_lasso.png)

---

## 🛠️ Tech Stack
- **Language:** R  
- **Libraries:** `ggplot2`, `dplyr`, `ggcorrplot`, `caTools`, `glmnet`, `Metrics`, `caret`, `leaps`, `readr`  
- **Reproducibility:** Quarto report, Makefile, GitHub Actions (CI)  

---

## 🚀 How to Run

### 1. Clone the repo
```bash
git clone https://github.com/Ganateja19/Flight-Price-Prediction-using-R.git
cd Flight-Price-Prediction-using-R
