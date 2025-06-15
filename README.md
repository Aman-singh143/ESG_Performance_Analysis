# ESG Investment Performance Analysis

Unveiling the financial impact of sustainability through rigorous data science.

---

## Project Overview

This project analyzes whether companies with strong Environmental, Social, and Governance (ESG) profiles provide superior financial returns or reduced risk. We focus on leading S\&P 500 companies—Apple (AAPL), Tesla (TSLA), and Microsoft (MSFT)—and compare their performance with the broader S\&P 500 index (^GSPC).

Through statistical analysis, regression modeling, and Monte Carlo simulations, we aim to answer a crucial question in sustainable finance:

> Can ESG-aligned investing outperform traditional investment strategies?

---

## Motivation

With the rise of ethical investing, ESG has become a key consideration for investors. However, the financial trade-offs of prioritizing ESG are still debated.

**This project seeks to:**

* Test whether ESG scores correlate with higher stock returns.
* Measure financial risk using Monte Carlo simulations and Value at Risk (VaR).
* Deliver actionable insights for integrating ESG in portfolios.

---

## Objectives

* **Analyze ESG Impact** on returns vs. the S\&P 500.
* **Simulate Risk** using historical data for 1000+ outcomes.
* **Build a Regression Model** linking ESG and financial performance.
* **Visualize Trends** clearly with statistical plots.
* **Inform Investing** with practical ESG strategies.

---

## Data Sources

### ESG Risk Ratings

* **File:** `SP 500 ESG Risk Ratings.csv`
* **Fields:** ESG total score, Environment, Social, Governance scores, Controversy, Percentile

**Example:**

| Symbol | Company | ESG Score | Env  | Soc  | Gov | Controversy |
| ------ | ------- | --------- | ---- | ---- | --- | ----------- |
| AAPL   | Apple   | 17.2      | 0.6  | 7.8  | 8.8 | 2.0         |
| TSLA   | Tesla   | 28.4      | 10.2 | 10.5 | 7.7 | 3.0         |

### Stock Prices

* **Source:** Yahoo Finance via `yfinance`
* **Tickers:** AAPL, TSLA, MSFT, ^GSPC
* **Period:** Jan 2015 – May 2024

**Example:**

| Date       | Ticker | Close | Volume      |
| ---------- | ------ | ----- | ----------- |
| 2015-01-02 | AAPL   | 24.29 | 212,818,400 |

---

## Methodology

### 1. Data Collection

* Load ESG data from CSV
* Fetch stock data using `yfinance`

### 2. Data Cleaning

* Remove null/irrelevant columns
* Fill missing controversy values
* Convert ESG percentiles for analysis

### 3. Integration

* Merge ESG and stock data by symbol

### 4. Performance Analysis

* Calculate daily returns
* Correlate ESG scores with returns
* Compare high vs. low ESG portfolios

### 5. Regression Modeling

* **Model:** OLS Regression
* **Target:** Stock returns
* **Features:** ESG score, individual components
* **Output:** R², coefficients, p-values

### 6. Risk Simulation (Monte Carlo)

* 1000 simulations, 1-year horizon, \$100K investment
* VaR (Value at Risk) @ 95% confidence level

### 7. Visualization

* Monte Carlo paths
* ESG-return correlations
* Regression summary

---

## Key Results

* **Regression R²:** \~0.62 - ESG explains 62% variance in returns
* **p-value:** < 0.05 - Statistically significant
* **VaR (95%):** \~\$30,492 — shows potential downside risk

---

## Technologies Used

* Python 3.8+
* Pandas & NumPy — Data handling
* Seaborn & Matplotlib — Visualization
* yFinance — Stock data
* Statsmodels — Regression modeling
* Jupyter Notebook — Interactive development

---

## Project Structure

```
ESG_Performance_Analysis/
├── ESG_Performance_Analysis.ipynb     # Main notebook
├── SP 500 ESG Risk Ratings.csv        # ESG data
├── requirements.txt                   # Python dependencies
├── README.md                          # Project documentation
```

---

## How to Use

### 1. Setup

```bash
git clone https://github.com/Aman-singh143/ESG_Performance_Analysis.git
cd ESG_Performance_Analysis
python -m venv env
source env/bin/activate  # Or env\Scripts\activate on Windows
pip install -r requirements.txt
```

### 2. Run Notebook

```bash
jupyter notebook ESG_Performance_Analysis.ipynb
```

### 3. Follow Steps in Notebook

* Load & clean data
* Visualize and analyze trends
* Run regression & Monte Carlo
* Interpret R², p-values, VaR

---

## Sample Outputs

### Regression Summary (Statsmodels)

```
R-squared: 0.620
const: 0.0123 (p < 0.001)
ESG Score: 0.0015 (p < 0.001)
```

### Monte Carlo Simulation

Simulates 1000 portfolio paths:

---

## Roadmap

* Add global ESG datasets
* Integrate real-time ESG APIs (e.g., Refinitiv, MSCI)
* Apply machine learning for return prediction
* Deploy via Streamlit for interactive analysis

---

## FAQ

**Q:** Why use Apple, Tesla, Microsoft?

> Diverse ESG profiles, high volatility, large-cap relevance

**Q:** What does VaR mean?

> Value at Risk shows worst-case loss at confidence level (e.g., 95%)

**Q:** Can I use my own ESG file?

> Yes! Just match the format and update the file path in the notebook

---

## License

MIT License — free for modification and redistribution with attribution

---

## Contact

**Aman Singh**
[GitHub](https://github.com/Aman-singh143)

---

> Note: This project is academic and research-oriented.
