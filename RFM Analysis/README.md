# Customer Segmentation using RFM Analysis

This project applies RFM (Recency, Frequency, Monetary) analysis to segment customers based on their purchasing behavior using an online retail dataset. The goal is to help businesses identify key customer groups for targeted marketing strategies.

## 🔍 Objective

- Clean and preprocess customer transaction data.
- Calculate RFM metrics for each customer.
- Segment customers using K-Means clustering.
- Visualize and interpret customer segments to support business decisions.

## 📊 Dataset

The dataset includes transaction-level data from an online retail store. It contains customer IDs, invoice dates, purchase amounts, and item quantities.

> Note: 23% of the data was removed during the cleaning process due to illogical or missing values.

## 🧹 Data Cleaning

- Removed duplicates and missing customer IDs.
- Handled illogical values (e.g., negative quantities or amounts).
- Dropped outliers in a separate version of the dataset for comparison.

## 📈 RFM Metrics

For each customer:
- **Recency**: Days since last purchase.
- **Frequency**: Number of transactions.
- **Monetary**: Total spending amount.

## 🤖 Clustering Approach

- Applied **K-Means clustering** with `K=3`.
- Performed clustering on:
  - The full dataset.
  - A cleaned dataset with outliers removed.
- Chose the optimal `K` based on the elbow method and silhouette score.

## 🧠 Cluster Interpretation

From the 3D visualization of the RFM clusters:

- **Cluster 0 – High-Value Loyalists**: Recent, frequent buyers with high spending.
- **Cluster 1 – New or Low-Value Customers**: Infrequent and low-spending.
- **Cluster 2 – Dormant or Churned Customers**: Old inactive customers with low frequency and value.

## 📌 Tools & Libraries

- **Languages**: Python  
- **Libraries**: Pandas, NumPy, Matplotlib, Seabo

