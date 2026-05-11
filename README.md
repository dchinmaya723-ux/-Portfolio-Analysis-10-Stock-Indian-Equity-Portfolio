# 📈 Portfolio Analysis — 10-Stock Indian Equity Portfolio

> A rigorous quantitative portfolio analysis of a 10-stock Indian equity portfolio benchmarked against the **Nifty 50**, covering **56 monthly observations (Jan 2020 – Aug 2024)**. Built using CAPM valuation, OLS beta regression, Sharpe ratio analysis, and correlation-based diversification assessment.

**Prepared by:** Das Chinmaya Shakti Prasad &nbsp;|&nbsp; **Roll No.:** D-1095

---

## 🏆 Key Portfolio Metrics at a Glance

| Metric | Value |
|---|---|
| 📊 Portfolio Return (Annualized) | **24.54%** |
| 📉 Portfolio Risk (Annualized σ) | **23.49%** |
| ⚡ Sharpe Ratio | **0.7984** |
| 🏁 Benchmark Return (Nifty 50) | 16.29% |
| 🏦 Risk-Free Rate (10Y G-Sec) | 5.78% |
| 🎯 Alpha over Nifty 50 | **+8.25% p.a.** |
| ✅ Undervalued Stocks (vs CAPM) | 8 out of 10 |

> **Conclusion:** The portfolio delivers a Sharpe Ratio of 0.7984, outperforming the Nifty 50 by **8.25% per annum** on an equal-weighted basis, with 8 of 10 holdings undervalued relative to CAPM-implied expected returns.

---

## 🗂️ File Structure

```
Portfolio_Analysis.xlsx
├── Sheet 1: Cover                  # Project summary, KPIs, and stock composition table
├── Sheet 2: Price Data             # 56 monthly adjusted closing prices (Jan 2020 – Aug 2024)
├── Sheet 3: Returns & Statistics   # Monthly returns, mean, std dev, annualized statistics
├── Sheet 4: Correlation Matrix     # 10×10 pairwise correlation matrix with diversification flags
├── Sheet 5: Risk-Return & CAPM     # OLS Beta, Alpha, CAPM E(R), valuation & style classification
└── Sheet 6: Portfolio Summary      # Portfolio-level risk/return, Sharpe ratio, methodology
```

---

## 🧩 Portfolio Composition

| # | Stock | Sector | Weight | Ann. Return | Ann. Risk (σ) | Beta (β) | Valuation | Style |
|---|---|---|---|---|---|---|---|---|
| 1 | Bhagyanagar India Ltd. | Metals & Mining | 10% | 34.56% | 51.67% | 1.28 | UNDER VALUED | Aggressive |
| 2 | HCL Technologies Ltd. | Information Technology | 10% | 23.69% | 30.45% | 0.88 | UNDER VALUED | Defensive |
| 3 | Machino Plastics Ltd. | Auto Ancillaries | 10% | 31.22% | 44.23% | 1.31 | UNDER VALUED | Aggressive |
| 4 | Reliance Chemotex Inds. Ltd. | Textiles | 10% | 26.57% | 47.74% | 1.08 | UNDER VALUED | Aggressive |
| 5 | Ujjivan Small Finance Bank Ltd. | Banking & Finance | 10% | -5.24% | 49.53% | 1.42 | OVER VALUED | Aggressive |
| 6 | Biocon Ltd. | Pharmaceuticals | 10% | 4.34% | 30.28% | 0.65 | OVER VALUED | Defensive |
| 7 | Hindustan Aeronautics Ltd. | Defence & Aerospace | 10% | 38.46% | 51.85% | 1.05 | UNDER VALUED | Aggressive |
| 8 | Megastar Foods Ltd. | FMCG / Food Products | 10% | 31.62% | 61.82% | -0.19 | UNDER VALUED | Defensive |
| 9 | HDFC Bank Ltd. | Banking & Finance | 10% | 22.16% | 30.67% | 0.88 | UNDER VALUED | Defensive |
| 10 | Vimta Labs Ltd. | Healthcare / Labs | 10% | 37.98% | 55.35% | 1.29 | UNDER VALUED | Aggressive |

