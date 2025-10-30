### 1. Set up project structure and environment

# Project Todo List

## 1. Set up project structure and environment

### 1.1 Directory Structure
- [x] Create project directories:
  - [x] data/raw/ for Kaggle dataset
  - [x] data/processed/ for cleaned data
  - [x] figures/ for plots with labels and units
  - [x] tables/ for summary statistics
  - [x] notebooks for analysis code

### 1.2 Python Environment
- [ ] Set up development environment:
  - [ ] Create virtual environment
  - [ ] Install required packages:
    - [ ] Data manipulation: pandas, numpy
    - [ ] Visualization: matplotlib, seaborn, plotly
    - [ ] Statistics: scipy, statsmodels
    - [ ] Machine learning: sklearn

### 1.3 Data Acquisition
- [ ] Download and organize Kaggle dataset

## 2. Dataset Familiarization and EDA

### 2.1 Dataset Structure Examination
- [ ] Load data
- [ ] Overview of the dataset structure (for each file)
  - [ ] Identify table dimensions
  - [ ] Analyze key columns (average temperatures, uncertainties, dates, locations)
  - [ ] Time coverage (start, end, granularity)
  - [ ] Unique identifiers (country, cities, etc.)
- [ ] Document data structure
- [ ] Choose most appropriate dataset for our analysis

### 2.2 Data Quality Analysis
- [ ] Discuss any notable data quality considerations
  - [ ] Missing values (The collection of minimum and maximum temperatures began in 1850)
  - [ ] Identify outliers using boxplots
  - [ ] Investigate anomalous periods
  - [ ] High variation in earlier decades (high variation for the earlier decades, impact of seasons)
- [ ] Document conclusions

### 2.3 Descriptive Statistics and Visualization
- [ ] Create and analyze distribution plots  (histograms, boxplots, time series plots, worldmap, bar charts, etc.):
  - [ ] Global temperature distribution over all the period (1750-2015)
  - [ ] Global temperature distribution yearly
  - [ ] Temperature distribution by location (country or city)
  - [ ] Geographic distribution yearly
  - [ ] Uncertainty distributions (yearly and by location)
  - [ ] Seasonal decomposition : Global temperature by seasons over all the period(1750-2015)
- [ ] For each distribution, calculate distribution statistics:
  - [ ] Mean, median, standard deviation
  - [ ] Min, max, quantiles
  - [ ] Skewness, kurtosis
- [ ] Characterise the measurement effort across time and space
  - [ ] Create location/time heatmap
  - [ ] Identify data patterns : Are there periods or regions with more/less data? How might these patterns affect the reliability of your results? (e.g., trends could be biased if early data is sparse or uncertain).
  - [ ] Assess potential biases and gaps : Are there gaps or biases in the data collection? (e.g., some countries underrepresented, or early years with sparse data).
  - [ ] Identify regional behavior clusters: Observe clusters of regions with similar behaviour.


## 3. Multi-Year Indicator Analysis
Which statistics indicators can characterise the trends or the temperature variability across many years?

- [ ] Select 3 sampling indicators that are informative. Justify each choice.
  - [ ] Spatial Coverage: Portion of country with measures (nb_country_with_data / total_nb_country)*100 by period. This indicator evaluates the geographical representativeness of data and allows to identify potential bias in the mondial coverage.
  - [ ] Decadal mean temperature: mean by decade (useful for smoothing variability).
  - [ ] Annual standard deviation: evaluate the evolution of the climate variability (standard deviation of the temperature distribution in one year).
  - [ ] Annual coefficient of variation (CV = std/mean): express the relative variability to the mean. It indicates how much the temperature fluctuates in proportion to its average value. For example, if CV = 10%, then the annual average temperature is 10°C and the standard deviation is 1°C.
  - [ ] Autocorrelation (lag-1): measure whether the temperatures of one year depend on those of the previous year. A high autocorrelation indicates a climate memory effect, 
  - [ ] Skewness across the year: assesses the evolution of the asymmetry of the distribution. If there is symmetry around the mean, then the seasons are balanced. If the skewness is > 0, then there is a right tail and the lower temperatures are more frequent. If the skewness is < 0, then there is a left tail and the high temperatures are more frequent.
- [ ] For every indicator, compute annual estimates and provide confidence intervals that reflect estimation uncertainty.
- [ ] Quantify and interpret temporal trends. Choose an adapted modelisation for each indicator. The goal is to analyse their evolution across the time. Is the trend linear/non linear? What does the trend mean in our context?
  - [ ] Linear models (Decadal mean, annual std, annual cv, skewness)
    - [ ] Linear Regression on the annual average temperatures
  - [ ] Generalized models (annual std, annual cv, skewness)
  - [ ] Smoothing (annual std, annual cv, skewness)
  - [ ] or any other defensible approach
    - [ ] SVR (Decadal mean) for non linear trend
    - [ ] Mann-Kendall : for monotonic trend
    - [ ] ANOVA
    - [ ] T-tests
  - [ ] Explain why it suits the indicator’s behaviour

## 4. Regional Evolution Analysis

### 4.1 Group Selection
- [ ] Choose a subset of individual units (e.g : geographical areas) that you consider interesting (e.g high temperatures, distinctive trends).


### 4.2 Group Analysis
- [ ] For each selected units:
  - [ ] Analyze temporal evolution patterns
  - [ ] Quantify uncertainty using confidence intervals
  - [ ] Comment on the limitations of our estimation procedure
- [ ] Discuss potential climate reasons behind the observed pattern (based on external knowledge or plausible hypotheses).


## 5. Synthesis and Recommendations

### 5.1 Key Findings
- [ ] Summarize the main insights you discovered
  - [ ] Highlight converging evidence across indicators as well as any contradictions

### 5.2 Recommendations
- [ ] Outline actionable recommendations for futur data collection (optioinal).
  - [ ] Suggest methodological improvements
  - [ ] Propose additional indicators
  - [ ] Identify future research questions / Follow-up questions that deserve investigation

### 5.3 Limitations Analysis
- [ ] Document key limitations:
  - [ ] Data quality issues
  - [ ] Modeling assumptions
  - [ ] Sensitivity to methodological choices

