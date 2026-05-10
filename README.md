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

# 📈 Progress & Findings So Far
## ✅ Project Progress

### 1. Data Loading
The dataset was loaded using `pandas`. An encoding issue occurred because the CSV file was not UTF-8 encoded.

```python
df = pd.read_csv("autos.csv", encoding="latin1")
