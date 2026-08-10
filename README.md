# Computational Intelligence 2026

Course materials for **Intro to Computational Intelligence** at the **University of Missouri, Fall 2026**.

This repository contains Jupyter notebooks, examples, project materials, and other course resources used throughout the semester.

---

## Getting the Course Materials

Open a terminal, Anaconda Prompt, or Miniforge Prompt and clone the repository:

```bash
git clone https://github.com/MizzouINDFUL/ComputationalIntelligence2026.git
cd ComputationalIntelligence2026
```

If you already cloned the repository, get the latest course materials with:

```bash
git pull
```

Run `git pull` regularly during the semester because notebooks and other course materials may be updated.

> **Important:** If Git reports that you have local changes that conflict with course updates, do not delete your work. Save or copy your work before trying to resolve the conflict.

A good practice is to keep your own project and assignment work separate from the original course notebooks.

---

# Python Environment

We will use a Conda environment named `ci`.

The main packages used in the course include:

- Python
- NumPy
- Matplotlib
- Pandas
- Jupyter
- IPython
- scikit-learn
- tqdm
- PyTorch

Additional packages may be installed later in the semester as needed.

---

# Windows Setup

## 1. Install Miniconda

Download and install the 64-bit Windows version of [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/).

After installation, open **Anaconda Prompt (Miniconda3)** from the Windows Start menu.

## 2. Create the Course Environment

Run:

```bash
conda create -n ci python -y
conda activate ci
```

Install the primary course packages:

```bash
conda install -c conda-forge numpy matplotlib jupyter ipython pandas scikit-learn tqdm -y
```

Install PyTorch:

```bash
conda install pytorch torchvision cpuonly -c pytorch -y
```

---

# macOS Setup

## 1. Install Miniforge

