# GMM-RBFN Cancer Classifier

A repository showcasing my Merit Prize submission for the Machine Learning class—presented at NTT Data—implementing and comparing Gaussian Mixture Model–driven Radial Basis Function Networks for classifying breast tumors as benign or malignant using scikit-learn’s Breast Cancer dataset.

## Table of Contents
- [Overview](#overview)  
- [Repository Structure](#repository-structure)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Methodology](#methodology)  
- [Results](#results)  
- [Author](#author)  
- [License](#license)  

## Overview  
This repository contains my Merit Prize submission for the ML class, which was presented at NTT Data. It implements and compares several approaches on the Breast Cancer dataset from scikit-learn: logistic regression as a baseline, EM clustering via Gaussian Mixture Models (GMM) to determine optimal clusters, and a Radial Basis Function Network (RBFN) whose hidden‐layer neurons correspond to GMM clusters.

## Repository Structure
```

GMM-RBFN-Cancer-Classifier/
├── Problem_Statement.pdf       # Original challenge description
├── G103368_notebook.ipynb      # Jupyter notebook with code & visualizations
├── G103368_report.pdf          # Formal report of methodology & findings
├── Presentation.pdf            # Powerpoint presentation shown at NTT Data Lisbon
└── README.md                   # This document

````

## Prerequisites
- **Python** 3.8+  
- **Jupyter Notebook**  
- **Python packages** (install via `pip`):  
  - numpy  
  - pandas  
  - scikit-learn  
  - matplotlib  
  - seaborn  

## Installation
```bash
git clone https://github.com/vasco-s-pereira/GMM-Driven-RBFN.git
cd MeritPrize
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
````

## Usage

1. Launch the notebook:

   ```bash
   jupyter notebook G103368_notebook.ipynb
   ```
2. Step through sections to preprocess data, run logistic regression, perform EM clustering, and train the RBFN.
3. Consult `G103368_report.pdf` for full analysis and `Presentation.pdf` for a concise overview.

## Methodology

1. **Data Preparation**

   * Loaded the Breast Cancer dataset from scikit-learn and split 70% train / 30% test.
   * Created three variants:

     * Original
     * Normalized
     * PCA-reduced (95% variance)&#x20;

2. **Baseline Logistic Regression**

   | Dataset    | Accuracy |   |
   | ---------- | -------- | - |
   | Original   | 96.5%    |   |
   | Normalized | 97.7%    |   |
   | PCA (95%)  | 97.7%    |   |

3. **Gaussian Mixture Models (GMM)**

   * Compared two covariance types: **full** vs **tied**.
   * Selected optimal number of clusters (k) by silhouette score and classification accuracy.&#x20;

4. **Radial Basis Function Network (RBFN)**

   * Used GMM cluster centers as hidden-layer centroids.
   * Gaussian kernel width β = 1/(2·d\_mean²).
   * Sigmoid output for binary classification.&#x20;

## Results

* **Best Configuration**: PCA-reduced data with tied-covariance GMM, k = 29.
* **RBFN Accuracy**: 98.8%, outperforming logistic regression baseline.&#x20;

## Author

Vasco Pereira
Computer Science Student, IST
[vasco.serpa.pereira@gmail.com](mailto:vasco.serpa.pereira@gmail.com)

## License

MIT License. See [LICENSE](LICENSE) for details.

```
```
