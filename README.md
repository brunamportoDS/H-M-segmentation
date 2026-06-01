#H & M Customer Segmentation

## Background: The 
H&M dataset contains 31 million transactions across over 1 million customers and more than 100,000 products. This project investigates what customers buy and their natural habits with no label and unsupervised learning. 

##Methods:
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

Notes:
 - Sample restricted to customers with more than 5 transactions.
 - Matrix Completion fails when compared to the column-mean baseline, likely due to the sparsity of the dataset.

## Libraries: 
Pandas, Numpy, Scikit-learn, Scipy, Matplotlib, Seaborn, ISLP. 