For modern Macs, especially Apple Silicon Macs (M1, M2, M3, M4, etc.), [Miniforge](https://github.com/conda-forge/miniforge) is recommended.

Follow the current installation instructions provided by the Miniforge project.

After installation, close and reopen Terminal.

Verify that Conda is available:

```bash
conda --version
```

If `conda` is not found, restart Terminal and try again.

You can also reload your shell configuration manually:

```bash
source ~/.zshrc
```

or, depending on your setup:

```bash
source ~/.zprofile
```

## 2. Create the Course Environment

Run:

```bash
conda create -n ci python -y
conda activate ci
```

Install the primary course packages:

```bash
conda install -c conda-forge numpy matplotlib jupyter ipython pandas scikit-learn tqdm -y
```

Install PyTorch:

```bash
conda install -c conda-forge pytorch torchvision -y
```

---

# Linux Setup

## 1. Install Miniconda or Miniforge

Install either [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/) or [Miniforge](https://github.com/conda-forge/miniforge).

Choose the installer appropriate for your Linux distribution and system architecture.

After installation, restart your terminal or reload your shell configuration:

```bash
source ~/.bashrc
```

or:

```bash
source ~/.zshrc
```

Verify that Conda is available:

```bash
conda --version
```

## 2. Create the Course Environment

Run:

```bash
conda create -n ci python -y
conda activate ci
```

Install the primary course packages:

```bash
conda install -c conda-forge numpy matplotlib jupyter ipython pandas scikit-learn tqdm -y
```

Install PyTorch:

```bash
conda install pytorch torchvision cpuonly -c pytorch -y
```

---

# Starting Jupyter

Each time you work on course material, first activate the course environment:

```bash
conda activate ci
```

Navigate to the repository folder:

```bash
cd ComputationalIntelligence2026
```

Then start Jupyter:

```bash
jupyter notebook
```

Your browser should open the Jupyter interface.

If you prefer JupyterLab and have it installed, you may instead run:

```bash
jupyter lab
```

---

# Testing Your Installation

After activating the `ci` environment, start Python or open a Jupyter notebook and try:

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
import sklearn
import torch

print("NumPy:", np.__version__)
print("Pandas:", pd.__version__)
print("scikit-learn:", sklearn.__version__)
print("PyTorch:", torch.__version__)
```

If these imports work without errors, your basic environment is ready.

---

# Updating Course Materials

The repository may change during the semester.

Before starting a new notebook, assignment, or project, update your local copy:

```bash
git pull
```

You can check whether your local repository has changes before pulling:

```bash
git status
```

If you have modified a course notebook and Git refuses to pull, save a copy of your work first.

For example, you can duplicate a notebook before editing it:

```text
FuzzySet.ipynb
FuzzySet_MyWork.ipynb
```

That helps keep your own work separate from files that may be updated in the repository.

---

# Troubleshooting

## 1. `conda` command not found

Close and reopen your terminal or Anaconda Prompt.

Then try:

```bash
conda --version
```

If Conda was just installed, you may need to reload your shell.

### macOS / Linux

```bash
source ~/.zshrc
```

or:

```bash
source ~/.bashrc
```

If that still does not work, verify that Miniconda or Miniforge was installed successfully.

---

## 2. Make sure the correct environment is active

Run:

```bash
conda env list
```

You should see an asterisk (`*`) next to `ci`.

For example:

```text
base
ci        *
```

If `ci` is not active, run:

```bash
conda activate ci
```

---

## 3. Check which Python is being used

### Windows

```bash
where python
```

### macOS / Linux

```bash
which python
```

The path should point to the `ci` environment rather than another Python installation.

---

## 4. Jupyter is using the wrong Python environment

If Jupyter starts but cannot import packages that you installed in `ci`, install an IPython kernel for the environment:

```bash
conda activate ci
python -m ipykernel install --user --name ci --display-name "Python (ci)"
```

Then restart Jupyter and select:

```text
Kernel -> Change Kernel -> Python (ci)
```

The exact menu name may vary slightly between Jupyter Notebook and JupyterLab.

---

## 5. A package cannot be imported

First activate the environment:

```bash
conda activate ci
```

Then try importing the package from Python:

```bash
python
```

For example:

```python
import numpy
import pandas
import sklearn
import torch
```

If a package is missing, reinstall it.

Example:

```bash
conda install -c conda-forge scikit-learn
```

For PyTorch on Windows or Linux:

```bash
conda install pytorch torchvision cpuonly -c pytorch
```

---

## 6. Jupyter command not found

Activate the environment:

```bash
conda activate ci
```

Then install Jupyter if needed:

```bash
conda install -c conda-forge jupyter
```

Try again:

```bash
jupyter notebook
```

---

## 7. Git command not found

Check whether Git is installed:

```bash
git --version
```

If the command is not found, install Git from [git-scm.com](https://git-scm.com/).

After installation, restart your terminal.

---

## 8. `git pull` reports local changes

First check what changed:

```bash
git status
```

Do **not** delete your work.

If you modified a course file, copy or rename your version before resolving the Git conflict.

A simple approach is:

1. Save your edited notebook under a new filename.
2. Restore the original course file.
3. Run `git pull`.
4. Compare your saved work with the updated course version.

If you are unsure, ask before using destructive Git commands.

---

## 9. Notebook kernel appears frozen

First try:

```text
Kernel -> Interrupt
```

If that does not help:

```text
Kernel -> Restart
```

Then rerun the notebook from the top.

Infinite loops, very large plots, or accidentally expensive code can make the kernel appear frozen.

---

## 10. A notebook works on one computer but not another

Check:

```bash
conda activate ci
conda env list
```

Then check package versions:

```bash
conda list
```

Make sure both systems are using the intended `ci` environment.

You can also verify Python:

```bash
python --version
```

---

# Useful Git Commands

Check repository status:

```bash
git status
```

Get the latest course files:

```bash
git pull
```

See recent commits:

```bash
git log --oneline -5
```

If you are working in your own Git repository and want to save your changes:

```bash
git add .
git commit -m "Update course work"
git push
```

Be careful with `git add .` and always run `git status` first so that you know which files are being committed.

---

# Getting Help

If something fails, copy the **full error message** before asking for help.

Useful information to include:

- your operating system;
- the command you ran;
- the full error message;
- the output of `conda env list`;
- the output of `python --version`; and
- whether the problem occurs in Terminal, Anaconda Prompt, or Jupyter.

This information makes troubleshooting much faster.