---

## 🔬 Methodology

### 1. Data & Returns
- **Source:** NSE/BSE adjusted monthly closing prices
- **Period:** January 2020 – August 2024 (56 monthly observations)
- **Return formula:** `Rt = (Pt − Pt-1) / Pt-1`
- **Annualization:** Mean × 12 &nbsp;|&nbsp; Std Dev × √12

### 2. Beta & Alpha Estimation (OLS Regression)
- Beta estimated via OLS: `βi = Cov(Ri, Rm) / Var(Rm)`
- Alpha: `αi = E(Ri) − Rf − βi × [E(Rm) − Rf]`
- **Benchmark:** Nifty 50 monthly returns
- Classification: Aggressive if β > 1 &nbsp;|&nbsp; Defensive if β < 1

### 3. CAPM Valuation
- `E(Ri) = Rf + βi × [E(Rm) − Rf]`
- **Risk-Free Rate (Rf):** 5.78% (10-Year Government Securities yield)
- **Market Return (Rm):** Nifty 50 annualized return over study period
- **Valuation Rule:** Under Valued if Actual Return > CAPM E(R); else Over Valued

### 4. Portfolio Risk & Return
- **Weights:** Equal-weighted (10% per stock)
- **Portfolio Variance:** Full covariance matrix approach — `σ²p = Σ Σ wi × wj × Cov(Ri, Rj)`
- **Sharpe Ratio:** `SR = [E(Rp) − Rf] / σp`
- **Alpha over Benchmark:** Portfolio return − Nifty 50 return

### 5. Correlation & Diversification Analysis
- Full 10×10 pairwise correlation matrix computed
- High positive correlation (≥ 0.50) flagged as low diversification benefit
- Low/negative correlation (≤ 0.00) flagged as good diversification
- Notable high pair: **HCL Tech ↔ Machino Plastics (r = 0.614)**

---

## 📊 Notable Findings

**Risk-Return Highlights:**
- **HAL** delivered the highest annualized return at 38.46%, followed by Vimta Labs (37.98%) and Bhagyanagar India (34.56%)
- **Ujjivan SFB** was the only stock with a negative return (-5.24%)
- **Megastar Foods** had the highest individual risk (σ = 61.82%) but a negative beta (-0.19), providing a natural market hedge

**Diversification:**
- Most stock pairs show low-to-moderate correlations, confirming good diversification benefits across sectors
- Only one pair breaches the high-correlation threshold (≥ 0.50): HCL Tech & Machino Plastics (0.614)

**CAPM Valuation:**
- 8 of 10 stocks are **undervalued** relative to their CAPM-implied expected return
- Only Ujjivan SFB and Biocon are flagged as overvalued based on CAPM

---

## ⚙️ Key Assumptions

| Parameter | Detail |
|---|---|
| Portfolio Weights | Equal-weighted — 10% per stock |
| Rebalancing Frequency | Monthly (assumed for calculation purposes) |
| Benchmark | Nifty 50 (monthly adjusted closing prices) |
| Risk-Free Rate | 5.78% p.a. — 10-Year Government Securities yield |
| Beta Estimation | OLS regression over 55 monthly return observations |
| Annualization | Mean × 12 \| Std Dev × √12 |
| Valuation Criterion | Under Valued if Actual Return > CAPM E(R) |

---

## 🛠️ Tools Used

- **Microsoft Excel** — Data processing, return computation, OLS regression, covariance matrix, CAPM
- **Data Sources:** NSE / BSE historical price data, RBI (10-year G-Sec yield as risk-free rate)

---

## 📌 Disclaimer

> This project is for **academic and educational purposes only**. It does not constitute investment advice or a recommendation to buy or sell any security. All assumptions and results are the author's own interpretation based on historical data. Past performance is not indicative of future results.

---

*Built with 📐 statistical rigour and ☕ patient spreadsheet work.*
