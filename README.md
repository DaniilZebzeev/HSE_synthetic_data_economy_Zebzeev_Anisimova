[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]
(https://colab.research.google.com/github/DaniilZebzeev/HSE_synthetic_data_economy/blob/main/synthetic-data-economy.ipynb)

# 📊 Synthetic Data Economy — Python Simulation

This repository contains a fully reproducible Python-based simulation of a **synthetic economic dataset**.  
The project is part of the presentation:

**“Synthetic Data Economies:  
Data Without Humans — The Rise of Synthetic Economic Datasets for Policy and Business Strategy.”**

The goal is to demonstrate how artificially generated datasets can replicate realistic macroeconomic and consumer-level patterns for both **policy modeling** and **business strategy**.

---

## 🚀 Project Overview

Synthetic data allow analysts, economists, and researchers to:

- model GDP shocks and inflation responses  
- simulate consumer behavior  
- run risk-free economic experiments  
- generate unlimited non-sensitive datasets for AI/ML  
- build reproducible economic models without confidential data  

This project shows how to generate such a dataset using **NumPy**, **Pandas**, **Matplotlib**, and **Scikit-learn**.

---

## 🧠 Key Features

### ✔ Synthetic Macroeconomic Indicators  
- GDP  
- Inflation  
- AI Investments  

### ✔ Consumer-Level Variables  
- Consumer Spending  
- Generated through linear + stochastic relationships  

### ✔ Visualizations  
- **Scatter Plot:** GDP vs Consumer Spending  
- **Correlation Heatmap:** structure of the synthetic dataset  

### ✔ Validation  
A linear regression model (R² score) validates that synthetic relationships behave similarly to real-world economic patterns.

---

## 🧩 Example Code Snippet

```python
np.random.seed(42)
gdp = np.random.normal(50000, 10000, 500)
inflation = np.random.normal(6, 1.5, 500)
consumer_spending = 0.25*gdp + np.random.normal(0, 4000, 500)
````

This 5-line generator produces a realistic synthetic mini-economy.

---

## 📈 Visual Examples

### **Correlation Heatmap**

Shows relationships between GDP, inflation, investments, and spending.

### **GDP vs Consumer Spending**

A classic macroeconomic relationship reproduced synthetically.

Plots are stored in the `/plots` directory.

---

## 🛠 Technologies Used

* Python 3
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* Google Colab / Jupyter Notebook

---

## 📘 How to Run

1. Clone the repository:

```bash
git clone https://github.com/DaniilZebzeev/HSE_synthetic_data_economy.git
```

2. Open the notebook:

```
synthetic-data-economy.ipynb
```

3. Run all cells — the notebook is fully reproducible.

---

## 🎓 Author

**Daniil Zebzeev**
HSE University — Digital Economist: Mastering Python for Intelligent Analysis (2025)

---

## ⭐ Citation

```
Zebzeev, D. (2025). Synthetic Data Economy — Python Simulation. GitHub Repository.

