# Crypto Clustering


## Data Processing and Normalizing

The data is imported and the "Coin ID" is set as index. A line plot is created to understand the price change percentage by different time periods to understand the basic trends. The the price change percentage value is normalized using the `StandardScalar` function to equalize feature scales, improve model performance and to deal with outlier robustness.

## Clustering

### K-Means Clustering

**Finding the Best Value for k Using the Original Data (Elbow Method)**

The elbow method is used to find the optimal value of k, the range of k is set from 1 to 11. This is a heuristic range is based on the instant where the inertia drops the greatest before creating an elbow shape. 

![Elbow Curve](Plots/Elbow%20Curve.png)

Based on the Elbow Curve Method, the best/optimal value of `k is 4` as the curve elbows at that instant.


**Clustering Cryptocurrencies with K-means Using the Original Data**

The K-means model is initialized using the best value of k which is 4. Using the `fit_predict` function the cryptocurrencies are grouped to predict the clusters. A scatter plot is created by setting the x to __"price_change_percentage_24h"__ and y to __"price_change_percentage_7d"__. 

![Crypto](Plots/Cryptocurrency%20Scatter%20Plot.png)


### K-Means Clustering using PCA

**Optimizing Clusters with Principal Component Analysis**

Principal Component Analysis (PCA) is used to reduce the features to three principal components.


**Finding the Best Value for k Using the PCA Data**

The elbow method is used to find the optimal value of k, the range of k is set from 1 to 11. The dataframe with the PCA components is used here.

![Elbow Curve](Plots/Elbow%20Curve%20Using%20PCA.png)

Based on the Elbow Curve Method, once again the best/optimal value of `k is 4` as the curve elbows at that instant.


**Clustering Cryptocurrencies with K-means Using the PCA Data**

The K-means model is initialized using the best value of k which is 4. Using the `fit_predict` function the cryptocurrencies are grouped to predict the clusters. A scatter plot is created by setting the x to __"PCA1"__ and y to __"PCA2"__, which are the first and second pincipal components  

![Crypto](Plots/Cryptocurrency%20Scatter%20Plot%20Using%20PCA.png)

## Comparison and Inference

While K-Means with PCA reduces the dimensionality of the data before clustering, which can help handle high-dimensional datasets and remove noise. By comparing the Cryptocurrency clusters it can be seen that the K-Means clustering with PCA is better clustered with lesser noise. Additionally, the dataset in question was not high-dimensional as the traditional K-Means operating on the original data, could still provide an effective clustering.