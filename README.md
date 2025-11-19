# RNA_Seq_Data_Preprocessing_-_Differential_Expression_Analysis
RNA_Seq_Data_Preprocessing_&amp;_Differential_Expression_Analysis
# 📊 RNA-Seq Differential Expression (DGE) Analysis Workflow in Python

This repository contains a **Jupyter Notebook** pipeline demonstrating the core concepts of **RNA-Seq data preprocessing, Quality Control (QC), and Differential Gene Expression (DGE)** analysis using standard Python libraries.

The workflow uses **simulated Poisson-distributed count data** to illustrate the calculation of log2 Fold Change ($\log_2 \text{FC}$) and statistical significance (p-value via OLS) between Control and Treatment groups, culminating in interactive volcano plot visualization.

## 🚀 Key Features

* **Simulated Data Generation:** Creates realistic, Poisson-distributed count data (100 genes, 10 samples) with inherent differential expression for demonstration purposes.
* **Data Preprocessing:** Implements **$\log_2$ transformation** ($\log_2(\text{counts} + 1)$) for normalization prior to statistical testing and visualization.
* **Log2 Fold Change Calculation:** Calculates the $\log_2 \text{FC}$ based on the mean normalized expression between groups.
* **Simple Statistical Model:** Uses the **Ordinary Least Squares (OLS) regression model** (via `statsmodels`) as a simple statistical test to assign p-values to each gene.
* **Exploratory Data Analysis (EDA):** Generates a **Boxplot** for visual inspection of expression distribution across samples.
* **Interactive Visualization:** Generates an **Interactive Volcano Plot** (using Plotly) to summarize DGE results ($\log_2 \text{FC}$ vs. $-\log_{10} \text{p-value}$) with hover functionality.
* **DEG Identification:** Filters results based on user-defined thresholds ($\log_2 \text{FC} > 1$ and $\text{p-value} < 0.05$).

---

## 🔬 Analysis Steps

The notebook is structured into the following executable steps:

1.  **Data Simulation:** Generates count data and corresponding metadata (Control vs. Treatment).
2.  **Normalization:** Applies $\log_2$ transformation.
3.  **QC/EDA:** Generates a **Boxplot** to check sample distribution.
4.  **DGE Calculation:** Computes mean expression and **$\log_2 \text{Fold Change}$** for all genes.
5.  **Statistical Testing:** Performs **OLS regression** for each gene to obtain **p-values**.
6.  **Volcano Plot Generation:** Creates both a static and an **interactive Plotly Volcano Plot** for visualization.
7.  **Output:** Prints and saves the list of significantly differentially expressed genes.

---

## 🛠️ Prerequisites and Execution

### Requirements

To run this notebook, you need a Python environment with the following libraries:

* `pandas`
* `numpy`
* `seaborn`
* `matplotlib`
* `statsmodels`
* `plotly.express` / `plotly.graph_objects`

### How to Run

1.  Open the **`RNA_Seq_Data_Preprocessing_&_Differential_Expression_Analysis.ipynb`** file in a Jupyter environment (e.g., JupyterLab, VS Code, or Google Colab).
2.  Execute all cells sequentially.

---

## 📊 Example Output

The notebook outputs two primary visualization figures:

1.  **Log2-normalized Expression Boxplot:** Confirms that the simulated data has shifted distributions between the Control and Treatment groups.
2.  **Interactive Volcano Plot:** Clearly visualizes the simulated differential expression, showing that the majority of genes fall into the **upper-right quadrant** (Upregulated and Significant), aligning with the higher Poisson lambda used for the treatment group simulation.

The final output is a pandas DataFrame displaying genes that meet the significance criteria ($\log_2 \text{FC} > 1$ and $\text{p-value} < 0.05$).
