# Portfolio Optimization with Genetic Algorithm (Static & Dynamic)

This project applies a **Genetic Algorithm (GA)** to optimize financial portfolios based on historical price data from S&P 500 companies. The study includes both **static** and **dynamic** portfolio strategies and compares them with traditional **Markowitz optimization**.

## 📌 Objective

To construct optimal investment portfolios that maximize return while minimizing risk, evaluated primarily using the **Sharpe Ratio**.

---

## 🧠 Key Methods

### 🧬 Genetic Algorithm

- **Encoding**: Chromosomes represent asset weights.
- **Fitness Function**: Sharpe Ratio.
- **Selection Method**: Tournament Selection.
- **Crossover & Mutation**: To evolve the population and avoid local optima.
- **Constraints**:
  - Asset weights sum to 1.
  - Individual weight limits (e.g., 0–30%).
  - Max number of assets per portfolio.

### 🔧 Bayesian Parameter Optimization

GA parameters (population size, mutation rate, etc.) are fine-tuned using Bayesian optimization to improve performance and reduce computation time.

---

## 🧪 Static vs. Dynamic Optimization

- **Static GA**: One-time optimization using training data; tested out-of-sample.
- **Dynamic GA**: Rolling window-based rebalancing every _n_ days.
  - Volatility estimated using GARCH(1,1).
  - Shrinkage applied to covariance matrix.
  - Walk-forward backtesting for realistic performance.

---

## 📊 Evaluation Metrics

- Annualized Return  
- Annualized Volatility  
- Sharpe Ratio  
- Maximum Drawdown  
- Forecast Accuracy: MAE, RMSE, MAPE, SMAPE, MASE

---

## 📈 Results Summary

The table below summarizes the **out-of-sample (test set)** performance of all models used in the project:

| Model                                  | Return   | Volatility | Sharpe Ratio | Max Drawdown |
|----------------------------------------|----------|------------|---------------|---------------|
| 📌 Static Genetic Algorithm            | 108.75%  | 28.14%     | 3.86          | -10.08%       |
| 📌 Dynamic Genetic Algorithm           | 62.28%   | 25.82%     | 2.25          | -15.20%       |
| Static Markowitz                       | 53.68%   | 17.74%     | 2.80          | -8.80%        |
| Dynamic Markowitz                      | 51.46%   | 17.72%     | 2.68          | -8.40%        |
| Dynamic Markowitz (Winsorized)        | 56.32%   | 16.29%     | 3.21          | -7.60%        |
| 1/N Equal-Weighted Portfolio           | 71.51%   | 19.07%     | 3.54          | -6.18%        |

> 🔍 GA-based models, especially the static version, achieved the highest returns with higher volatility and drawdown.  
> Markowitz and 1/N strategies offered more stable performance with lower risk.

---

## 🔗 Notes

- **Data Source**: Prices retrieved from Yahoo Finance via `yfinance`.

---

## 👩‍💻 Authors

- Genetic Algorithm: [Ezgi Cinkılıç](https://github.com/Ezgi-Cinkilic)
- Markowitz & Data Pipeline: [Zeynep Çindemir](https://github.com/zeynepcindemir)

---

## 📜 License

This project is shared for academic and personal learning purposes.

