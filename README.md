# Customer-Segmentation-Project

## Introduction
This project is about customer segmentation using unsupervised learning on online-retail dataset. In businesses, it is hard to understand their customers. This project applies unsupervised clustering techniques to identify distinct customer groups using purchasing data and attempts to understand their behaviour towards the online retail shop for future targeted marketing. This project also aims to determine which group generates what percentage of revenue, the total revenue each group generates, and the top 5 products that each group of customers buys the most.

## Dataset
The dataset that has been used is a transactional data which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers. The dataset has total number of 541,909 rows of transactions. Link to access the dataset is as follows:
https://archive.ics.uci.edu/dataset/352/online+retail.

## Methodology
The clustering is done by using feature engineered features for each individual registered customers, therefore, it will be difficult to find out the correct recency of unregistered customers. The engineered features are called RFM (Recency, Frequency and Monetary). Recency is the days that have been passed between last day of purchase of a customer and a reference day. In this analysis the reference day is the next day of the last transaction of the dataset. Frequency is the number of transactions of each customer. Monetary is the total spending (generated revenue) of each customer between the time period of dataset. Furthermore, these data were highly skewed, therefore log-transformation have been used for clustering purpose.

To determine the group of clusters, distance-based clustering algorithms (such as Agglomerative Hierarchical and K-means) are implemented. Agglomerative hierarchical clustering applies the Ward method for distance between two clusters and the Euclidean distance for dissimilarity measures between two observations. The following defines these metrics:

** Euclidean Distance **
Let's consider the $n x p$ data matrix, where $n$ is the number of observed units and $p$ is the number of features; let's indicate with $i$ and $j$ two observations and with $x_{ih}$ the value of the $h$-th feature for the $i$-th object.

