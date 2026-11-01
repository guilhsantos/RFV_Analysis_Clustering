[🇧🇷 Português](README.md) · 🇺🇸 **English**

# Segmenting e-commerce purchases with K-Means

Clustering of more than 500,000 e-commerce purchase rows to separate buying profiles and propose a marketing action for each group.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/guilhsantos/RFV_Analysis_Clustering/blob/main/RFV_Analysis_Clustering.ipynb)

## Problem

Treating every customer the same wastes marketing budget. People who buy in bulk and people who buy a little at a higher price call for different approaches.

## Solution

Unsupervised clustering (K-Means) of purchases by **quantity**, **unit price**, and **total spent**, with the number of groups chosen by a metric instead of by eye.

## Result

The Silhouette Score (tested from 2 to 20 groups) pointed to **2 clusters**:

| Cluster | Rows | Avg. quantity | Avg. unit price | Avg. spend | Proposed action |
|---|---|---|---|---|---|
| **0 · High volume** | 7,444 | 50.8 units | 0.42 | 19.17 | loyalty program and exclusive discounts |
| **1 · Low volume** | 347,586 | 6.7 units | 2.77 | 11.43 | promotions that encourage bigger orders |

The main finding is a small group that buys many units of cheap items and spends more per purchase. That group deserves its own treatment.

## How I did it

1. **Exploration:** 541,909 rows, 135k without a customer ID, 5,268 duplicates, and negative prices and quantities (returns).
2. **Cleaning:** removed nulls, duplicates, and zero prices, and dropped spend outliers using the IQR.
3. **Features:** created total spend (`quantity × price`) and standardized with `StandardScaler`.
4. **Choosing k:** Silhouette Score from 2 to 20 groups on a 10% sample, with PCA for visualization.
5. **Reading the groups:** averages per cluster and marketing recommendations.

## Limitations and next steps

- The segmentation is **per purchase**, not per customer. The natural next step is to compute true RFV per customer (recency, frequency, and value) and cluster on that. The per-customer RFM calculation is in [Extracao_e_Tratamento_de_Dados_com_Python](https://github.com/guilhsantos/Extracao_e_Tratamento_de_Dados_com_Python).
- Try more groups using business criteria, not just the metric.

## Stack

Python · pandas · NumPy · scikit-learn (K-Means, PCA, Silhouette) · Plotly · Seaborn · Google Colab

---

Made by [Guilherme Santos](https://portifolio-guilherme-santos.vercel.app) · [LinkedIn](https://www.linkedin.com/in/guilherme-santos-dataeng)
