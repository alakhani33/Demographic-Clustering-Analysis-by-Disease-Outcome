
# Demographic Clustering Analysis by Disease Outcome

## Overview
This project analyzes a dataset of individuals to determine whether demographic clusters differ between people affected by a disease (`OUTCOME = 1`) and those not affected (`OUTCOME = 0`).

We applied clustering techniques and statistical tests to answer:

- Are there distinct demographic clusters within each group?
- Do clusters differ significantly across disease outcomes?

## Methodology

### 1. Data Preparation
- Selected **25 demographic variables** (age, sex, race, insurance, deprivation index).
- Normalized data using **standard scaler**.
- Split dataset into two groups by `OUTCOME`.

### 2. Clustering
For each group:
- Tested clustering with **KMeans**, **Agglomerative Clustering**, **Birch**.
- Determined optimal number of clusters using **Elbow**, **Silhouette**, **Calinski-Harabasz**.
- Selected **3 clusters** as optimal.
- Chose best clustering algorithm per group:
  - `OUTCOME=0`: **Agglomerative Clustering** (highest Calinski-Harabasz)
  - `OUTCOME=1`: **KMeans** (highest Calinski-Harabasz)

### 3. Cluster Profiling
- Computed **mean demographics** per cluster.
- Compared clusters **within each group** and **across groups**.

### 4. Statistical Testing
- Conducted **t-tests** (continuous variables) and **chi-squared tests** (categorical variables).
- Compared clusters **within groups** and **between same-number clusters across groups**.

## Key Findings

✅ Clusters **within each outcome group are significantly different** (age, deprivation index, insurance type, race).  
✅ Clusters in `OUTCOME=1` group had **higher deprivation indices and younger affected individuals** in one cluster.  
✅ **Significant differences in continuous demographics between same-number clusters across groups**.  
❌ **No significant differences in categorical variables (race, sex, insurance) between same-number clusters across groups**.

## How to Run
1. Install requirements:
   ```bash
   pip install pandas scikit-learn scipy matplotlib
   ```
2. Run the provided Python script.
3. Results will print summaries and generate diagnostic plots.

## Files
- `clustering_analysis.ipynb`: full Python analysis code.
- `README.md`: this document.
