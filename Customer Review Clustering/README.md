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
![image](https://github.com/user-attachments/assets/aa7e6c27-2c8e-4be0-bd00-4838d77595c2)
![image](https://github.com/user-attachments/assets/7f1d302e-5403-4ee2-abf2-2b098159dc6a)
![image](https://github.com/user-attachments/assets/c814e96b-d9ee-468d-9b90-ac9d22088ff2)


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

![image](https://github.com/user-attachments/assets/c49f2509-adcd-48bb-86f0-3e17040d4a0f)
K-Means Clustering

![image](https://github.com/user-attachments/assets/898737d6-412d-4534-9b3c-62dd591785dd)
Hierarchical Clustering

![image](https://github.com/user-attachments/assets/2dde0754-d18b-45a6-99bb-c357851ad0ab)
Gaussian Mixture Model (GMM)

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

## Conclusion

This project demonstrates the power of clustering in text mining, allowing Amazon to segment reviews without labeled data. The findings can support:
- Product-specific sentiment analysis
- Better-targeted marketing strategies
- Data-driven decision-making

By combining TF-IDF with dimensionality reduction and clustering algorithms, this analysis reveals nuanced patterns in customer behavior and feedback.
