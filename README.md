# Statistical Analysis of Cholesterol and Blood Pressure Data

This project presents a detailed statistical analysis of cholesterol and blood pressure data using a Jupyter Notebook (`lab.ipynb`). The analysis is based on the `age_bloodpressure_full.csv` dataset and includes descriptive statistics, normality testing, correlation analysis, and the development of a simple linear regression model.

---

## Dataset Description

The analysis focuses on the following key variables from the `age_bloodpressure_full.csv` dataset:
- cholesterol
- age_years
- blood_pressure
- weight
- activity_level

---

## Structure of the Analysis

The notebook is divided into the following key stages:

### 1. Descriptive Statistics
Key summary statistics were computed for `cholesterol` (selected as the random variable X), including:
- Mean, Median, Mode
- Minimum, Maximum
- Variance, Standard Deviation
- Skewness, Kurtosis

---

### 2. Visual Distribution Analysis
To understand the distribution of `cholesterol`, the following plots were generated:
1. Histogram with KDE (Kernel Density Estimate): A unimodal, bell-shaped distribution.
2. Boxplot: Highlights high symmetry with one potential low-value outlier.
3. Q-Q (Quantile-Quantile) Plot: Indicates strong similarity to a normal distribution (data points lie close to the diagonal line).

Conclusion: The visual analysis suggests the data is approximately normally distributed.

---

### 3. Formal Normality Tests
To statistically assess normality, two tests were conducted on the `cholesterol` variable, with a 5% significance level (α = 0.05):
- Null Hypothesis (H₀): The data is normally distributed.

Test Results:
1. Chi-Squared (χ²) Test:
   - p-value: 0.0184
   - Conclusion: p < 0.05 → Reject H₀
2. Shapiro-Wilk Test:
   - p-value: 0.0308
   - Conclusion: p < 0.05 → Reject H₀

Final Verdict: Statistical tests indicate the `cholesterol` distribution is significantly different from normal, despite visual indications.

---

### 4. Correlation Analysis
A correlation matrix heatmap was generated for all numerical variables, revealing:
- Strong Correlations:
  - age_years ↔ cholesterol
  - age_years ↔ blood_pressure
- Moderate Correlation:
  - blood_pressure ↔ cholesterol

---

### 5. Simple Linear Regression
Based on the strong correlation, an OLS (Ordinary Least Squares) model was constructed to predict `cholesterol` levels using the independent variable age_years.

Regression Equation:
cholesterol = 151.53 + 0.6776 × age_years

---

## Key Findings

1. Model Summary:
   - R-squared: 0.501 → The model explains 50.1% of the variability in cholesterol levels.
   - F-statistic p-value: 1.12e-31 → Model is statistically significant (p < 0.05).
   - T-test p-value (age_years): 0.000 → Age is a statistically significant predictor of cholesterol levels.

2. Residual Check:
   - A Shapiro-Wilk test of model residuals yielded a p-value = 0.8709.
   - Conclusion: Since p > 0.05, the residuals are normally distributed, validating the application of OLS regression.

---

## Steps to Reproduce

Follow these steps to reproduce the analysis:

1. Software Requirements:
   - Install Python (3.x) and Jupyter Notebook (or Jupyter Lab).

2. Install Dependencies:
   ```bash
   pip install pandas matplotlib seaborn scipy statsmodels numpy
   ```

3. Prepare the Dataset:
   Place the `age_bloodpressure_full.csv` file in the same directory as the notebook.

4. Run the Analysis:
   - Launch Jupyter Notebook and open `lab.ipynb`.
   - Execute all cells sequentially.

---

Feel free to reach out for further assistance with running the notebook.
