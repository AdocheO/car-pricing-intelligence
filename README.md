#  Used Car Market Intelligence & Pricing Insights

##  Project Overview

This project analyzes a real-world used car marketplace dataset to generate pricing intelligence and resale value insights.

The objective is to transform messy marketplace data into actionable business insights that can help:
- buyers
- sellers
- dealers
- marketplace platforms

make smarter pricing decisions.

---

##  Project Objectives

- Analyze resale prices across different brands
- Understand how mileage affects pricing
- Study depreciation trends using vehicle age
- Identify brands with strong value retention
- Build a simple pricing estimator

---

##  Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- VS Code
- Jupyter Notebook

---

##  Project Structure

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
```

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
```

### 3. Vehicle Age Preparation

The yearOfRegistration column was inspected to identify unrealistic years.

Vehicle age was treated carefully because using the current year could distort the analysis. Since the prices represent historical listing prices, vehicle age should be calculated relative to the dataset period rather than today’s year.

```python
df["vehicleAge"] = 2018 - df["yearOfRegistration"]
```
### 4. Mileage Cleaning

The odometer column was originally stored as text, with values such as:

150,000km

The column was cleaned by removing km, removing commas, and converting the values to numeric format.

```python
df["odometer"] = df["odometer"].str.replace("km", "", regex=False)
df["odometer"] = df["odometer"].str.replace(",", "", regex=False)
df["odometer"] = pd.to_numeric(df["odometer"])
```
Key observation:

The most common mileage category was 150,000km
The column had only 13 unique mileage groups, meaning mileage was bucketed

## Early EDA Findings
Average Resale Price by Brand
| Brand         | Average Price | Listings |
| ------------- | ------------: | -------: |
| Porsche       |     36,057.63 |      219 |
| Land Rover    |     20,360.77 |       83 |
| Jaguar        |     13,194.43 |       58 |
| Jeep          |     11,879.97 |       87 |
| Mini          |     10,957.37 |      366 |
| Audi          |     10,523.18 |    3,167 |
| Mercedes-Benz |      9,411.03 |    3,553 |
| BMW           |      9,106.06 |    4,035 |
| Chevrolet     |      7,236.18 |      200 |
| Skoda         |      6,891.92 |      640 |


## 📊 Exploratory Data Analysis (EDA)

### Price Distribution After Cleaning

The original dataset contained:
- invalid zero-priced listings
- extreme outliers in the millions

After cleaning:
- the distribution became more interpretable
- market pricing trends became clearer

![Price Distribution](outputs/charts/price_distribution.png)


