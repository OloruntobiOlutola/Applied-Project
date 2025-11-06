# Applied Project — Climate Temperature Analysis

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)

**Statistical Hypothesis Testing of Global Temperature Trends**

---

## 🎯 Project Overview

This project conducts rigorous statistical hypothesis testing to determine whether there are significant changes in global land temperature over time (1750-2015).

### Research Question
**Are there statistically significant changes in global land temperature over time?**

### Hypotheses
- **H₀ (Null Hypothesis)**: There are NO significant changes in temperature over time
- **H₁ (Alternative Hypothesis)**: There ARE significant changes in temperature over time

### Methodology
The analysis applies multiple independent statistical tests to evaluate the null hypothesis:
1. **Linear Regression Analysis** — Tests for linear temporal trends
2. **Mann-Kendall Trend Test** — Non-parametric test for monotonic trends
3. **Independent t-Test** — Compares early vs recent period temperatures
4. **ANOVA** — Tests for differences across time periods
5. **Mann-Kendall with Uncertainty** — Examines measurement precision evolution

The project uses the Berkeley Earth climate dataset, containing monthly temperature observations from 1750 to 2015.

---

## 📁 Repository Structure

```
Applied Project/
├── README.md                 # Project documentation
├── requirement.txt           # Python dependencies
└── notebooks/
    └── app.ipynb            # Main analysis notebook
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.11 or higher
- pip (Python package manager)

### Installation & Setup

1. **Clone or download the repository**
   ```bash
   cd "Applied Project"
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python3 -m venv .venv
   ```

3. **Activate the virtual environment**
   - On macOS/Linux:
     ```bash
     source .venv/bin/activate
     ```
   - On Windows:
     ```bash
     .venv\Scripts\activate
     ```

4. **Install dependencies**
   ```bash
   pip install -r requirement.txt
   ```

### Running the Analysis

**Launch Jupyter Notebook/Lab:**
```bash
jupyter lab notebooks/app.ipynb
```
or
```bash
jupyter notebook notebooks/app.ipynb
```

The notebook will automatically download the dataset from Kaggle using the `kagglehub` library — no manual data download required.

### Running All Cells

Once the notebook opens:
1. Go to **Run** menu → **Run All Cells** (or use Shift+Enter to run cells sequentially)
2. The analysis will execute all statistical tests and generate visualizations
3. Results and conclusions will be displayed at the end of the notebook

---

## 📊 Dataset

**Source**: [Berkeley Earth – Climate Change: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

The analysis uses **GlobalTemperatures.csv**, containing:
- 3,192 monthly observations from January 1750 to December 2015
- Land average temperature measurements (°C)
- Measurement uncertainty values (°C)

The dataset is accessed directly via the `kagglehub` Python library during notebook execution.

---

## 🛠️ Technologies & Libraries

**Core Python Libraries:**
- `pandas` — Data manipulation and analysis
- `numpy` — Numerical computations
- `scipy` — Statistical tests and distributions
- `statsmodels` — Statistical modeling and QQ-plots
- `matplotlib` & `seaborn` — Data visualization
- `kagglehub` — Automatic dataset download from Kaggle
- `pymannkendall` — Mann-Kendall trend analysis

---

## 📝 Project Workflow

The notebook follows this analytical workflow:

1. **Data Loading & Preparation**
   - Load dataset from Kaggle
   - Clean missing values
   - Create annual aggregations

2. **Exploratory Data Analysis**
   - Visualize temperature distributions
   - Examine temporal patterns
   - Analyze measurement uncertainty

3. **Distribution Analysis**
   - Test for normality
   - Identify best-fitting distributions
   - Calculate confidence intervals

4. **Hypothesis Testing**
   - Apply multiple statistical tests
   - Evaluate null hypothesis
   - Generate comprehensive summaries

5. **Results & Visualization**
   - Professional publication-quality plots
   - Statistical test summaries
   - Interpretations and conclusions

---

## 🔄 Reproducibility

All analyses are fully reproducible:
- Single notebook contains complete analysis pipeline
- Deterministic statistical tests (no randomness)
- Automatic dataset version control via `kagglehub`
- All dependencies specified in `requirement.txt`

---

## 📚 Resources

**Dataset:**
- [Berkeley Earth Dataset on Kaggle](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

**Statistical Methods:**
- [Mann-Kendall Trend Test](https://link.springer.com/article/10.1007/s10661-020-08615-x)
- [Student's t-distribution](https://online.stat.psu.edu/stat415/lesson/2/2.2)
- [Model Selection (AIC/BIC)](https://www.methodology.psu.edu/resources/AIC-vs-BIC/)

---

## 📄 License

MIT License

---

## 👥 Authors

- [Julie DORNAT](https://github.com/JulieDornat) : 22001111
- [Oloruntobi OLUTOLA](https://github.com/OloruntobiOlutola) 22504382
- [Sukhjot KAUR](https://github.com/Sukhjot-Kaur-AI) 22510515

For questions or contributions, please open an issue or submit a pull request.
