# NYC Yellow Taxi Fare Analysis using Python & Statistics

## 📌 Project Overview

This project analyzes the **New York City Yellow Taxi Trip Data (January 2020)** to understand how **fare amount varies with trip duration, distance, passenger count, and payment type**, and to test whether payment method has a statistically significant impact on fares.

The project demonstrates **data cleaning, exploratory data analysis, statistical hypothesis testing, and regression modeling** using Python.

---

## Summary

### 🟢 Situation  
The NYC Yellow Taxi dataset contains **over 6 million trip records** with multiple data quality issues such as missing values, duplicates, invalid fares, and extreme outliers.  
The goal was to prepare this raw dataset for analysis and extract meaningful insights about fare behavior.

---

### 🔵 Task  
I was responsible for:

- Cleaning and preprocessing a large real-world dataset  
- Performing **exploratory data analysis (EDA)**  
- Testing whether **payment type (Card vs Cash)** impacts fare amount  
- Building a **linear regression model** to study the relationship between trip duration and fare  

---

### 🟡 Action  

I performed the following steps:

#### 1. Data Preprocessing & Cleaning
- Loaded the raw CSV file (`yellow_tripdata_2020-01.csv`)  
- Converted pickup and drop-off times to datetime  
- Created a new feature:  
  - `duration = dropoff_time - pickup_time` (in minutes)
- Selected key analytical columns:
  - `passenger_count`, `payment_type`, `fare_amount`, `trip_distance`, `duration`
- Handled missing values (~1.02% rows dropped)
- Removed duplicate records (reduced dataset from ~6.4M to ~3.0M rows)
- Filtered invalid data:
  - Passenger count between 1 and 5  
  - Payment types: Card & Cash only  
  - Removed negative/zero fare, distance, and duration  

#### 2. Outlier Treatment
- Applied **IQR method** on:
  - `fare_amount`
  - `trip_distance`
  - `duration`
- Removed extreme outliers to improve distribution quality  

#### 3. Exploratory Data Analysis
- Distribution analysis of:
  - Fare amount by payment type  
  - Trip distance by payment type  
- Created:
  - Histograms  
  - Boxplots  
  - Pie chart for payment type preference  
  - Stacked bar chart for passenger count vs payment type  

#### 4. Statistical Hypothesis Testing
- Performed **Independent Two-Sample T-Test**:

  - **H₀ (Null Hypothesis):**  
    Mean fare for Card = Mean fare for Cash  

  - **H₁ (Alternative Hypothesis):**  
    Mean fare for Card ≠ Mean fare for Cash  

- Result:
  - T-statistic ≈ **169.21**  
  - P-value ≈ **0.0**  
  - **Null hypothesis rejected** → Payment type significantly affects fare amount  

#### 5. Regression Analysis
- Built a **Linear Regression Model**:


- Model performance:
- **R² ≈ 0.76** (76% of fare variance explained by duration)
- P-value ≈ 0.0 → Strong statistical significance  

- Visualized:
- QQ Plot for normality check  
- Scatter plot with regression line  

---

### 🔴 Result  

Key outcomes from the project:

- Successfully cleaned and reduced a **6.4M row dataset** to a high-quality analytical dataset of **~2.3M rows**
- Found that:
- **Card payments dominate (~67%)**, Cash (~33%)
- Average fare for Card users is **higher than Cash users**
- The difference is **statistically significant**
- Built a regression model showing:
- Trip duration is a **strong predictor** of fare amount  
- Each additional minute increases fare by ~₹0.69 (unit as per dataset)

This project demonstrates strong skills in:
- Data cleaning & preprocessing  
- Exploratory data analysis  
- Statistical inference  
- Regression modeling  
- Visualization & storytelling  

---

## 🛠️ Tech Stack

- **Language:** Python  
- **Libraries:**
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scipy  
- statsmodels  
