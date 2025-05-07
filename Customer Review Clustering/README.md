# Customer Review Clustering of Amazon Sales Dataset

## Project Overview

This project applies unsupervised learning techniques—**K-Means**, **Hierarchical Clustering**, and **Gaussian Mixture Model (GMM)**—to analyze customer reviews from an Amazon sales dataset. The goal is to uncover hidden patterns, identify themes across product categories, and gain insights that can guide marketing strategies and product improvements.

## Objectives

- Discover inherent groupings in customer reviews.
- Understand review patterns across product categories.
- Compare performance of different clustering techniques.
- Interpret cluster themes for actionable business strategies.

## Dataset

- **Source**: Amazon sales reviews dataset (1,212 cleaned entries)
- **Main fields**:
  - `category`
  - `discounted_price`
  - `review_content`

### Preprocessing Steps

- Text cleaning: removal of noise (punctuation, numbers, HTML, etc.)
- Tokenization and lemmatization
- TF-IDF vectorization
- Dimensionality reduction using **PCA** (2 components)

## Methodology

| Step                  | Description |
|-----------------------|-------------|
| Text Preprocessing    | Normalize and clean textual data. |
| Feature Extraction    | TF-IDF vectorization of review content. |
| Dimensionality Reduction | Apply PCA for 2D clustering visualization. |
| Clustering Algorithms | K-Means, Hierarchical Clustering, GMM. |
| Evaluation Metric     | Silhouette Score to assess clustering quality. |

## 📊 Results

| Model        | No. of Clusters | Silhouette Score |
|--------------|------------------|------------------|
| K-Means      | 3                | **0.5773**       |
| Hierarchical | 3                | 0.5543           |
| GMM          | 3                | 0.4923           |

- **K-Means** delivered the best cluster separation and cohesion.
- All models consistently identified **3 optimal clusters**, indicating stable underlying patterns.

## Cluster Analysis

### K-Means Insights:
- **Cluster 0**: Focus on laptop purchases (keywords: size, worth, purchase)
- **Cluster 1**: Feature-heavy reviews on Bluetooth, earphones, TVs
- **Cluster 2**: Mentions of Apple/Samsung, cables, durability

### Hierarchical Clustering:
- Clusters aligned with product categories:
  - **Cluster 0**: Computers & Accessories
  - **Cluster 1**: Home & Kitchen
  - **Cluster 2**: Electronics
- Marketing suggestions were tailored to each cluster based on themes.

### GMM:
- Offers soft clustering (probabilistic assignment).
- Visualizes customer spending patterns within each cluster.
- Highlights flexibility in cluster shape interpretation.

## 📷 Suggested Visual Snippets

You may include up to 10 visuals in the GitHub README. Here are the most informative:

1. **Category Distribution** (bar plot)
2. **Review Length Distribution** (histogram)
3. **Word Cloud** of frequent terms
4. **Elbow & Silhouette Graphs** for K-Means
5. **K-Means Cluster Visualization (2D PCA)**
6. **Silhouette Plot for K-Means**
7. **Hierarchical Dendrogram**
8. **Hierarchical Cluster Assignment Plot**
9. **Cluster-wise Review Themes Table**
10. **GMM Cluster Plot with Probabilities**

## Conclusion

This project demonstrates the power of clustering in text mining, allowing Amazon to segment reviews without labeled data. The findings can support:
- Product-specific sentiment analysis
- Better-targeted marketing strategies
- Data-driven decision-making

By combining TF-IDF with dimensionality reduction and clustering algorithms, this analysis reveals nuanced patterns in customer behavior and feedback.
