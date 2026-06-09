# Customer Segmentation Using Unsupervised Learning

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-KMeans-green?style=flat&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

---

## Task Objective

A retail mall wants to understand its diverse customer base and run **targeted marketing campaigns** instead of treating every customer the same. The objective is to use unsupervised machine learning to discover natural customer groups based on spending behavior and income, then design specific marketing strategies for each segment.

---

## Approach

### 1. Data Loading & Description
- Loaded the Mall Customers Dataset (200 samples, 5 features)
- Features: CustomerID, Gender, Age, Annual Income (k$), Spending Score (1–100)
- No missing values found

### 2. Data Cleaning & Preprocessing
- Dropped non-predictive `CustomerID` column
- Label encoded `Gender` (Female=1, Male=0)
- Applied `StandardScaler` to normalize features before clustering

### 3. Exploratory Data Analysis (EDA)
- Distribution plots for Age, Annual Income, and Spending Score
- Scatter plot of Income vs Spending Score colored by Gender
- Correlation heatmap to understand feature relationships

### 4. K-Means Clustering
- **Elbow Method:** Plotted Within-Cluster Sum of Squares (WCSS) for K=2 to K=10
- **Silhouette Score:** Computed for each K to validate cluster quality
- Selected **K=5** as the optimal number of clusters based on the elbow curve and silhouette analysis
- Applied final K-Means model and assigned cluster labels

### 5. PCA Visualization
- Reduced all features to 2 principal components using PCA
- Explained **cumulative variance** reported per component
- Plotted cluster separation in 2D PCA space

### 6. t-SNE Visualization
- Applied t-SNE (perplexity=30, 1000 iterations) to non-linearly project the data to 2D
- Validated that clusters are well-separated even in non-linear space

### 7. Marketing Strategy Development
- Profiled each cluster by mean Income, Spending Score, and Age
- Proposed targeted marketing tactics for each segment

---

## Results & Insights

### Cluster Profiles & Marketing Strategies

| Cluster | Profile | Marketing Strategy |
|---------|---------|-------------------|
| 0 | Low Income, Low Spend | Budget deals, coupons, value bundles |
| 1 | High Income, Low Spend | Premium/exclusive products, VIP access |
| 2 | Mid Income, Mid Spend | Cross-sell, personalized email, loyalty points |
| 3 | Low Income, High Spend | Flash sales, buy-now-pay-later, trending items |
| 4 | High Income, High Spend ⭐ | Max budget here — VIP concierge, early access |

### Key Findings

1. **5 distinct segments** were identified with high silhouette scores, confirming meaningful cluster separation.

2. **Cluster 4 (High Income, High Spend)** is the most valuable customer group — highest purchase potential and willingness to spend. Maximum marketing investment should target this segment.

3. **Cluster 3 (Low Income, High Spend)** represents impulsive buyers — flash sales, limited-time offers, and BNPL payment options resonate most with this group.

4. **PCA and t-SNE** both confirmed well-separated clusters, validating the K=5 choice and proving customers genuinely fall into distinct behavioral groups.

5. **Gender has minimal impact** on clustering — Income and Spending Score are far more predictive of shopping behavior than demographics.

---

## Dataset

| Property | Value |
|----------|-------|
| Source | Kaggle — Mall Customers Dataset |
| Link | https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python |
| Rows | 200 |
| Columns | 5 |
| Notebook Fallback | Synthetic dataset auto-generated if URL fails |

---

## Libraries Used

`pandas` `numpy` `matplotlib` `seaborn` `scikit-learn` (KMeans, PCA, TSNE, silhouette_score)

## How to Run

1. Open `Task2_Customer_Segmentation.ipynb` in Google Colab
2. Click **Runtime → Run All**
3. Dataset auto-downloads from public mirror; synthetic fallback activates if unavailable
