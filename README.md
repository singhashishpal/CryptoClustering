# CryptoClustering
Repo for CryptoClustering challenge


This module analyzes and clusters a dataset of cryptocurrencies based on price change percentages over different timeframes. Using K-means clustering, Principal Component Analysis (PCA), and the elbow method, this project aims to find optimal clusters for understanding cryptocurrency behavior.

## Module Steps

### 1. **Data Normalization**

* **Standardization** : The data from the CSV file is normalized using standard scaller from scikit learn
* **DataFrame Creation** : A new DataFrame is created with the scaled data, and the original coin id  index is retained for easier cryptocurrency identification.

### 2. Finding the Best Value for k

* **Elbow Method** : To determine the optimal number of clusters k
* Create a list of k  values ranging from 1 to 11.
* Used a loop to compute the inertia for each `k` and store it in a list.
* Plot the inertia values as an elbow curve.
* Identify the optimal k  by examining the point at which the inertia begins to decrease slowly (the “elbow”).

### 3. **Clustering Cryptocurrencies Using the Scaled DataFrame**

* **K-means Initialization** : Initialize and fit a K-means model using the optimal `k` value from the elbow method.
* **Predict Clusters** : Group cryptocurrencies by predicting clusters on the scaled data.
* **Data Augmentation** : Copy the scaled DataFrame and add a new column for the predicted cluster labels.
* **Scatter Plot Visualization:** plot a scatter plot by using hvplot.

### 4. **Optimizing Clusters with Principal Component Analysis (PCA)**

* **PCA Reduction** : Reduce features to three principal components to simplify clustering.
* **PCA DataFrame Creation** : Create a new DataFrame using the three principal components, keeping coin id as the index.

### 5. **Finding the Best k with PCA DataFrame**

* **Elbow Method on PCA** :
* Repeat the elbow method using the scaled PCA DataFrame to find the best k value.
* **Comparison** : Determine if the optimal k  differs from the original scaled DataFrame.

### 6. **Clustering with K-means Using PCA DataFrame**

* **K-means Model** : Initialize K-means with the best k for the PCA data.
* **Cluster Prediction** : Fit and predict clusters using the PCA DataFrame.
* **Data Augmentation** : Copy the PCA DataFrame, adding a column for predicted clusters.
* **PCA Scatter Plot** : scatter plot was plotted 

## Conclusion

This project provides insights into clustering cryptocurrencies based on price changes across different time periods and evaluates the effect of dimensionality reduction with PCA. By reducing the feature set, the analysis can still capture the majority of the dataset's information, potentially simplifying the clustering process with minimal information loss.

***Reference: class recordings* **