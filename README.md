# 🚗 Used Car Market Intelligence & Pricing Insights

## 📌 Project Overview

This project analyzes a real-world used-car marketplace dataset to generate pricing intelligence and understand how factors such as:
- brand
- mileage
- vehicle age

affect resale value.

The goal is to transform messy marketplace data into actionable insights for:
- buyers
- sellers
- dealers
- marketplace platforms

---

## 🎯 Business Objectives

- Establish pricing benchmarks across brands
- Analyze depreciation trends
- Identify brands with strong value retention
- Understand mileage impact on resale pricing
- Build a simple pricing estimator

---

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- VS Code
- Jupyter Notebook

---

## 📂 Project Structure

```text
car-pricing-intelligence/
│
├── analysis.ipynb
├── cleaned_autos.csv
├── pricing_estimator.csv
├── README.md
│
├── outputs/
│   └── charts/
│
└── reports/
```

---

# 🧹 Data Cleaning & Preparation

Key preprocessing steps included:

- Fixed dataset encoding issues using `latin1`
- Removed invalid zero-priced listings
- Removed extreme price outliers above 100,000
- Standardized column names into snake_case
- Converted mileage values from text to numeric format
- Created vehicle age feature
- Filtered unrealistic vehicle ages

---

# 📊 Exploratory Data Analysis (EDA)

## 📈 Vehicle Price Distribution

### Key Findings
- Vehicle prices are heavily right-skewed
- Most listings fall within the low-to-mid price range
- Premium vehicles form a smaller high-price segment

![Vehicle Price Distribution](outputs/charts/price_distribution.png)

---

## 📉 Price vs Mileage

### Key Findings
- Higher mileage strongly correlates with lower resale prices
- Low-mileage vehicles command premium pricing
- Depreciation becomes more significant at higher mileage ranges

![Price vs Mileage](outputs/charts/price_vs_mileage.png)

---

## 🚗 Price vs Vehicle Age

### Key Findings
- Vehicle prices decrease as vehicle age increases
- Depreciation is steepest during the early years
- Older vehicles stabilize within lower price ranges

![Price vs Vehicle Age](outputs/charts/price_vs_vehicle_age.png)

---

# 🏆 Value Retention Analysis

### Key Findings
- Mercedes-Benz, BMW, and Audi retained stronger resale value
- Toyota showed smoother long-term depreciation
- Volkswagen demonstrated stable mid-market positioning
- Premium brand advantages reduced gradually with age

![Vehicle Depreciation by Brand](outputs/charts/value_retention_by_brand.png)

---

# 🧮 Pricing Estimator

A simple rule-based pricing estimator was developed using:

- Brand
- Mileage band
- Vehicle age band

The estimator returns:
- average price
- median price
- estimated pricing ranges

This provides an interpretable pricing intelligence tool for:
- buyers
- dealers
- marketplace platforms

---

# 📌 Key Insights

- Mileage and vehicle age are major drivers of depreciation
- Premium brands maintain higher resale value over time
- Most used-car listings exist within the affordable-to-mid-range market
- Data cleaning significantly improved interpretability and analysis reliability

---

# 🚀 Future Improvements

- Machine learning price prediction model
- Interactive dashboard
- Market segmentation analysis
- Underpriced vs overpriced vehicle detection
- Deployment as a web application

---

# 📚 Learning Outcomes

This project strengthened skills in:
- real-world data cleaning
- exploratory data analysis
- business intelligence
- statistical reasoning
- pricing analysis
- data storytelling

---

# 📬 Connect With Me

I’m documenting my journey into data science and analytics through real-world projects and public learning.

- GitHub
- LinkedIn
- X (Twitter)
