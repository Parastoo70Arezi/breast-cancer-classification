# Breast Cancer Classification Using Machine Learning

## Overview
This project applies machine learning techniques to classify breast tumors as **benign** or **malignant** using the Wisconsin Breast Cancer Dataset. Three classification models were implemented and compared: Logistic Regression, Random Forest, and Support Vector Machine (SVM).

## Dataset
- **Source:** Wisconsin Breast Cancer Dataset
- **Samples:** 569 (357 Benign, 212 Malignant)
- **Features:** 30 numerical features extracted from digitized images of fine needle aspirate (FNA) of breast masses
- **Target:** Diagnosis (Benign = 0, Malignant = 1)

## Features Description
Each sample contains three types of measurements for 10 cell nucleus characteristics:
- **_mean:** Mean value
- **_se:** Standard error
- **_worst:** Largest/worst value

Key characteristics include: radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, and fractal dimension.

## Project Structure
```
breast-cancer-classification/
├── breast_cancer_classification.ipynb
├── wisc_bc_data.csv
└── README.md
```

## Methodology
1. **Exploratory Data Analysis (EDA)**
   - Class distribution analysis
   - Feature distribution histograms
   - Correlation heatmap
   - Boxplots comparing benign vs malignant features
   - Pairplot of top correlated features

2. **Preprocessing**
   - Removed irrelevant columns (id)
   - Encoded target variable
   - Train/test split (80/20) with stratification
   - Feature scaling using StandardScaler

3. **Models**
   - Logistic Regression (solver: liblinear)
   - Random Forest (100 estimators)
   - Support Vector Machine (RBF kernel)

## Results

| Model | Accuracy | Recall (Malignant) |
|-------|----------|-------------------|
| Logistic Regression | 97.37% | 0.98 |
| Random Forest | 93.86% | 0.93 |
| SVM | 98.25% | 0.98 |

## Key Findings
- **SVM achieved the highest accuracy (98.25%)**
- **Most important features:** `area_worst` and `points_worst`
- From a biological perspective, malignant tumors show larger cell areas and more irregular boundaries — consistent with pathological hallmarks of cancer aggressiveness
- `_worst` features outperformed `_mean` features in predictive power, reflecting that the most abnormal cells drive malignancy

## Biological Interpretation
The dominance of `area_worst` and `points_worst` aligns with known cancer biology:
- Malignant cells undergo uncontrolled proliferation, resulting in larger cell sizes
- Irregular concave boundaries reflect loss of normal cell architecture
- These morphological features mirror what pathologists assess under microscopy

## Requirements
```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

## Author
Parastoo | English Language Teacher & Cancer Biology Researcher  

