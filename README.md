# 🛍️ Mall Customer Segmentation using K-Means Clustering

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange?style=flat-square&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-2.x-green?style=flat-square&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-blueviolet?style=flat-square)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Charts-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

> **Unsupervised machine learning project** that segments mall customers into 5 distinct behavioral groups using K-Means Clustering — enabling data-driven marketing strategies based on income and spending patterns.

---

## 📌 Project Overview

Retail businesses collect rich customer data but often struggle to make sense of it. This project applies **K-Means Clustering** — an unsupervised machine learning algorithm — to a mall customer dataset to discover hidden customer segments without any predefined labels.

The end goal is to answer:
> **"Which customers should we focus our marketing budget on, and how?"**

---

## 🗂️ Dataset

| Detail | Info |
|--------|------|
| **Source** | [Kaggle — Mall Customer Segmentation Data](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) |
| **Records** | 200 customers |
| **Features** | 5 columns |
| **Target** | None (Unsupervised Learning) |

### Feature Description

| Column | Type | Description |
|--------|------|-------------|
| `CustomerID` | Integer | Unique customer identifier |
| `Gender` | Categorical | Male / Female |
| `Age` | Integer | Customer age (18–70) |
| `Annual Income (k$)` | Integer | Annual income in thousands USD |
| `Spending Score (1-100)` | Integer | Mall-assigned score based on purchase behaviour |

---

## 📊 Visualizations & Analysis

### Step 1 — Distribution of Annual Income
> Understanding how income is spread across all 200 customers before any modelling.

<img width="723" height="723" alt="plot_01_displot_income" src="https://github.com/user-attachments/assets/03442c42-1243-48c4-948f-58c4f9d42025" />


---

### Step 2 — Distribution of Age
> Checking the age range and spread of mall customers.

<img width="723" height="723" alt="plot_02_displot_Age" src="https://github.com/user-attachments/assets/cfe78fa5-5bc0-485e-84d0-11c10895a42e" />


---

### Step 3 — Distribution of Spending Score
> Understanding how spending scores are distributed — are customers mostly average, or spread across all levels?

<img width="723" height="723" alt="plot_02_displot_Spending_Score_1-100" src="https://github.com/user-attachments/assets/9de6e73e-5baa-49c1-ab96-9621c258f75e" />

---

### Step 4 — KDE Plot: Annual Income by Gender
> Kernel Density Estimation comparing male vs female income distributions.

<img width="899" height="659" alt="plot_03_kde_income_gender" src="https://github.com/user-attachments/assets/d2d89624-c21c-4b2c-8f1c-795e62575f19" />


---

### Step 5 — KDE Plot: Age by Gender
> Comparing the age distributions of male and female customers.

<img width="906" height="659" alt="plot_04_kde_Age" src="https://github.com/user-attachments/assets/2363f7c0-f8fe-49e5-b966-c5041bc0c9ad" />


---

### Step 6 — KDE Plot: Spending Score by Gender
> Females show a sharper, higher peak around spending score 50 — more concentrated spending behaviour.

<img width="891" height="659" alt="plot_04_kde_Spending_Score_1-100" src="https://github.com/user-attachments/assets/bf83a2e0-ff29-4a58-8eeb-0fddde1356c0" />


---

### Step 7 — Scatter Plot: Income vs Spending Score by Gender
> Pre-clustering visual. You can already see ~5 natural groups forming — confirming K-Means is the right approach.

<img width="874" height="659" alt="plot_05_scatter_income_spending" src="https://github.com/user-attachments/assets/e92989c3-caa0-4a5b-b026-5d5a3a00c450" />


---

### Step 8 — Pairplot (All Features by Gender)
> Every feature combination plotted against each other, colored by gender. A complete picture of all relationships in the data.

<img width="1652" height="1472" alt="plot_06_pairplot" src="https://github.com/user-attachments/assets/4bd2b8b3-b63c-4b46-8517-8d81ee761758" />


---

### Step 9 — Correlation Heatmap
> Checking if features are correlated. Low correlation between Income and Spending Score means each adds unique information — ideal for clustering.

