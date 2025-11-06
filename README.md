# Applied-Project — Climate Temperature Analysis
![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)

Independent statistic study of the Berkeley Earth Kaggle temperature dataset.

This project explores global temperature evolution and tests whether long-term climate warming is statistically significant using frequentist and machine learning approaches.

## Goals

This project aims to characterize and test the temporal behavior of global temperatures based on the Berkeley Earth dataset.

Rather than simply fitting a trend, we investigate the stability, variability, and evolution of the temperature distribution over time.

Specifically, we aim to:
1. Assess the long-term evolution of global mean temperature
- determine whether the temperature increase, decrease, stagnate or oscillate.
- Test whether the observed change is statistically significant.

2. Evaluate the stability of temperature variability
- Examine whether the variance of temperature remains constant or changes over time.

3. Analyze the temperature distribution shape
- Evaluate the evolution of the temperature indicators (mean, median, skewness, kurtosis) across decades.
- Study when outliers become more frequent.

4. Integrate uncertainty
- Evaluate how measurement uncertainty affects conclusions on temperature trends.

## Roadmap

1. Data preparation

- Cleaning: handle missing or invalid values, duplicates, and date inconsistencies.
- Validation: check for temporal continuity and measurement plausibility.
- Selection and Aggregation : select/add usefull columns for our study (by country, region, year, month).
- Transformation: resample monthly data into annual series for trend analysis.

2. Exploratory data analysis (EDA)

- Visual exploration: time series plots, boxplots, histograms, and heatmaps.
- Distributional checks: use QQ-plots and KDE (Kernel Density Estimate) to assess normality and shape.
- Seasonal decomposition: visualize distribution by seasons.
- Autocorrelation analysis: compute ACF/PACF, effective degrees of freedom (autocorrelation reduces independency), and identify dependency patterns.
- Outlier and anomaly detection: highlight extreme (boxplot) or inconsistent temperature values.
- Statistic indicators: mean, mediane, std,skewness, peak, gaps distribution.

3. Statistical testing (frequentist approach)

- Linear regression (GLSAR- Generalized Least Squares with AutoRegressive errors): estimate trend while accounting for autocorrelation, compare expected slope (if the temperature increases over time, we have an increasing slope) and experimental slope.
- Mann–Kendall test: non-parametric detection of monotonic trends, robust to outliers.
- T-test: compare mean temperatures between early and recent periods.
- ANOVA: evaluate inter-decade differences in mean temperature.
- Change-point detection: identify structural breaks using algorithms such as PELT.
- Interpretation: determine trend magnitude (°C/decade) and its statistical significance.

4. Machine learning approach - Predictive modeling

- Support Vector Regression (SVR): model nonlinear temperature trends and forecast future values.
- SVM Classification: assign temperature observations to historical epochs or climate phases.
- Evaluation metrics: MSE, accuracy and confusion matrix.
- Model comparison: contrast ML models with statistical baselines to evaluate added value.

5. Conclusion
- Produce summary
- Answer our problematic
- Make recommandations

## Dataset presentation

Source: [Berkeley Earth – Climate Change: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data) 


### Time coverage (for GlobalTemperatures.csv):

- Global land data: ~1750- 2015
- Land + Ocean data: ~1850-2015

### Files included

- GlobalLandTemperaturesByContry.csv: average monthly temperatures by country
- GlobalLandTemperaturesByState.csv: average monthly temperatures by state (limited coverage)
- GlobalLandTemperaturesByCity.csv: average monthly temperatures by city
- GlobalLandTemperaturesByMajorCity.csv: average monthly temperatures for major cities
- GlobalTemperatures.csv: global monthly averages (main dataset used)

### Key columns (from GlobalTemperatures.csv)

- dt: Date
- LandAverageTemperature
- LandAverageTemperatureUncertainty (95% CI) 
- LandMaxTemperature 
- LandMaxTemperatureUncertainty
- LandMinTemperature
- LandMinTemperatureUncertainty
- LandAndOceanAverageTemperature
- LandAndOceanAverageTemperature

This dataset enables multiple complementary analyses of climate trends and uncertainty.

### Possible limitations and issues

- Presence of seasons that can affect the distribution shape (opposite seasons between hemispheres)
- Measurement techniques have evolved and become increasingly accurate. The early data was collected using mercury thermometers.
- History events such as the modernisation and industrialisation altered measurement consistency. In the 1940s, the aiports constructions caused the moving of weather station.

## Repository contents
- [README.md](README.md) — this file
- [notebooks/](notebooks/) — exploratory analyses and reproducible reports (Jupyter)
  - [app.ipynb](notebooks/app.ipynb) — main analysis notebook
- [requirement.txt](requirement.txt) — Python package dependencies
- .venv/ — Python virtual environment (not tracked in git)

## Quick start
1. Set up environment:
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate  # On Windows: .venv\Scripts\activate
    pip install -r requirement.txt
    ```
2. Run analyses:
    ```bash
    jupyter lab notebooks/app.ipynb
    ```

The dataset is accessed directly from Kaggle using the `kagglehub` library (no manual download required).

## Reproducibility
- The main analysis notebook [app.ipynb](notebooks/app.ipynb) contains all exploratory analyses and visualizations
- Data is accessed directly from Kaggle via the `kagglehub` library
- Use conda if preferred — create environment from requirement.txt

## Resources

Datasets:
- [Berkeley Earth Dataset on Kaggle](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

Inspirations: 
- [Temperature by Country study](https://www.kaggle.com/code/amelinvladislav/map-of-temperatures-and-analysis-of-global-warming)

Sources:
- [Sampling in statistics and data analytics](https://medium.com/@narula.rashmi888/understanding-the-importance-of-sampling-in-statistics-and-data-analytics-47e58993ea5e)


## License & Authors
- License: MIT
- Authors: Applied Statistics Project team

For questions or contributions, open an issue or submit a PR.
