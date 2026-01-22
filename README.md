# S&P 500 Sector Weights EDA  
Exploratory Data Analysis using Python and Pandas

Presentation Link: https://drive.google.com/file/d/1k7a6D8SbG4QEKWcz-YSWVaZhy1eIyNot/view?usp=drive_link

Google Colab link: https://drive.google.com/file/d/172crY77TplrNl26SdIuJCvlnDZsHTXzv/view?usp=sharing

---

## Project Overview
This project performs exploratory data analysis on **S&P 500 sector composition** (using IVV as a proxy) to understand how sector weights evolve over time and what those shifts imply for diversification, market regimes, and future sector outlooks.

The analysis follows four parts:
1. Descriptive statistics and pie charts  
2. Correlation matrix and heat maps  
3. Histograms and conditional distributions  
4. Storytelling and future predictions  

---

## Project Objectives
- Download and clean sector data from a web source
- Compute descriptive statistics on sector weights
- Visualize sector distribution using pie charts and time-series charts
- Build a 20-year sector weight dataset from a string and convert it to numeric form
- Analyze sector correlations and explain economic intuition
- Use conditional distributions to test how one sector’s weight relates to another
- Make forward-looking predictions and career or investment recommendations using sector cycles

---

## Data Sources
### 1) iShares IVV Holdings (S&P 500 Proxy)
The project downloads IVV holdings from iShares and uses the **Sector** and **Market Value** fields to estimate sector composition.

- IVV “Detailed Holdings and Analytics” CSV endpoint (used in notebook):
  https://www.ishares.com/us/products/239726/ishares-core-sp-500-etf/1467271812596.ajax?fileType=csv&fileName=IVV_holdings&dataType=fund

### 2) Sector Weights Time Series (2002–2021)
A sector-weight dataset is provided as a multiline string (percentage format) and parsed into a numeric pandas DataFrame.

### 3) Additional Constructed Data Points
- A synthetic **2000** datapoint is added by setting Information Technology to 32% and scaling other sectors proportionally to 2002.
- A **2024** datapoint is added using updated sector weights from IVV (entered manually based on the downloaded data).

---

## Tools & Libraries
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  

---

## Data Preparation & Cleaning
Key cleaning steps include:
- Skipping header rows in the IVV holdings CSV
- Converting Market Value, Weight (%), Notional Value, and Price fields to numeric
- Removing currency symbols and commas in numeric fields
- Grouping by Sector and aggregating Market Value to compute weighted sector shares
- Parsing percent strings (example “15%”) into numeric decimals for time-series analysis

---

## Visualizations Included

### Descriptive Statistics and Pie Charts
- Descriptive statistics of holdings data
- Pie chart of sector distribution by stock count
- Pie chart of sector distribution weighted by market value (S&P 500 proxy)

### Correlation Matrix and Heatmap (2002–2021)
- Sector weight correlation matrix
- Heatmap of correlations
- Discussion of high and low correlation sector pairs with economic explanations

### Histograms and Conditional Distributions
- Histogram + KDE for Consumer Discretionary sector weights
- Conditional KDE of Consumer Discretionary weights:
  - High Energy years vs Low Energy years
- Interpretation of shifts in conditional distributions

### Storytelling and Predictions (2000–2024)
- Bar chart comparing sector weights in 2000 vs 2024
- Line chart of sector weights over time (2000–2024)
- Stability vs volatility scatter plot (average weight vs standard deviation)
- Crisis-focused visualization around:
  - Dotcom bubble (2000–2002)
  - Global financial crisis (2007–2009)
- Forward-looking sector predictions and career or investment recommendations

---

## Key Findings Summary
- Sector weights are not static. Technology and Communication-related sectors show long-term expansion and higher volatility.
- Defensive sectors such as Utilities, Consumer Staples, and Materials tend to be more stable over time.
- Correlation analysis reveals natural diversification pairs (example Health Care vs Communication Services shows negative correlation).
- Conditioning Consumer Discretionary weights on Energy weights provides evidence that sector composition shifts across macro regimes.
- Crisis periods show sector rotation effects, reinforcing the value of tracking sector weights over time for both investing and career planning.

---
