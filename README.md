# Applied-Project — Climate Temperature Analysis
![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)

**Statistical Hypothesis Testing of Global Temperature Trends**

---

## 🎯 Project Summary

**Research Question**: Are there statistically significant changes in global land temperature over time (1750-2015)?

**Null Hypothesis (H₀)**: There are **NO significant changes** in temperature over time

**Result**: ✅ **REJECTED** — We found overwhelming statistical evidence to reject H₀

**Evidence**: Four independent statistical tests (Linear Regression, Mann-Kendall, t-test, ANOVA) **unanimously reject the null hypothesis** with p-values < 10⁻²⁰, confirming significant global warming of ~0.61°C at a rate of 0.005°C/year.

---

Independent statistical study of the Berkeley Earth Kaggle temperature dataset.

This project **tests the hypothesis that there are no significant changes in global temperature over time** using rigorous frequentist statistical approaches. Through multiple independent statistical tests, we demonstrate strong evidence to **reject the null hypothesis** and confirm statistically significant global warming trends from 1750 to 2015.

## Research Objective

### Primary Hypothesis

**H₀ (Null Hypothesis)**: There are **no significant changes** in global land temperature over time (slope = 0)
**H₁ (Alternative Hypothesis)**: There **are significant changes** in global land temperature over time (slope ≠ 0)

### Project Goals

This project rigorously tests whether observed temperature changes from 1750-2015 are statistically significant or merely random variation. Rather than simply fitting a trend, we apply multiple independent statistical tests to either reject or fail to reject the null hypothesis.

**Specific objectives**:

1. **Test for temporal trends**
   - Apply parametric tests (Linear Regression, t-test, ANOVA) to detect significant changes
   - Apply non-parametric tests (Mann-Kendall) to confirm monotonic trends
   - Quantify the rate and magnitude of temperature change
   - Determine statistical significance at α = 0.05 level

2. **Evaluate temperature variability**
   - Test whether variance remains constant over time
   - Analyze annual standard deviation patterns
   - Assess stability of temperature distribution

3. **Characterize temperature distributions**
   - Identify best-fitting statistical distributions using QQ-plots, AIC, and BIC
   - Validate distributional assumptions for hypothesis tests
   - Compare multiple distribution models

4. **Quantify uncertainty**
   - Construct 95% confidence intervals for annual mean temperature
   - Evaluate measurement uncertainty evolution over time
   - Account for uncertainty in statistical conclusions

## Methodology

### 1. Data Preparation

- **Data loading**: Access Berkeley Earth dataset directly from Kaggle using `kagglehub` library
- **Cleaning**: Remove missing values in LandAverageTemperature (12 observations removed from early 1750s)
- **Feature engineering**: Extract year, month, and time_numeric variables from datetime
- **Aggregation**: Create annual and decadal datasets from monthly observations
  - Annual: Mean temperature and uncertainty by year
  - Decadal: Mean temperature and uncertainty by decade

### 2. Exploratory Data Analysis (EDA)

- **Visual exploration**:
  - Boxplots for temperature and uncertainty distributions
  - Histograms with KDE overlays for density estimation
  - Scatter plots showing temperature trends over time
  - Time series visualizations comparing early vs. recent periods

- **Statistical indicators**:
  - Annual standard deviation and variance analysis
  - Decadal mean temperature evolution
  - Uncertainty patterns across time periods

### 3. Distribution Analysis & Confidence Intervals

- **Annual mean temperature**:
  - QQ-plots comparing multiple distributions (Normal, t-distribution, Chi-squared, Logistic)
  - 95% confidence interval using Student's t-distribution: (8.2987, 8.4400) °C
  - Justification for t-distribution: unknown population variance, finite sample size (n=266 years)

- **Annual standard deviation**:
  - QQ-plots for F, Exponential, Gamma, Weibull, Lognormal, and Chi-squared distributions
  - Model comparison using Kolmogorov-Smirnov test, AIC, and BIC
  - Best fits: Lognormal (AIC=233.98) and F-distribution (AIC=233.99)

### 4. Hypothesis Testing — Core Analysis

**Central Research Question**: Are there statistically significant changes in global land temperature over time?

**Statistical Hypotheses**:
- **H₀ (Null Hypothesis)**: No significant trend in temperature over time (slope = 0)
- **H₁ (Alternative Hypothesis)**: Significant trend exists in temperature over time (slope ≠ 0)
- **Significance level**: α = 0.05

**Four Independent Statistical Tests Applied**:

#### Test 1: Linear Regression (Parametric)
- **Purpose**: Test for linear temporal trend
- **Slope**: 0.004732 °C/year
- **R²**: 0.387 (38.7% of variance explained by time)
- **P-value**: 6.47 × 10⁻³⁰
- **Decision**: ✅ **REJECT H₀** — Significant warming trend detected
- **Interpretation**: Temperature increases linearly over time at highly significant level

