# 🛍️ Customer Segmentation Using K-Means Clustering

This project focuses on **segmenting customers** based on their **Annual Income** and **Spending Score**, using the **K-Means Clustering algorithm**. The goal is to group customers into meaningful clusters to help businesses **understand purchasing behavior** and enable **targeted marketing** strategies.

---

## 📁 Dataset

The dataset used is the **Mall Customer Segmentation Data** from Kaggle. It includes the following columns:

- `CustomerID`: Unique customer identifier  
- `Gender`: Male/Female  
- `Age`: Age of the customer  
- `Annual Income (k$)`: Annual income in thousand dollars  
- `Spending Score (1-100)`: Score assigned based on customer behavior  

🔗 [Dataset Source (Kaggle)](https://www.kaggle.com/vjchoudhary7/customer-segmentation-tutorial)

---

## 📌 Project Workflow

### 1. 📊 Exploratory Data Analysis (EDA)
- Visualized distributions of `Age`, `Annual Income`, and `Spending Score`
- Analyzed patterns and relationships to understand customer behavior

### 2. 🧹 Data Preprocessing
- Dropped `CustomerID` as it's non-informative for clustering
- Standardized numerical features using `StandardScaler`
- Selected features for clustering:
  - 2D: `Annual Income`, `Spending Score`
  - 3D: `Age`, `Annual Income`, `Spending Score`

> **Note:** The `Gender` column was not used in clustering because:
> - KMeans is distance-based and works best with numeric features.
> - Encoding categorical features like Gender can mislead distance-based clustering unless carefully processed (e.g., one-hot encoding + dimensionality adjustments).
> - The goal was to group customers based on **behavioral attributes**, not demographic identity.

### 3. 🔍 Finding Optimal Number of Clusters
- Used **Silhouette Score** to evaluate clustering quality for `k = 2 to 10`
- Validated results using the **Elbow Method** (WCSS)

### 4. 🤖 Final KMeans Clustering
- Applied KMeans with the best `k` value based on silhouette scores
- Cluster labels were assigned to each customer

### 5. 📈 Visualization
- Plotted clusters in **standardized feature space** and **original units**
- Displayed centroids for better interpretation

### 6. 🧠 Cluster Insights & Conclusion
- Analyzed mean Annual Income and Spending Score per cluster
- Interpreted segments like:
  - High-income high spenders
  - Low-income high spenders
  - Low-income low spenders, etc.

---

## 📊 Sample Output

**Cluster Summary:**

| Cluster | Avg. Income | Avg. Spending Score | Description                      |
|---------|-------------|---------------------|----------------------------------|
| 0       | $55.3k      | 49.5                | Mid-income average spenders      |
| 1       | $86.5k      | 82.1                | High-income, high spenders       |
| 2       | $25.7k      | 79.4                | Low-income, high spenders        |
| 3       | $88.2k      | 17.1                | High-income, low spenders        |
| 4       | $26.3k      | 20.9                | Low-income, low spenders         |

---

## 🧰 Tech Stack

- Python 3  
- Jupyter Notebook  
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
