# Customer Segmentation Project

## Introduction
This project is about customer segmentation using unsupervised learning on online-retail dataset. In businesses, it is hard to understand their customers. This project applies unsupervised clustering techniques to identify distinct customer groups using purchasing data and attempts to understand their behaviour towards the online retail shop for future targeted marketing. This project also aims to determine which group generates what percentage of revenue, the total revenue each group generates, and the top 5 products that each group of customers buys the most.

## Dataset
The dataset that has been used is a transactional data which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers. The dataset has total number of 541,909 rows of transactions. Link to access the dataset is as follows:
https://archive.ics.uci.edu/dataset/352/online+retail.

## Results
K-means clsutering model with 4 cluster has been used that gives Silhouette score around 0.32. The following groups of registered customers are labeled by interpreting the centroids of each cluster:
  1. At-risk
  2. One-timers 
  3. Regulars
  4. VIP loyal customers

In the dataset of the online retail shop, possible churn (At-risk) of registered customers are about 30% of their total registered customers in the data and they are generating 21.68% of the revenue. Their loyal customers are the highest revenue generating customers, which is 67.84% of the total revenue from registered customer in the dataset. It will be a good investment in marketing toward these two groups. This business can retain around 90% of total revenue from registered customers by focusing only around 50% of their registered customers who bought from the online retail shop between the dataframe time period. The other two groups, regular and one-time buyers, contribute in-total around 10% of the total revenue from registered customers. 
Furthermore, I also try to find out the top 5 bought products by each group of customers. Which could be useful for marketing ideas.


## Methodology
### Feature Engineering
The clustering is done by using feature engineered features for each individual registered customers, therefore, it will be difficult to find out the correct recency of unregistered customers. The engineered features are called RFM (Recency, Frequency and Monetary). Recency is the days that have been passed between last day of purchase of a customer and a reference day. In this analysis the reference day is the next day of the last transaction of the dataset. Frequency is the number of transactions of each customer. Monetary is the total spending (generated revenue) of each customer between the time period of dataset. Furthermore, these data were highly skewed, therefore log-transformation have been used for clustering purpose.

### Clustering Algorithm
To determine the group of clusters, distance-based clustering algorithms (such as Agglomerative Hierarchical and K-means) are implemented. Agglomerative hierarchical clustering applies the Ward method for distance between two clusters and the Euclidean distance for dissimilarity measures between two observations to initiate the algorithm. The following defines these metrics:

**Euclidean Distance**\
Let's consider the $n \times p$ data matrix, where $n$ is the number of observed units and $p$ is the number of features; let's indicate with $i$ and $j$ two observations and with $x_{ih}$ the value of the $h$-th feature for the $i$-th object. If the observed variables are all quantative, each unit can be identified with a point in the $p$-dimensional space and the dissimilarity measure, Euclidean distance, between two objects $i$ and $j$ can be measured through:

$$d_{ij} = \sqrt{\sum_{h=1}^{p}(x_{ih}-x_{ij})^2}$$

**Ward Method**\
Distance between two clusters $C$ and $G$ is defined as the deviance between these two clusters. Let $x_{ihs}$ be the value of variable $h$ in cluster $s$. Then, 

$$E_s = \sum_{h=1}^{p}\sum_{i=1}^{n_s}(x_{ihs}-\bar{x}_{hs})^2$$

$E_s$ is the deviance within $s$-th cluster and $E = \sum_{s}E_s$ is the deviance within the whole partition. The algorithm looks for the merge that will imply the smallest incerase of the 'devince within' the whole partition.

### Model Selection
The clustering algorithm model is selected by using Silhouette Score, Inertia and by visualization method of hierarchical clustering.

**Silhouette Score**\
The following formula is used to calculate the silhouette score for each $i$-th data point:

$$S(i) = \frac{b(i)-a(i)}{max(a(i), b(i))}.$$

Here, 
  $b(i)$ = smallest average distance to points in a different cluster,
  $a(i)$ = average distance to other points in the same cluster.
The denonimator normalizes the difference so the silhouette score stays between $-1$ and $1$. Points score closer to $1$ implies well classified and closer to $-1$ implies the worst case.

**Inertia**\
The inertia formula for K-means clustering is the sum of squared distances between each data point and the centroid of the cluster it belongs to. Formally, it is expressed as:

$$Inertia = \sum_{h=1}^{k}\sum_{ \vec{x} \epsilon C_h} \left\lVert \vec{x} - \vec{\mu_h} \right\rVert^2 ,$$

here, 
  $C_h$ = set of points $h$-th clsuter,
  $\vec{x}$ = a vector of data point,
  $\vec{\mu_h}$ = the centroid of $h$-th cluster.


## Libraries
Pandas, Matplotlib, Seaborn, Numpy, Scikit-learn, Scipy.





