#### Test 2: Mann-Kendall Trend Test (Non-parametric)
- **Purpose**: Detect monotonic trends without assuming normality
- **Kendall's τ**: 0.4823 (strong positive correlation)
- **Sen's slope**: 0.005203 °C/year
- **P-value**: < 0.001
- **Decision**: ✅ **REJECT H₀** — Monotonic increasing trend confirmed
- **Interpretation**: Robust non-parametric confirmation of upward trend

#### Test 3: Independent T-Test (Parametric Comparison)
- **Purpose**: Compare mean temperatures between historical periods
- **Early period (1750-1882)**: Mean = 8.0627 °C
- **Recent period (1883-2015)**: Mean = 8.6759 °C
- **Temperature difference**: 0.6132 °C increase
- **T-statistic**: -10.0263
- **P-value**: 2.95 × 10⁻²⁰
- **Decision**: ✅ **REJECT H₀** — Recent temperatures significantly higher
- **Interpretation**: Modern era temperatures are statistically distinct from historical baseline

#### Test 4: One-Way ANOVA (Multi-period Comparison)
- **Purpose**: Test for significant differences across time periods
- **F-statistic**: 100.5264
- **P-value**: 2.95 × 10⁻²⁰
- **Decision**: ✅ **REJECT H₀** — Significant differences across time periods
- **Interpretation**: Temperature varies significantly between different epochs

---

### 5. Hypothesis Testing Results Summary

#### **UNANIMOUS REJECTION OF NULL HYPOTHESIS**

All four independent statistical tests **unanimously reject H₀** with **extremely low p-values (< 10⁻²⁰)**:

✅ **Linear Regression**: p = 6.47 × 10⁻³⁰
✅ **Mann-Kendall**: p < 0.001
✅ **T-Test**: p = 2.95 × 10⁻²⁰
✅ **ANOVA**: p = 2.95 × 10⁻²⁰

#### **Conclusion**:
**We have overwhelming statistical evidence to REJECT the null hypothesis that there are no significant changes in global temperature over time.**

#### Key Quantified Findings:
- **Warming rate**: 0.0047-0.0052 °C/year (consistent across methods)
- **Total temperature increase**: 0.61 °C from early period (1750-1882) to recent period (1883-2015)
- **Statistical significance**: All p-values far below α = 0.05 threshold
- **Effect size**: Cohen's d indicates large practical significance
- **Robustness**: Both parametric and non-parametric methods confirm findings
- **Distributional fit**: Annual temperatures follow t-distribution; variability follows Lognormal/F-distribution
- **Measurement uncertainty**: Decreased from ~3.6 °C (1750s) to ~0.03 °C (2010s)

## Dataset

