# Portfolio-Optimization
# 📊 Portfolio Analysis — Sharpe Ratio Optimization

> Quantitative analysis and portfolio optimization on 5 major US tech stocks (AAPL, MSFT, GOOGL, AMZN, TSLA)

## Overview

This project applies quantitative finance techniques to analyze 3 years of historical stock data and identify the optimal portfolio allocation based on the Sharpe Ratio — the standard measure of risk-adjusted return in finance.

**Stocks analyzed**: Apple (AAPL), Microsoft (MSFT), Google (GOOGL), Amazon (AMZN), Tesla (TSLA)  
**Period**: 2021–2024  
**Data source**: Yahoo Finance API

---

## Pipeline

```
  📥 Data Download (yfinance)
        │
        ▼
  🧹 Cleaning — filter US market holidays
        │
        ▼
  📈 Feature Engineering
     • Normalized prices (base 100)
     • Daily & log returns
     • Cumulative returns
     • 30-day rolling volatility
     • Sharpe Ratio per stock
        │
        ▼
  📊 Visualization (4 charts)
        │
        ▼
  ⚡ Portfolio Optimization
     → Best asset selected by Sharpe Ratio
```

---

## Methodology

### Financial Metrics Computed

| Metric | Description |
| --- | --- |
| Daily Return | Percentage price change day over day |
| Log Return | Logarithmic return (additive property) |
| Cumulative Return | Total performance since start date |
| Annualized Volatility | 30-day rolling std × √252 |
| **Sharpe Ratio** | (Mean daily return − risk-free rate) / daily std |

> Risk-free rate assumption: 2% annualized (US Treasury proxy)

### Portfolio Optimization

The model computes the individual Sharpe Ratio for each of the 5 stocks and allocates 100% of the portfolio to the best-performing asset on a risk-adjusted basis.

---

## Results

### Individual Sharpe Ratios (2021–2024)

| Stock | Sharpe Ratio |
| --- | --- |
| **AAPL** | **0.0024** ✅ Selected |
| MSFT | 0.0016 |
| GOOGL | 0.0011 |
| AMZN | 0.0010 |
| TSLA | 0.0001 |

### Optimal Allocation

**→ AAPL at 100%** (highest risk-adjusted return over the period)

---

## Visualizations

The notebook generates 4 charts:

1. **Normalized Prices (Base 100)** — visual comparison of all 5 stocks from the same starting point
2. **Cumulative Returns** — how each stock evolved over 3 years
3. **30-day Rolling Volatility** — risk evolution over time
4. **Sharpe Ratio Bar Chart** — ranking of risk-adjusted performance per stock

---

## Project Structure

```
portfolio-optimization/
├── projet.ipynb        # Main notebook
├── requirements.txt
└── README.md
```

---

## Installation

```bash
git clone https://github.com/chrisayegh/portfolio-optimization.git
cd portfolio-optimization
pip install -r requirements.txt
```

### Dependencies

```
yfinance
pandas
numpy
matplotlib
scipy
holidays
```

---

## Usage

```bash
jupyter notebook projet.ipynb
```

Run all cells in order to download data, compute metrics, visualize results, and get the optimal allocation.

---

## Technologies

| Library | Purpose |
| --- | --- |
| `yfinance` | Stock data download |
| `pandas` | Data manipulation |
| `numpy` | Numerical computations |
| `matplotlib` | Visualization |
| `holidays` | US market calendar filtering |

---

## 👤 Author

**Christopher Sayegh**
- GitHub: [@chrisayegh](https://github.com/chrisayegh)
