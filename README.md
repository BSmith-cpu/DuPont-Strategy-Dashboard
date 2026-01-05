# DuPont-Strategy-Dashboard

**A financial intelligence tool that bridges the gap between raw accounting data and strategic decision-making.**

This project is an interactive analytics dashboard designed to look under the hood of S&P 100 companies. Instead of just tracking stock prices, it automates the **DuPont Analysis framework** to deconstruct Return on Equity (ROE). This allows analysts and investors to instantly see *why* a company is performing well—whether it's due to superior operations, efficient asset use, or simply taking on more debt.

## Why This Matters

Return on Equity (ROE) is often the "North Star" metric for investors, but a single number can be misleading. A high ROE could signal a highly efficient business, or it could mask a dangerous level of leverage.

This dashboard solves that ambiguity. By breaking ROE down into its three constituent drivers, the tool provides a clear, real-time health check on corporate strategy, separating sustainable growth from financial engineering.

## How It Works

### 1. Dynamic Data Sourcing

The application is built to be "always on." Rather than relying on static CSV files, it fetches fresh data every time it runs:

* **S&P 100 Scraping:** A custom scraper securely connects to Wikipedia to fetch the latest list of S&P 100 constituents, ensuring the ticker list is never out of date.
* **Live Financials:** The system integrates with the `yfinance` API to pull real-time Balance Sheets and Income Statements, standardizing the data for immediate analysis.

### 2. Intelligent Data Processing

Financial data is notoriously messy. Different sectors report "Equity" differently, and missing data points can crash standard scripts. This project uses **defensive data engineering** to handle these edge cases:

* It automatically normalizes accounting labels (like mapping "Total Stockholder Equity" vs. "Stockholders Equity").
* It includes robust error handling to manage zero-revenue periods or missing quarters without breaking the user experience.

### 3. Automated Insights

The dashboard doesn't just display charts; it interprets them. A built-in logic layer analyzes the components of the DuPont formula to classify the company's strategy. It highlights whether performance is margin-driven or leverage-driven and includes a **Risk Alert System** that flags companies when their financial leverage (Equity Multiplier) exceeds safe historical norms.

## The Analytical Framework

The dashboard relies on the **Three-Step DuPont Identity**, a fundamental formula that splits ROE into three actionable levers:

* **Profit Margin:** How much profit is kept from every dollar of sales? *(The Efficiency Lever)*
* **Asset Turnover:** How well are assets used to generate sales? *(The Activity Lever)*
* **Equity Multiplier:** How much of the company is funded by debt vs. equity? *(The Leverage Lever)*

## Tech Stack

* **Python:** The core logic engine.
* **Dash & Plotly:** Used to build the interactive, responsive user interface.
* **Pandas:** Handles the heavy lifting of financial data manipulation.
* **yfinance:** The gateway to live market and fundamental data.