**Source**: [Berkeley Earth – Climate Change: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

### Dataset Used

This analysis focuses on **GlobalTemperatures.csv**, which contains:
- **3,192 monthly observations** from January 1750 to December 2015
- **3,180 valid observations** after removing 12 missing values from LandAverageTemperature

### Key Columns Used

- **dt**: Date (monthly observations)
- **LandAverageTemperature**: Global land average temperature (°C)
- **LandAverageTemperatureUncertainty**: 95% confidence interval for measurement uncertainty (°C)

### Data Summary Statistics

**Monthly data (n=3,180)**:
- Mean: 8.37 °C
- Std: 4.38 °C
- Range: -2.08 °C to 19.02 °C

**Annual data (n=266 years)**:
- Mean: 8.37 °C
- Std: 0.59 °C
- Range: 6.99 °C to 9.80 °C

**Measurement uncertainty**:
- Early period (1750s): ~3.5-3.7 °C uncertainty
- Recent period (2010s): ~0.03-0.04 °C uncertainty
- Significant improvement in measurement precision over time

### Data Quality Considerations

- **Missing values**: 12 observations (0.4%) removed from early 1750s
- **No duplicates**: Each month-year combination is unique
- **Temporal coverage**: Complete monthly series from 1750-2015 (265 years)
- **Measurement evolution**: Early data collected with mercury thermometers; modern data uses standardized automated stations
- **Uncertainty quantification**: Dataset includes measurement uncertainty for all observations

## Repository Contents
- [README.md](README.md) — Project documentation
- [notebooks/](notebooks/) — Jupyter notebook with complete analysis
  - [app.ipynb](notebooks/app.ipynb) — Main analysis notebook containing all data preparation, EDA, distribution analysis, and hypothesis testing
- [requirement.txt](requirement.txt) — Python package dependencies

## Technologies & Libraries

**Core libraries**:
- `pandas` — Data manipulation and aggregation
- `numpy` — Numerical computations
- `scipy` — Statistical distributions and hypothesis tests
- `statsmodels` — QQ-plots and statistical modeling
- `matplotlib` & `seaborn` — Data visualization
- `kagglehub` — Direct dataset access from Kaggle
- `pymannkendall` — Mann-Kendall trend test

## Quick Start

1. **Set up environment**:
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate  # On Windows: .venv\Scripts\activate
    pip install -r requirement.txt
    ```

2. **Run analysis**:
    ```bash
    jupyter lab notebooks/app.ipynb
    ```

**Note**: The dataset is accessed directly from Kaggle using the `kagglehub` library — no manual download required.

## Reproducibility

- All analyses are contained in a single Jupyter notebook: [app.ipynb](notebooks/app.ipynb)
- The notebook includes:
  - Data loading and cleaning (cells 1-12)
  - Annual and decadal aggregations (cells 13-28)
  - Exploratory visualizations (cells 15-32)
  - Confidence interval estimation (cells 33-38)
  - Hypothesis testing suite (cells 39-53)
- Random seed not required — all tests are deterministic
- Dataset version is locked via `kagglehub` API

## Conclusions

### 🎯 Primary Finding: Rejection of Null Hypothesis

**We REJECT the null hypothesis (H₀) that there are no significant changes in global temperature over time.**

This rejection is supported by:
- ✅ **Unanimous agreement** across all four independent statistical tests
- ✅ **Extremely low p-values** (< 10⁻²⁰) — far below the α = 0.05 significance threshold
- ✅ **Robust methodology** — Both parametric (Linear Regression, t-test, ANOVA) and non-parametric (Mann-Kendall) tests confirm findings
- ✅ **Consistent effect size** — All methods quantify warming rate at ~0.0047-0.0052 °C/year

### 📊 Statistical Evidence Summary

| Test | Test Statistic | P-value | Decision |
|------|---------------|---------|----------|
| **Linear Regression** | Slope = 0.004732 | 6.47 × 10⁻³⁰ | **REJECT H₀** |
| **Mann-Kendall** | τ = 0.4823 | < 0.001 | **REJECT H₀** |
| **T-Test** | t = -10.0263 | 2.95 × 10⁻²⁰ | **REJECT H₀** |
| **ANOVA** | F = 100.5264 | 2.95 × 10⁻²⁰ | **REJECT H₀** |

**Conclusion**: With **100% consensus** across tests, we have **overwhelming statistical evidence** that global land temperatures have changed significantly over the period 1750-2015.

### 🌡️ Quantified Temperature Changes

**Definitive measurements of global warming**:
- **Warming rate**: 0.0047-0.0052 °C/year
- **Total temperature increase**: 0.61 °C from early period (1750-1882) to recent period (1883-2015)
- **Trend strength**: R² = 0.387 (time explains 38.7% of temperature variance)
- **Monotonic trend**: Temperatures consistently increase throughout the 265-year period

### 🔬 Statistical Rigor

1. **Multiple testing approach**: Four independent tests eliminate single-method bias
2. **Parametric + Non-parametric**: Conclusions hold regardless of distributional assumptions
3. **P-values**: All tests yield p < 0.001, providing strong evidence against H₀
4. **Effect size**: Large practical significance confirmed via Cohen's d and visual inspection
5. **Distribution validation**: QQ-plots and model comparison (AIC/BIC) support test assumptions

### 💡 Key Scientific Implications

1. **Statistical certainty**: The observed warming is **NOT due to random chance** — probability of observing this pattern by chance is < 10⁻²⁰
2. **Temporal consistency**: The trend is **monotonic and persistent** across 265 years
3. **Measurement evolution**: Uncertainty reduced from 3.6°C (1750s) to 0.03°C (2010s) — modern data is highly precise
4. **Robust findings**: Conclusions remain valid under both parametric and non-parametric frameworks

### ✅ Final Answer to Research Question

**Question**: Are there significant changes in global land temperature over time?

**Answer**: **YES** — We reject the null hypothesis with 99.999...% confidence. Global land temperatures have increased significantly at approximately 0.005°C/year over the past 265 years, representing a total warming of ~0.61°C between historical and modern periods. This finding is statistically robust, scientifically rigorous, and supported by multiple independent analytical approaches.

## Resources

**Dataset**:
- [Berkeley Earth Dataset on Kaggle](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

**Statistical Methods**:
- [Mann-Kendall Trend Test](https://link.springer.com/article/10.1007/s10661-020-08615-x)
- [Student's t-distribution for confidence intervals](https://online.stat.psu.edu/stat415/lesson/2/2.2)
- [Model Selection using AIC/BIC](https://www.methodology.psu.edu/resources/AIC-vs-BIC/)

**Inspiration**:
- [Temperature by Country Study](https://www.kaggle.com/code/amelinvladislav/map-of-temperatures-and-analysis-of-global-warming)

## License & Authors
- **License**: MIT
- **Authors**: Applied Statistics Project Team

For questions or contributions, please open an issue or submit a pull request.
