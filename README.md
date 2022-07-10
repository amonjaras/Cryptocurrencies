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

### **Deliverable 2: Reducing Data Dimensions Using PCA**

By using the SKLearn KMeans, we were able to produce an elbow curve that shows the value of `4` that will serve best as the K value for the model. See Fig 1:

> *Fig 1: Elbow plot*

![elbow](https://github.com/amonjaras/Cryptocurrencies/blob/main/Images/elbow.png)


[:top: Go To Top](#index)


This work belongs to [^1].
Course [^2].
[^note]:
[^1]: Author: Audrey MONJARAS :mexico: :panama: :canada:
[^2]: Data Analytics: Unit 18 UML
