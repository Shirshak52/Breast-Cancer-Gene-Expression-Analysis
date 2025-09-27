# Breast Cancer Gene Expression Analysis  
This project analyzes **gene expression data collected from breast cancer patients and healthy individuals** to identify the *specific genes whose activity levels consistently differ between the two groups*. Using statistical tests and dimensionality reduction, the project highlights gene patterns that may serve as breast cancer indicators, helping separate patients and healthy individuals based on their gene expression profiles.

## About the Dataset
The dataset was taken from the ***Gene Expression Omnibus (GEO)*** and contains microarray gene expression data from 29 breast tissue samples. The **29 columns represent each patient** and **~54000 rows represent gene probes** that measure expression levels. The patients were marked either **"Normal"**, **"Normal Risk Atypia"**, **"High Risk"**, or **"High Risk Atypia"**. For simplicity, the former two have been labeled as **"Healthy"** while the latter two have been labeled as **"Cancer"** to allow clearer comparison.

For a more detailed understanding, the **webpage can be visited here**: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi. The ***GEO Accession ID is GSE153796***.

## Project Workflow
Data Preparation → Statistical Analysis → Dimensionality Reduction

### Data Preparation
Transposed the dataset so each **row represents a patient**, and each **column represents a gene probe**.
Assigned each patient a label: "Healthy" or "Cancer".  

### Statistical Analysis (T-test)
Ran **t-tests** on each gene to find which ones showed significant difference in expression levels between cancer and healthy patients.
Selected the genes with **p-values < 0.01 as the most significant**.  

### Dimensionality Reduction (PCA)
Applied **Principal Component Analysis** on the significant genes to reduce the dataset into 2 columns (i.e. dimensions) for 2D plotting.
**Visualized patients on a scatter plot**, showing clear grouping by health status **(cancer vs. healthy)**.  

## Results
Out of ~54000 gene probes, ***156 genes showed strong statistical significance (p < 0.01)*** between cancer and healthy patients.
PCA visualization using these genes showed mostly clear separation between the two patient groups, with some overlap:
Healthy and cancer patients generally clustered in distinct regions on the 2D plot.
This suggests that **gene expression patterns from a relatively small number of genes can help distinguish cancer risk**.  

## Conclusion
This project demonstrates how statistical testing and dimensionality reduction can revveal key differences in gene expression between breast cancer and healthy patients. A subset of 156 genes showed strong potential as breast cancer indicators. Visual analysis confirmed that these gene expression patterns can help separate the two groups. The results highlight how **even without machine learning models**, basic statistical tools and clear visualizations can uncover valuable biological insights.

## Code Implementation
For the code implementation of this project, please refer to the notebook itself.
