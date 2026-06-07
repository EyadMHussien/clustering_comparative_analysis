# 📊 Wholesale Customer Segmentation: A Comparative Clustering Analysis

## 🎯 Overview
This project presents a comparative analysis of different unsupervised machine learning algorithms for customer segmentation. The goal is to group wholesale customers based on their annual spending across various product categories, identifying distinct purchasing profiles to drive targeted business strategies.

## 📂 Dataset
* **Source**: The project uses the `Wholesale customers data.csv` dataset.
* **Structure**: The data consists of 440 customer samples and 8 features.
* **Features**: Features include categorical identifiers (`Channel`, `Region`) and continuous spending data on product categories: `Fresh`, `Milk`, `Grocery`, `Frozen`, `Detergents_Paper`, and `Delicassen`.

## 🛠️ Data Preprocessing & Exploratory Data Analysis (EDA)
To ensure the clustering algorithms perform optimally, the following preprocessing steps are applied:
* **Data Cleaning**: The dataset was verified to have no missing values or exact duplicate rows.
* **Feature Scaling**: Applied Z-score normalization using `StandardScaler` to ensure features with larger numerical ranges do not dominate the distance calculations.
* **Outlier Detection**: Box plots were generated for each scaled numerical feature to visually detect potential outliers.
* **Dimensionality Reduction**: Utilized both Principal Component Analysis (PCA) and t-Distributed Stochastic Neighbor Embedding (t-SNE) to project the multi-dimensional data into 2D spaces for visual exploration of non-linear clustering patterns.

## 🧠 Clustering Algorithms Evaluated
The notebook implements and compares three distinct clustering paradigms, evaluated at $K=2$, $K=3$, and $K=4$ clusters:
1. **K-Means Clustering**: A centroid-based algorithm that partitions data into $K$ distinct clusters.
2. **Spectral Clustering**: A technique that uses the eigenvalues of a similarity matrix to perform dimensionality reduction before clustering in fewer dimensions.
3. **Gaussian Mixture Model (GMM)**: A probabilistic model that assumes data points are generated from a mixture of Gaussian distributions, providing soft assignments (probabilities) rather than hard boundaries.

## 📈 Evaluation Metrics
To objectively compare the performance of each algorithm, the following mathematical metrics were used:
* **Silhouette Score**: Measures how similar an object is to its own cluster compared to other clusters.
* **Davies-Bouldin Index (DBI)**: Evaluates intra-cluster similarity and inter-cluster differences (lower is better).
* **Calinski-Harabasz Score (CHS)**: Also known as the Variance Ratio Criterion, measuring the ratio of between-cluster dispersion to within-cluster dispersion (higher is better).

## 💡 Cluster Profiling & Insights
Beyond purely mathematical metrics, the analysis calculates the average feature values per cluster to establish qualitative customer profiles. This helps translate the clusters into real-world characteristics, such as separating "small fresh produce buyers" from "large frozen and detergents buyers".