<img width="1116" height="907" alt="plot_07_heatmap" src="https://github.com/user-attachments/assets/03afc1ec-602d-41db-b534-bbba3e64dd22" />


---

### Step 10 — Elbow Method (Annual Income only)
> Running K-Means for K=1 to K=10 on income alone. The bend in the curve tells us the optimal K.

<img width="913" height="691" alt="plot_08_elbow_income" src="https://github.com/user-attachments/assets/60f31f70-1e9e-42cc-8982-0e51fd0198df" />


---

### Step 11 — Elbow Method (Income + Spending Score)
> Same elbow analysis using both features. The curve bends at **K=5** — this is the optimal number of clusters. ✅

<img width="913" height="691" alt="plot_09_elbow_income_spending" src="https://github.com/user-attachments/assets/31248cc9-e45b-417c-b3e7-08167042e2bf" />


---

### Step 12 — Final K-Means Clusters (K=5) ⭐
> The main result. Each dot is a customer, color = cluster group, ★ = cluster centroid (center point).

<img width="1288" height="1029" alt="plot_10_clusters" src="https://github.com/user-attachments/assets/510c49fc-9bb7-430b-bd90-e4b41d8da8a4" />


---

## 🎯 Cluster Profiles & Business Strategy

| Cluster | Avg Income | Avg Spending | Profile | Recommended Strategy |
|---------|-----------|-------------|---------|----------------------|
| **Cluster 1** ⭐ | High ($86k) | High (82) | Premium Shoppers | **Priority target** — loyalty programs, exclusive offers |
| **Cluster 2** | Low ($26k) | High (79) | Enthusiastic Spenders | Sales events, budget-friendly premium products |
| **Cluster 0** | Medium ($55k) | Medium (50) | Average Customers | Retention campaigns, general promotions |
| **Cluster 3** | High ($88k) | Low (17) | Wealthy but Cautious | Time-limited offers, luxury positioning |
| **Cluster 4** | Low ($26k) | Low (21) | Budget Shoppers | Discount bundles, cost-effective campaigns |

> 💡 **Key Insight:** 54% of **Cluster 1** (highest-value) shoppers are **female** → marketing campaigns should prioritize female-oriented fashion and lifestyle products.

---

## 🧠 What I Learned

**1. Exploratory Data Analysis (EDA)**
Understanding data shape, distribution, and relationships before modelling using `displot`, `kdeplot`, `scatterplot`, `pairplot`, and `heatmap`.

**2. K-Means Clustering**
Unsupervised algorithm that groups data into K clusters by assigning each point to the nearest centroid, then recalculating centroids until convergence.

**3. The Elbow Method**
Objective way to choose K — plot inertia (WCSS) vs number of clusters and pick the point where improvement slows. Result: **K=5**.

**4. Feature Scaling (StandardScaler)**
Normalises features to mean=0, std=1 so no single variable dominates the distance calculations inside K-Means.

**5. Cluster Profiling**
After clustering, compute mean values and gender splits per cluster to translate math results into real business insights.

---

## 🔧 Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, manipulation, groupby analysis |
| `seaborn` | Statistical visualizations — KDE, pairplot, heatmap, scatter |
| `matplotlib` | Plot rendering and saving figures |
| `scikit-learn KMeans` | K-Means clustering algorithm |
| `scikit-learn StandardScaler` | Feature normalisation |
| `jupyter` | Interactive notebook environment |


## 📈 Results Summary

- ✅ Identified **5 distinct customer segments** from completely unlabelled data
- ✅ Used the **Elbow Method** to objectively validate K=5
- ✅ Cluster 1 (high income + high spending) = **primary marketing target**
- ✅ Gender analysis revealed **54% of top-value customers are female**
- ✅ Each cluster translated into a **clear, actionable business strategy**

---

## 🔗 Connect With Me

- 💼 **LinkedIn:** https://www.linkedin.com/in/ashok-gaihre-489a102bb 
- 🐙 **GitHub:** [ashokgaihrep18-dev](https://github.com/ashokgaihrep18-dev)


⭐ *Star this repo if it helped you!*

---

## 📄 License

This project is open source under the [MIT License](LICENSE).
