# **Cryptocurrencies**
Unsupervised Machine Learning

## **Index**

- [Overview](#overview)

- [Resources](#resources)

- [Results](#results)

- [Summary](#summary)

[:top: Go To Top](#index)

## **Overview**

Research was done teaming up with Martha. We understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. Now it’s time to put all these skills to use by creating an analysis for our clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the **Advisory Services Team** at **Accountability Accounting**, one of our most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data we will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what we are looking for, we have decided to use unsupervised learning. To group the cryptocurrencies, we decided on a clustering algorithm. W’ll use data visualizations to share our findings with the board.

[:top: Go To Top](#index)

## **Resources**
### **Data**

- [Cryptocurrency dataset](https://github.com/amonjaras/Cryptocurrencies/blob/main/M18_Challenge/Resources/crypto_data.csv)

### **Tools**

- Jupyter Notebook
- Python

[:top: Go To Top](#index)

## **Results**

✅ **[Deliverable 1 to 4](https://github.com/amonjaras/Cryptocurrencies/blob/main/M18_Challenge/crypto_clustering.ipynb)**

### **Deliverable 1: Processing the Data for PCA**

We started our dataset with 1,252 cryptocurrencies, using pandas we were able to:

- Keep all the cryptocurrencies that are being traded
- Keep the crypto with a working algorithm
- Remove the `IsTrading` column
- Remove rows with at least 1 null value
- Keep the rows where coins are mined

After all this process we were able to reduce the dataset to 532 tradable cryptocurrencies. After this process, we were able to standardize the data by using the following code:

```
x_scaled = StandardScaler().fit_transform(x)
x_scaled[:5]
```

[:top: Go To Top](#index)

### **Deliverable 2: Reducing Data Dimensions Using PCA**

We were able to reduce dimensions to three principal components and transform the data. Also we were able to create a dataframe to store our components as per the following code:

```
pcs_df = pd.DataFrame(data = crypto_pca, 
                     columns = ["PC1", "PC2", "PC3"], index = x.index)
print(pcs_df.shape)
pcs_df.head(10)
```


[:top: Go To Top](#index)

### **Deliverable 3: Clustering Cryptocurrencies Using K-Means

By using the SKLearn KMeans, we were able to produce an elbow curve that shows the value of `4` that will serve best as the K value for the model. See Fig 1:

> *Fig 1: Elbow curve*

![elbow](https://github.com/amonjaras/Cryptocurrencies/blob/main/Images/elbow.png)


With our K value we were able to obtain our clusters predictions. Additional to the predictions we created a combined dataset of the filtered data with the scaled and cluster for visualization purposes

[:top: Go To Top](#index)

### **Deliverable 4: Visualizing Cryptocurrencies Results**

With the combined data we create a 3D plottly express scatter plot showing the clusters with markers identifying `CoinName` and `Algorithm`. See Fig 2

> *Fig 2: 3D scatter plot*

![3dscatter](https://github.com/amonjaras/Cryptocurrencies/blob/main/Images/3dscatter.png)

Using all the information, we created an hvplot table containing `CoinName`, `Algorithm`, `ProofType`, `TotalCoinSupply`, `TotalCoinsMided` and `Class`. This data set can be used for additional analysis and visualizations by the clusters. The Fig 3 shows the hvplot

> *Fig 3: hvplot scatter plot*

![hvplot](https://github.com/amonjaras/Cryptocurrencies/blob/main/Images/hvplot.png)

[:top: Go To Top](#index)


## **Summary**

We have identified the classification of 532 cryptocurrencies based on similarities of their features.
It is importat to mention that majority of the cryptocurrencies can be grouped in two classes (0 and 3 as per scatter plots), this information will be key for the **Advisory Services Team** at **Accountability Accounting**

[:top: Go To Top](#index)

This work belongs to [^1].
Course [^2].
[^note]:
[^1]: Author: Audrey MONJARAS :mexico: :panama: :canada:
[^2]: Data Analytics: Unit 18 UML
