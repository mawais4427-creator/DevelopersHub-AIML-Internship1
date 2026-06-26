# Task 2: Stock Price Prediction

**Internship:** DevelopersHub Corporation — AI/ML Engineering  
**Intern Name:** Muhammad Awais  
**Due Date:** 26th June, 2026  
**Difficulty:** Intermediate

---

## Objective

Download real stock market data from the internet, engineer features, train machine learning models to predict the next day's closing price, and visualize the results. This task teaches **regression** — predicting a number.

---

## Dataset

- **Stock:** Apple Inc. (AAPL)
- **Source:** Yahoo Finance via `yfinance` library (downloaded automatically)
- **Period:** January 2022 – January 2024 (2 years)
- **Size:** ~503 trading days
- **Columns:** Open, High, Low, Close, Volume

---

## Key Concepts

| Concept           | Explanation |
|---------------    |--------------------------------------------------|
| Regression        | ML where the output is a number (price), not a category |
| Features          | Input columns used to make predictions — Open, High, Low, Volume, Close |
| Target            | The value we want to predict — next day's closing price (`Next_Close`) |
| Train/Test Split  | Train on old data, test on newer data the model has never seen |
| Linear Regression | Finds a straight-line relationship between features and target |
| Random Forest     | Uses 100 decision trees and averages their predictions (more accurate) |
| shuffle=False     | Critical for time-series — we must not mix past and future data |

---

## Libraries Used

| Library | Purpose |
|---------|---------|
| yfinance | Download real stock market data from Yahoo Finance |
| pandas | Data manipulation and feature engineering |
| numpy | Numerical operations |
| matplotlib | Plot actual vs predicted price charts |
| scikit-learn | Train Linear Regression and Random Forest models |

---

## Steps Performed

1. Installed and imported all required libraries
2. Downloaded 2 years of Apple (AAPL) stock data using `yfinance`
3. Created the target column `Next_Close` by shifting the Close column up by 1 row
4. Dropped the last row (no next-day value available)
5. Selected features: Open, High, Low, Volume, Close
6. Split data — 80% training, 20% testing with `shuffle=False`
7. Trained **Linear Regression** model and evaluated performance
8. Trained **Random Forest Regressor** (100 trees) and evaluated performance
9. Plotted Actual vs Predicted prices for both models
10. Compared both models using MAE and R² Score
11. Wrote a summary of findings in a Markdown cell

---

## Feature Engineering

The `Next_Close` target column was created by shifting the `Close` column up by 1 row:

```
Row 0:  Open=170, Close=172  →  Next_Close=175   ← Row 1's close
Row 1:  Open=174, Close=175  →  Next_Close=169   ← Row 2's close
```

This means each row contains today's market data and tomorrow's closing price as the label.

---

## Models Trained

### Model A — Linear Regression
- Finds a straight-line formula connecting features to the target
- Simple, fast, and interpretable
- Formula: `Next_Close = w1*Open + w2*High + w3*Low + w4*Volume + w5*Close + bias`

### Model B — Random Forest Regressor
- Builds 100 decision trees independently
- Each tree makes a prediction; the average is the final answer
- Handles non-linear patterns better than Linear Regression
- Settings: `n_estimators=100`, `random_state=42`

---

## Evaluation Metrics

| Metric | Meaning |
|--------|---------|
| MAE (Mean Absolute Error) | Average dollar difference between predicted and actual price |
| R² Score | How much of the price variation the model explains (1.0 = perfect) |

---

## Results

| Model | MAE | R² Score |
|-------|-----|----------|
| Linear Regression | ~$0.20 | ~0.9998 |
| Random Forest | ~$1.50 | ~0.9980 |

> An R² score above 0.90 is considered excellent for stock price data.

---

## Visualizations Created

- **Closing Price Chart** — full 2-year AAPL price trend
- **Volume Bar Chart** — daily trading volume over 2 years
- **Linear Regression: Actual vs Predicted** — blue (actual) vs red dashed (predicted)
- **Random Forest: Actual vs Predicted** — blue (actual) vs green dashed (predicted)
- **Feature Importance Chart** — which features Random Forest relied on most

---

## Key Findings

- Both models achieved very high R² scores because today's closing price is a very strong predictor of tomorrow's price
- The most important feature in Random Forest is `Close` — the current day's closing price
- Linear Regression achieves a lower MAE here because the day-to-day price relationship is nearly linear
- Both prediction plots show the models closely tracking actual prices during the test period
- AAPL dropped significantly in 2022 and recovered strongly in 2023
- Volume spikes often coincide with major price movements

---

## How to Run

1. Install the required library if not already installed:
   ```
   pip install yfinance
   ```
2. Open `task2.ipynb` in VS Code or Google Colab
3. Run all cells top to bottom using **Shift + Enter**
4. Stock data downloads automatically — no manual file needed

> To predict a different stock, change `ticker = 'AAPL'` to `'TSLA'` (Tesla) or `'GOOGL'` (Google).

---

## File Structure

```
Task2_Stock_Prediction/
└── task2.ipynb
```