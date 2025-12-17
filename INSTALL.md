# Installation Guide

## Prerequisites

- **Python 3.8 or higher** (recommended: Python 3.10+)
- **pip** (Python package manager)
- **Git** (optional, for cloning)

---

## Installation Methods

### Option 1: Quick Install (Recommended)

```bash
# Navigate to project directory
cd HSE

# Install all dependencies
pip install -r requirements.txt
```

### Option 2: Install with Exact Versions (For Reproducibility)

```bash
# Use frozen requirements for exact package versions
pip install -r requirements-frozen.txt
```

### Option 3: Manual Installation

```bash
pip install numpy pandas matplotlib scikit-learn jupyter notebook ipykernel
```

---

## Virtual Environment Setup (Recommended)

### Using venv (Python built-in)

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### Using conda

```bash
# Create conda environment
conda create -n synthetic-econ python=3.10

# Activate environment
conda activate synthetic-econ

# Install dependencies
pip install -r requirements.txt
```

---

## Verify Installation

```bash
# Check Python version
python --version

# Verify packages
pip list | grep -E "numpy|pandas|scikit-learn|matplotlib|jupyter"
```

Expected output:
```
jupyter                1.0.0
matplotlib             3.8.2
numpy                  1.26.4
pandas                 2.2.0
scikit-learn           1.4.0
...
```

---

## Running the Notebook

### Method 1: Jupyter Notebook

```bash
# Start Jupyter Notebook server
jupyter notebook

# In browser, navigate to:
# http://localhost:8888/notebooks/synthetic_data_economy%20(1).ipynb
```

### Method 2: JupyterLab (Alternative)

```bash
# Install JupyterLab (if not already installed)
pip install jupyterlab

# Start JupyterLab
jupyter lab
```

### Method 3: VS Code

1. Install **Python** extension in VS Code
2. Install **Jupyter** extension in VS Code
3. Open `synthetic_data_economy (1).ipynb`
4. Select Python kernel (your virtual environment)
5. Run cells with `Shift+Enter`

---

## Troubleshooting

### Issue: `ModuleNotFoundError: No module named 'sklearn'`

**Solution:**
```bash
pip install scikit-learn
```

### Issue: Jupyter kernel not found

**Solution:**
```bash
# Install IPython kernel
python -m ipykernel install --user --name=synthetic-econ

# Select kernel in Jupyter: Kernel → Change Kernel → synthetic-econ
```

### Issue: Permission denied on Windows

**Solution:**
```bash
# Run command prompt as Administrator, or use:
pip install --user -r requirements.txt
```

### Issue: SSL certificate error

**Solution:**
```bash
pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt
```

---

## Platform-Specific Notes

### Windows
- Use PowerShell or Command Prompt
- Virtual environment activation: `venv\Scripts\activate`

### macOS
- May need to use `python3` instead of `python`
- Virtual environment activation: `source venv/bin/activate`

### Linux
- Install system dependencies (if needed):
  ```bash
  sudo apt-get install python3-pip python3-venv
  ```

---

## Updating Dependencies

```bash
# Update all packages to latest compatible versions
pip install --upgrade -r requirements.txt

# Update specific package
pip install --upgrade numpy
```

---

## Uninstallation

```bash
# Deactivate virtual environment (if active)
deactivate

# Remove virtual environment directory
rm -rf venv  # macOS/Linux
rmdir /s venv  # Windows

# Uninstall packages (if not using venv)
pip uninstall -r requirements.txt -y
```

---

## Minimal Requirements

If disk space is limited, install only essential packages:

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

**Note:** This is the minimal set required to run the notebook. Optional packages (seaborn, tqdm) are not strictly necessary.

---

## Checking Compatibility

```bash
# Check if packages are compatible with your Python version
pip check
```

Expected output: `No broken requirements found.`

---

## Additional Resources

- [Python Virtual Environments Guide](https://docs.python.org/3/tutorial/venv.html)
- [Jupyter Documentation](https://jupyter-notebook.readthedocs.io/)
- [NumPy Installation Guide](https://numpy.org/install/)
- [Scikit-learn Installation](https://scikit-learn.org/stable/install.html)

---

**Installation Time:** ~2-5 minutes (depending on internet speed)
**Disk Space Required:** ~500 MB (including dependencies)

---

For issues not covered here, please check the main [README.md](README.md) or open an issue.
