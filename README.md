# Statistical Analysis of Cholesterol and Blood Pressure Data

This project is a Jupyter Notebook (`lab.ipynb`) that conducts a detailed statistical analysis of data from the `age_bloodpressure_full.csv` file.

The analysis includes descriptive statistics, normality testing, correlation analysis, and the construction of a simple linear regression model.

## Dataset Description

The analysis uses the `age_bloodpressure_full.csv` dataset. The key variables for this study are:
* `cholesterol`
* `age_years`
* `blood_pressure`
* `weight`
* `activity_level`

## Structure of the Analysis

The notebook is divided into several key stages:

### 1. Descriptive Statistics
* **Variable:** `cholesterol` (selected as the random variable *X*).
* **Calculations:** Key summary statistics were computed:
    * Mean
    * Median
    * Mode
    * Minimum and Maximum
    * Variance and Standard Deviation
    * Skewness
    * Kurtosis

### 2. Visual Distribution Analysis
* Three plots were generated to visualize the distribution of the `cholesterol` variable:
    I.  **Histogram with KDE (Kernel Density Estimate):** Shows a unimodal (single-peaked) and bell-shaped distribution.
    II.  **Boxplot:** Demonstrates high symmetry (median almost in the center) and identifies one potential low-value outlier.
    III.  **Q-Q (Quantile-Quantile) Plot:** Shows that the data points lie very close to the diagonal line, indicating a strong similarity to a normal distribution.

* **Visual Conclusion:** The data *appears* to be approximately normally distributed.

### 3. Formal Normality Tests
* Two tests are used to statistically check the hypothesis of normality for the `cholesterol` distribution (at a significance level of $\alpha = 0.05$).
* **Null Hypothesis ($H_0$):** The data is normally distributed.

    I.  **Chi-Squared ($\chi^2$) Test:**
        * *p-value:* `0.0184`
        * *Conclusion:* p < 0.05, **reject $H_0$**.
    II.  **Shapiro-Wilk Test:**
        * *p-value:* `0.0308`
        * *Conclusion:* p < 0.05, **reject $H_0$**.

* **Final Conclusion (Tests):** Both formal tests show that the distribution is **statistically significantly different from normal**, despite the results of the visual analysis.

### 4. Correlation Analysis
* A correlation matrix heatmap was generated for all numerical variables in the dataset.
* **Strong Correlations:**
    * `age_years` and `cholesterol`
    * `age_years` and `blood_pressure`
* **Moderate Correlations:**
    * `blood_pressure` and `cholesterol`

### 5. Simple Linear Regression
* Based on the strong correlation, an OLS (Ordinary Least Squares) model was built to predict cholesterol levels.
* **Independent Variable (X):** `age_years`
* **Dependent Variable (Y):** `cholesterol`

---

## Key Findings

The analysis yielded the following results:

1.  **Regression Model:**
    A statistically significant positive linear relationship was established between age and cholesterol level. The final regression equation is:

$$
\text{cholesterol} = 151.53 + 0.6776 \times \text{age\_years}
$$

2.  **Model Significance:**
    * **R-squared:** `0.501`. The model explains **50.1%** of the variability in cholesterol levels, which is a moderately strong result.
    * **F-statistic p-value:** `1.12e-31`. The overall model is statistically significant (p < 0.05).
    * **T-test p-value (for age_years):** `0.000`. Age is a statistically significant predictor of cholesterol (p < 0.05).

3.  **Residual Check:**
    * A Shapiro-Wilk test on the model's residuals yielded a *p-value* = `0.8709`.
    * Since p > 0.05, we **fail to reject** the null hypothesis. This means the model's residuals **are normally distributed**, which validates the use of OLS regression.

## Requirements to Run

To reproduce this analysis, you need to install the following Python libraries:

## How to Use

1.  Ensure you have Python and Jupyter Notebook (or Jupyter Lab) installed.
2.  Install the necessary dependencies:
    ```bash
    pip install pandas matplotlib seaborn scipy statsmodels numpy
    ```
3.  Place the `age_bloodpressure_full.csv` file in the same directory as the notebook.
4.  Launch Jupyter Notebook and open `lab.ipynb`.
5.  Run the cells in order.
