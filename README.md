## Note on Documentation

This README provides comprehensive project documentation including:
- Installation instructions
- Technical implementation details
- Extended analysis and recommendations

For the **core academic analysis**, please refer to the Jupyter notebook.
The README supplements the notebook with practical information for reproduction and deployment.

# Synthetic Data Economy: Macroeconomic Analysis & Policy Simulation

**A data science project demonstrating the power of synthetic datasets for economic modeling, policy analysis, and machine learning.**

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Methodology](#methodology)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Results & Findings](#results--findings)
- [Installation & Usage](#installation--usage)
- [Visualizations](#visualizations)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [References](#references)

---

## Overview

This project explores the use of **synthetic economic datasets** for rapid scenario analysis and policy decision-making. By generating realistic macroeconomic relationships programmatically, we can:

- Test policy interventions without waiting for real-world data
- Simulate extreme scenarios (recessions, booms) safely
- Train machine learning models while preserving privacy
- Validate economic theories through controlled experiments

### Why Synthetic Data?

**Real-world challenges:**
- Macroeconomic data releases have 1-2 month lags
- Privacy regulations (GDPR, CCPA) restrict access to individual-level data
- Surveys and experiments are expensive and time-consuming

**Synthetic data solution:**
- Generate data instantly with known ground truth
- No privacy concerns — no real individuals or companies
- Cost-effective and reproducible

---

## Key Features

### 1. **Realistic Economic Relationships**
- GDP, Inflation, Unemployment (Okun's Law)
- Monetary Policy (Taylor Rule approximation)
- Consumer Spending driven by national income
- AI Investments correlated with economic output

### 2. **Policy Scenario Analysis**
- **Recession simulation:** 15% GDP drop → comparable spending decline
- **Sensitivity analysis:** Response curves across GDP shocks (-30% to +20%)
- **Policy recommendations:** Interest rate cuts, fiscal stimulus

### 3. **Machine Learning with Proper Validation**
- **Linear Regression:** Baseline interpretable model
- **Random Forest:** Regularized model to control complexity
- **Cross-validation:** 5-fold CV for robust performance estimates
- **Residual analysis:** Confirms model validity (homoscedasticity, normality)

### 4. **Statistical Rigor**
- Train/test split (80/20) prevents data leakage
- Regularization prevents overfitting (`max_depth=10`, `min_samples_split=10`, `min_samples_leaf=5`)
- Feature importance analysis identifies key economic drivers
- Comprehensive correlation analysis (heatmap visualization)

---

## Methodology

### Data Generation Process

```python
# Macroeconomic indicators (n=5000 observations)
GDP ~ Normal(50000, 10000)
Inflation ~ Normal(6%, 1.5%)
Unemployment = f(GDP, noise)  # Okun's Law
Interest_Rate = f(Inflation, noise)  # Taylor Rule
AI_Investments = 0.04 × GDP + noise
Consumer_Spending = 0.25 × GDP + Normal(0, 7)
```

**Key design principles:**
- Intentional noise (σ = 7) mimics real-world unpredictability
- Economic relationships follow established theories
- Clipping ensures realistic ranges (e.g., unemployment ∈ [3%, 18%])

### Analysis Pipeline

1. **Visual Exploration** → Scatter plots verify economic logic
2. **Correlation Analysis** → Heatmap reveals variable relationships
3. **Scenario Testing** → Recession shock + sensitivity curves
4. **ML Modeling** → Predictive models with cross-validation
5. **Residual Diagnostics** → Validate model assumptions

---

## Project Structure

### File Organization

| Category | File | Purpose |
|----------|------|---------|
| **Core Analysis** | `synthetic_data_economy_project.ipynb` | Main analysis notebook (13 sections + subsections) |
| **Documentation** | `README.md` | Comprehensive project documentation |
| | `QUICKSTART.md` | 3-step quick start guide |
| | `INSTALL.md` | Detailed installation & troubleshooting |
| **Dependencies** | `requirements.txt` | Core Python packages |
| | `requirements-frozen.txt` | Pinned versions (exact reproducibility) |
| **Project Meta** | `LICENSE` | Educational use license |
| | `.gitignore` | Git version control exclusions |

### Directory Tree
```
HSE_synthetic_data_economy/
├── 📓 synthetic_data_economy_project.ipynb
├── 📖 README.md
├── ⚡ QUICKSTART.md
├── 📋 INSTALL.md
├── 📦 requirements.txt
├── 🔒 requirements-frozen.txt
├── ⚖️ LICENSE
└── 🚫 .gitignore
```

### Notebook Structure (13 Main Sections)

1. **Abstract** — Brief overview of project goals and methods
2. **Introduction** — Motivation for synthetic data in economics
3. **Motivation and Related Papers** — Academic context and literature review
4. **Experimental Design** — Dataset structure and analysis stages
5. **Generation of Synthetic Dataset** — 5000 synthetic observations with economic relationships
6. **Visual Exploration of Synthetic Economic Relationships** — GDP vs Spending, Unemployment, Interest Rates
7. **Correlation Structure of the Synthetic Economy** — Pairwise variable relationships and heatmap
8. **What-If Scenario: Simulating a Recession** — 15% GDP drop simulation
9. **Policy and Business Implications** — Business and monetary policy recommendations
10. **Sensitivity Analysis: How Does Spending React to Different GDP Shocks?** — Consumer spending response curves
11. **ML Analysis** — Linear Regression & Random Forest with validation
    - Model Performance Analysis
    - Residual Analysis Results
    - Feature Importance Analysis Results
12. **Conclusion** — Summary, advantages, limitations, recommendations
13. **Sources** — Academic and industry references

---

## Getting Started

### Quick Start (2 minutes)
See [QUICKSTART.md](QUICKSTART.md) for immediate setup.

### Detailed Setup
See [INSTALL.md](INSTALL.md) for:
- Virtual environment configuration
- Dependency troubleshooting
- Platform-specific instructions

### Reproducibility
Use `requirements-frozen.txt` for exact package versions:
```bash
pip install -r requirements-frozen.txt
```

---

## Technologies Used

**Core Libraries:**
- `numpy` — Numerical computations & random data generation
- `pandas` — Data manipulation & analysis
- `matplotlib` — Data visualization
- `scikit-learn` — Machine learning models & validation

**Models:**
- **Linear Regression** — Interpretable baseline (Test R² = 0.879)
- **Ridge Regression** — L2 regularization (Test R² = 0.879)
- **Lasso Regression** — L1 regularization (Test R² = 0.879)
- **Random Forest Regressor** — Regularized nonlinear model (Test R² = 0.892)
  - Regularized: `max_depth=10`, `min_samples_split=10`, `min_samples_leaf=5`

**Validation Techniques:**
- Train/test split (80/20)
- 5-fold cross-validation
- Residual analysis (homoscedasticity, normality tests)

---

## Results & Findings

### Economic Relationships (Validated)

| Relationship | Evidence | Theoretical Basis |
|-------------|----------|-------------------|
| GDP → Consumer Spending | Strong positive correlation | Keynesian consumption function |
| GDP ↔ Unemployment | Negative correlation | Okun's Law |
| Inflation → Interest Rate | Positive correlation | Taylor Rule (monetary policy) |
| GDP → AI Investments | Moderate positive correlation | Investment accelerator |

### Policy Simulation Results

**Recession Scenario (15% GDP drop):**
- Consumer spending shows comparable decline
- **Recommended policy response:**
  - Central bank: Cut interest rates by 2-3%
  - Fiscal policy: Increase government spending
  - Business strategy: Reduce inventory, increase cash reserves

### Machine Learning Performance

| Model | Test R² | CV R² (5-fold) | Interpretation |
|-------|---------|----------------|----------------|
| Linear Regression | 0.879 | 0.892 ± 0.002 | Strong baseline performance |
| Ridge Regression | 0.879 | 0.892 ± 0.002 | L2 regularization, same as linear |
| Lasso Regression | 0.879 | 0.892 ± 0.002 | L1 regularization, same as linear |
| Random Forest (regularized) | 0.892 | 0.898 ± 0.002 | Slight advantage from nonlinear patterns |

**Key insight:** All models show strong performance due to:
1. **Clear linear relationship** between GDP and consumer spending (0.25 coefficient)
2. **Moderate noise level** (σ = 7) allows models to capture the underlying pattern
3. **Strong regularization** in Random Forest prevents overfitting while capturing nonlinear interactions

The similar performance across models confirms that the synthetic dataset follows a primarily linear consumption function, with Random Forest showing a slight advantage by capturing interaction effects between features.

### Feature Importance

**Top predictors of consumer spending:**
1. **GDP** — Dominant driver (highest importance by significant margin)
2. **Unemployment** — Moderate importance
3. **AI Investments** — Moderate importance
4. **Interest Rate** — Modest importance
5. **Inflation** — Modest importance

The feature importance distribution confirms the intended causal structure: GDP is the primary driver of consumer spending, while remaining indicators contribute indirectly through correlation with GDP or random variation.

---

## Installation & Usage

### Prerequisites

```bash
Python 3.8+
```

### Install Dependencies

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

### Run the Notebook

```bash
cd HSE_synthetic_data_economy
jupyter notebook synthetic_data_economy_project.ipynb
```

### Execute All Cells

1. Open the notebook in Jupyter
2. Click **Kernel → Restart & Run All**
3. Review outputs (visualizations + tables + analysis)

**Estimated runtime:** ~30 seconds

---

## Visualizations

The notebook generates comprehensive visualizations including:

### Exploratory Analysis
- **GDP vs Consumer Spending** — Scatter plot showing linear relationship
- **GDP vs Unemployment** — Negative correlation (Okun's Law)
- **Inflation vs Interest Rate** — Monetary policy response
- **Correlation Heatmap** — All pairwise relationships

### Scenario Analysis
- **Recession Impact** — Base economy vs 15% GDP drop
- **Sensitivity Curve** — Spending response to GDP shocks (-30% to +20%)

### ML Diagnostics
- **Feature Importance** — Horizontal bar chart (Random Forest)
- **Residuals vs Predicted** — Linear Regression diagnostic
- **Residuals vs Predicted** — Random Forest diagnostic
- **Residual Distributions** — Histograms (both models)

---

## Limitations

### Methodological
- **Moderate noise by design** (σ = 7) — Simulates real-world variability
- **Linear consumption function** — Real economies have nonlinear thresholds
- **High multicollinearity** (VIF > 10) — GDP correlates with other indicators, affecting coefficient stability
- **No time dynamics** — Static cross-sectional data (no lags, trends)
- **Correlation ≠ Causation** — Need causal inference for real policy

### Real-World Applicability
- **Cannot predict black swan events** (pandemics, wars, financial crises)
- **Assumes stable relationships** — Reality has structural breaks
- **No behavioral factors** — Ignores consumer psychology, expectations
- **Simplified monetary policy** — Real central banks use complex rules

### Data Quality
- **Sample size (5000)** — While adequate, larger datasets may capture more complexity
- **No validation against real data** — Purely synthetic benchmark

---

## Future Work

### Enhancements

1. **Time-series extension**
   - Add quarterly lags (GDP_t, GDP_t-1, GDP_t-2)
   - Model autocorrelation & seasonality
   - ARIMA/VAR models for forecasting

2. **Causal inference**
   - Instrumental variables (IV) regression
   - Difference-in-differences (DiD) for policy evaluation
   - Regression discontinuity design (RDD)

3. **Real data comparison**
   - Download GDP/inflation from FRED API
   - Compare synthetic vs real correlations
   - Validate realism of generated data

4. **Advanced ML models**
   - Gradient Boosting (XGBoost, LightGBM)
   - Neural networks for deep patterns
   - Ensemble methods (stacking)

5. **Interactive dashboard**
   - Streamlit/Dash app for live simulations
   - User-adjustable shock parameters
   - Real-time visualization updates

---

## References

### Academic Background

**Synthetic Data in Economics:**
- Rubin, D. B. (1993). *Statistical Disclosure Limitation*. Journal of Official Statistics.
- Nowok, B., Raab, G. M., & Dibben, C. (2016). *synthpop: Bespoke Creation of Synthetic Data in R*. Journal of Statistical Software.

**Economic Theories:**
- Okun, A. M. (1962). *Potential GNP: Its Measurement and Significance*. Proceedings of the Business and Economics Statistics Section.
- Taylor, J. B. (1993). *Discretion versus Policy Rules in Practice*. Carnegie-Rochester Conference Series on Public Policy.

**Recent Literature:**
1. Tait, J. (2025). Synthetic Data in Investment Management. CFA Institute Research & Policy Center. URL: https://rpc.cfainstitute.org/sites/default/files/docs/research-reports/tait_syntheticdataininvestmentmanagement_online.pdf

2. Yoon, J., Jarrett, D., Van der Schaar, M. (2019). Time-series Generative Adversarial Networks. Advances in neural information processing systems, 32 (NeurIPS 2019). URL: https://papers.nips.cc/paper_files/paper/2019/file/c9efe5f26cd17ba6216bbe2a7d26d490-Paper.pdf

3. Xu, L., Skoularidou, M., Cuesta-Infante, A., Veeramachaneni, K. (2019). Modeling Tabular Data using Conditional GAN. Advances in neural information processing systems, 32 (NeurIPS 2019). URL: https://papers.nips.cc/paper_files/paper/2019/file/254ed7d2de3b23ab10936522dd547b78-Paper.pdf

4. World Economic Forum (2025). Synthetic Data: The New Data Frontier. URL: https://reports.weforum.org/docs/WEF_Synthetic_Data_2025.pdf

**Market Statistics:**
- Global synthetic data market: approximately $1.1B (2023) → $11.2B (2030)
- Adopters: European Central Bank, UK Office for National Statistics, World Bank

### Tools & Libraries

- [NumPy Documentation](https://numpy.org/doc/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [Matplotlib Gallery](https://matplotlib.org/stable/gallery/index.html)

---

## License

This project is created for educational purposes as part of a mini-project at HSE University (Higher School of Economics).

---

## Contact & Acknowledgments

**Project Type:** Mini-project (team of 2)  
**Team Members:** [DaniilZebzeev](https://github.com/DaniilZebzeev), [aaanisimova](https://github.com/aaanisimova)  
**Institution:** HSE University — Digital Economics Program

**Feedback & Questions:**
Feel free to open an issue or reach out for collaboration opportunities.

---

**Last Updated:** December 2025  
**Notebook Version:** 1.0

---

## Quick Start Summary

```bash
# 1. Clone the repository
git clone https://github.com/DaniilZebzeev/HSE_synthetic_data_economy.git
cd HSE_synthetic_data_economy

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the notebook
jupyter notebook synthetic_data_economy_project.ipynb

# 4. Execute all cells (Kernel → Restart & Run All)
# 5. Review results: visualizations + tables + comprehensive analysis
```

**Expected output:** Comprehensive analysis of synthetic economy with ML models, policy scenarios, and validation diagnostics.

---

*Made with Python, Economics, and Data Science*
