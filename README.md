# 🚗 Used Car Market Intelligence & Pricing Insights

## 📌 Project Overview

This project analyzes a real-world used car marketplace dataset to generate pricing intelligence and resale value insights.

The objective is to transform messy marketplace data into actionable business insights that can help:
- buyers
- sellers
- dealers
- marketplace platforms

make smarter pricing decisions.

---

## 🎯 Project Objectives

- Analyze resale prices across different brands
- Understand how mileage affects pricing
- Study depreciation trends using vehicle age
- Identify brands with strong value retention
- Build a simple pricing estimator

---

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- VS Code
- Jupyter Notebook

---

## 📂 Project Structure

```text
car-pricing-intelligence/
│
├── autos.csv
├── analysis.ipynb
├── README.md
└── outputs/
```

---

# Progress & Findings So Far
## Project Progress

### 1. Data Loading
The dataset was loaded using `pandas`. An encoding issue occurred because the CSV file was not UTF-8 encoded.

```python
df = pd.read_csv("autos.csv", encoding="latin1")

### 2. Price Cleaning

Initial inspection showed that the price column contained invalid and extreme values.

Key Findings
1,421 listings had a price of 0
Some listings had unrealistically high prices in the millions
The original price distribution was heavily distorted by outliers
Cleaning Decisions

Listings with price = 0 were removed because they likely represented missing or invalid prices.

```python
df = df[df["price"] > 0]

Price outliers were analyzed using percentiles:

| Percentile |  Price |
| ---------- | -----: |
| 90%        | 15,999 |
| 95%        | 22,000 |
| 99%        | 38,456 |
| 99.9%      | 99,370 |

Since 99.9% of listings were below approximately 100,000, prices above 100,000 were treated as extreme outliers.

```python
df = df[df["price"] < 100000]

