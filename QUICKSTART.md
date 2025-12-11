# Quick Start Guide

Get up and running in 5 minutes!

---

## 1️⃣ Install Python (if not already installed)

Download from: https://www.python.org/downloads/

**Minimum version:** Python 3.8+
**Recommended:** Python 3.10 or 3.11

---

## 2️⃣ Set Up Virtual Environment (Optional but Recommended)

```bash
# Navigate to project folder
cd HSE

# Create virtual environment
python -m venv venv

# Activate it
# Windows:
venv\Scripts\activate

# macOS/Linux:
source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

**Installation time:** ~2-3 minutes

---

## 4️⃣ Launch Jupyter Notebook

```bash
jupyter notebook
```

Your browser will open automatically at `http://localhost:8888`

---

## 5️⃣ Run the Analysis

1. Click on `synthetic_data_economy (1).ipynb`
2. Go to **Kernel** → **Restart & Run All**
3. Wait ~30 seconds for execution
4. Review results!

---

## Expected Output

✅ **10 visualizations** (scatter plots, heatmaps, residual plots)
✅ **5 data tables** (model performance, feature importance)
✅ **1 conclusion** with metrics and recommendations

---

## Troubleshooting

**Problem:** `ModuleNotFoundError`
**Solution:** `pip install scikit-learn numpy pandas matplotlib jupyter`

**Problem:** Jupyter won't start
**Solution:** `pip install --upgrade jupyter notebook`

**Problem:** Kernel not found
**Solution:** `python -m ipykernel install --user`

---

## Next Steps

- Read the full [README.md](README.md) for detailed explanations
- Check [INSTALL.md](INSTALL.md) for advanced setup options
- Modify code to test your own economic scenarios!

---

**Questions?** Open an issue or check the documentation.

---

**Total setup time:** < 5 minutes
**Notebook runtime:** ~30 seconds
**Skill level:** Beginner-friendly
