#H & M Customer Segmentation

# H&M Customer Segmentation

Unsupervised customer segmentation of H&M shoppers using PCA, SVD, matrix completion, k-means, and hierarchical clustering. The analysis discovers four interpretable customer types from purchase behavior and product preferences.

## The question

Given a transaction log of millions of purchases and no labels telling us who is who, can we find natural groups of customers based on how they shop and what they buy?

## Dataset

We use H&M's [Personalized Fashion Recommendations dataset](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations) from Kaggle (2022). It contains roughly 31 million transactions across 1.37 million customers and 105,000 products over a two-year window (September 2018 to September 2020).

To keep the analysis computationally manageable, we sample 10,000 customers who each had at least five transactions during the window. We verify that the sample is statistically indistinguishable from the eligible population on age, transaction count, and club membership. 

## Methods:
- PCA: reduce 14 behavioral features to interpretable axes.
- SVD: factorize a customer with a product-category-matrix to latent preference factors.
- Matrix Completion: estimate unobserved purchase affinities by applying iterative low-rank approximation.
- K-means: partition customers into segments (k = 4 selected with WCSS + silhouette)
- Hierarchical clustering: complete and ward linkage for comparisons.

## Result: 
|Cluster| Size| Description|
|---|---|---|
|1|2,347|Low-engagement, divided skew|
|2|4,014| High-value customers-higher frequencies, spends, and varieties|
|3|302| Inactive Children speclists|
|4|3,312|Occasional ladieswear shoppers|

K-means silhouette produces 0.21- Ward hierarchical replicates the same structure at 0.16.

Four customer segments emerged consistently across methods:
- **High-value active women's fashion shoppers**: heavy buyers with broad product variety
- **Occasional women's fashion shoppers**: Ladieswear-focused but lower engagement
- **Occasional Divided trend shoppers**: younger, trend-oriented buyers concentrated in the Divided line
- **Inactive parents**: low-frequency shoppers buying primarily in Baby/Children categories

The segmentation has a two-layer structure: product composition separates specialist minorities from the womenswear majority, and engagement subdivides what remains.

Notes:
 - Sample restricted to customers with more than 5 transactions.
 - Matrix Completion fails when compared to the column-mean baseline, likely due to the sparsity of the dataset.

## Libraries: 
Pandas, Numpy, Scikit-learn, Scipy, Matplotlib, Seaborn, ISLP. 

## Contributors
Bruna Porto
Helen Liu
Devlin Hoang
