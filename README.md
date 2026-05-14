# NASDA — Neuroimaging Autism Spectrum Disorder Analyser

NASDA (Neuroimaging Autism Spectrum Disorder Analyser) is an open-source machine learning and visualisation tool developed as part of a Bachelor Graduation Thesis at TU Delft.

The project investigates the classification of Autism Spectrum Disorder (ASD) from resting-state functional MRI (rs-fMRI) data using interpretable machine learning methods and graph-based neuroimaging features.

The system combines:
- rs-fMRI feature processing
- machine learning classification
- feature importance analysis
- interactive visualisation through a graphical user interface (GUI)

The project was developed using the ABIDE I dataset and focuses on balancing:
- interpretability
- reproducibility
- neuroscientific usefulness
- classification performance

The accompanying thesis achieved classification accuracies up to 64.4% balanced accuracy using interpretable models such as Support Vector Machines and Logistic Regression on Pearson correlation features.

---

# Thesis Information

**Title:**  
*Design and Evaluation of Classifiers for Autism Spectrum Disorder from rs-fMRI Data – Autism Detection based on Brain Graph Features*

**Authors:**  
- H4naka
- cxwchen

**Institution:**  
TU Delft

**Supervisors:**  
- Prof. dr. ir. Geert Leus
- ir. Ruben Wijnands

**Degree:**  
BSc Electrical Engineering

**Year:**  
2025

---

# Project Goals

The primary goals of NASDA were:

1. Classify ASD vs Typical Control (TC) subjects using rs-fMRI data.
2. Compare traditional Pearson correlation features against graph-based features.
3. Evaluate classifier robustness across acquisition sites, age groups, and sex.
4. Investigate feature importance for neuroscientific interpretability.
5. Provide an interactive GUI for neuroscientific exploration and experimentation.

---

# Project Structure and Collaboration

NASDA was developed as part of a larger multi-group Bachelor Graduation Project at TU Delft.

The overall project was divided into multiple specialised subgroups responsible for different stages of the ASD detection pipeline, including:
- feature extraction
- graph inference
- feature engineering
- feature selection
- classification
- visualisation

This repository primarily contains the work of the classification and integration subgroup.

---

# Contributions

## H4naka

## cxwchen

## Additional Contributors
Additional project members contributed to:
- graph feature generation
- graph inference methods
- covariance estimation pipelines
- feature selection systems
- supporting research infrastructure

Their work formed important upstream components integrated into the NASDA pipeline and broader graduation project.

---

# Features

## Machine Learning Pipeline
- Logistic Regression
- Support Vector Machines (SVM)
- Decision Trees
- Random Forests
- Multi-Layer Perceptrons (MLP)
- Linear Discriminant Analysis (LDA)
- K-Nearest Neighbours (KNN)

## Neuroimaging Features
- Pearson correlation functional connectivity matrices
- Graph-based brain connectivity features
- AAL atlas ROI mapping
- Functional connectivity analysis

## Evaluation Methods
- Sex-specific evaluation
- Age-specific evaluation
- AUROC, sensitivity, specificity, balanced accuracy, and F1-score

## GUI Functionality
- Feature selection
- Classifier selection
- Subject selection
- Custom CSV importing
- Performance reporting
- Pipeline control
- Brain region visualisation

---

# Repository Structure

```text
NASDA/
│
├── HR_V1_0_03.py              # Main GUI and application entry point
├── classification.py          # Classification pipeline logic
├── classifiers.py             # Classifier implementations/configuration
├── hyperparametertuning.py    # Hyperparameter optimisation
├── performance.py             # Performance metric calculations
├── featureimportance.py       # Feature importance analysis
├── feature_selection_methods.py
├── basicfeatureextraction.py  # Pearson correlation feature extraction
├── nilearnextraction.py       # Nilearn-based extraction utilities
├── nilearndetection.py        # Brain visualisation and detection
├── visualise.py               # Plotting and ROI visualisation
├── plot.py                    # Plotting utilities
├── loaddata.py                # Dataset loading utilities
├── functionality_buttons.py   # GUI interaction logic
├── selection_buttons.py       # GUI selection controls
├── test.py                    # Startup/testing script
├── Brain_background.png
├── logo.ico
└── LICENSE
```

---

# Dataset

This project uses the:

## ABIDE I Dataset
Autism Brain Imaging Data Exchange I (ABIDE I)

The dataset contains resting-state functional MRI scans collected from multiple international acquisition sites.

Because ABIDE data cannot be redistributed directly, users must obtain the dataset independently.

---

# Installation

## Requirements

Recommended:
- Python 3.10+
- Windows environment (original development platform)

Main libraries used:
- scikit-learn
- nilearn
- numpy
- pandas
- matplotlib
- tkinter
- Pillow

Install dependencies:

```bash
pip install scikit-learn nilearn numpy pandas matplotlib pillow
```

---

# Running NASDA

The application was primarily executed through:

```python
from HR_V1_0_03 import *
import HR_V1_0_03

check()

if __name__ == "__main__":
    start()
```

Or alternatively:

```bash
python test.py
```

depending on local configuration.

---

# Methodology Overview

## Feature Extraction

Two feature representations were evaluated:

### Pearson Correlation Features
Functional connectivity matrices were constructed using Pearson correlation between AAL atlas brain regions.

### Graph-Based Features
Graph-theoretical features generated from ICA-derived connectivity representations and graph inference techniques.

---

## Harmonisation

Multi-site harmonisation was performed using:
- NeuroHarmonize
- ComBat-based correction

to reduce scanner and site-specific variability in multisite classification experiments.

---

## Evaluation Strategy

Models were evaluated using:
- Stratified 5-fold cross validation
- Leave-One-Group-Out cross validation

Subgroup analyses included:
- acquisition site
- sex
- age-based evaluations

---

# Results Summary

Key findings from the thesis include:

- Logistic Regression, SVM, and MLP achieved the strongest performance on Pearson correlation features.
- Graph-based features generally underperformed compared to Pearson correlation features in the current implementation.
- Important brain connectivity regions consistently involved:
  - inferior occipital gyrus
  - superior temporal pole
  - precuneus
  - cerebellum

The project demonstrated that interpretable machine learning methods remain competitive for ASD classification while offering substantially greater neuroscientific interpretability than many deep learning approaches.

---

# GUI Preview

NASDA includes an interactive GUI intended for neuroscientific experimentation and exploratory analysis.

The interface supports:
- model selection
- feature selection
- visualisation
- performance inspection

Repository screenshots may be added in the future.

---

# Future Improvements

Potential future work includes:
- deep learning architectures
- improved harmonisation techniques
- external dataset validation
- improved graph feature engineering
- GPU acceleration
- modular package restructuring
- expanded GUI functionality

---

# Citation

If you use this repository in academic work, please cite the accompanying thesis.

```bibtex
@thesis{nasda2025,
  title={Design and Evaluation of Classifiers for Autism Spectrum Disorder from rs-fMRI Data},
  author={H4naka and cxwchen},
  institution={Delft University of Technology},
  year={2025},
  url={https://github.com/H4naka/NASDA}
}
```

---

# Licence

This repository is released under the licence included in the repository.

---

# Acknowledgements

Special thanks to:
- Prof. dr. ir. Geert Leus
- ir. Ruben Wijnands

and the collaborating graduation subgroups contributing to feature extraction and graph design research.
