# Cryptocurrencies
Unsupervised Machine Learning database- cryptocurrencies
by Monica Holmes 
06/20/21

# **CRYPTOCURRENCIES ANALYSIS**
## **PURPOSE**
The purpose of this repository is to utilize unsupervised Machine Learning, Jupyter, and Pandas to process unstructured data, cluster the data, reduce dimensions and reduced the principal components using principal component analysis (PCA).

This analysis will be used for clients who are preparing to get into the cryptocurrency market. One client is interested in offering a new cryptocurrency investment portfolio for its customers; however, the company is lost in the vast universe of cryptocurrencies. This report includes what cryptocurrencies are on the trading market and how they may be grouped to create a classifications system for this new investment. This analysis will also provide visualizations of my findings.

![image](https://user-images.githubusercontent.com/78371845/123480846-f11c2700-d5d0-11eb-99b3-23c079d3124f.png)


The IsTrading column is dropped.
![image](https://user-images.githubusercontent.com/78371845/123480935-0abd6e80-d5d1-11eb-84ae-aecf1d3d0530.png)


All the rows that have at least one null value are removed.
![image](https://user-images.githubusercontent.com/78371845/123481164-596b0880-d5d1-11eb-8f2c-92bbd6584fc8.png)


The CoinName column is dropped.
![image](https://user-images.githubusercontent.com/78371845/123481500-d26a6000-d5d1-11eb-9f55-c49145773979.png)



All the rows that do not have coins being mined are removed.
 ![image](https://user-images.githubusercontent.com/78371845/123481290-87504d00-d5d1-11eb-8115-bda11bf7a715.png)


A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame.
![image](https://user-images.githubusercontent.com/78371845/123481396-a949cf80-d5d1-11eb-8248-cb6e19ea7773.png)


The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X.
![image](https://user-images.githubusercontent.com/78371845/123481553-e615c680-d5d1-11eb-9282-af9cc7f24038.png)


The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function.
![image](https://user-images.githubusercontent.com/78371845/123481589-f5950f80-d5d1-11eb-9718-ace295d63ae7.png)


The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components. 
![image](https://user-images.githubusercontent.com/78371845/123481661-0d6c9380-d5d2-11eb-8898-bcb28974720d.png)


The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame.
![image](https://user-images.githubusercontent.com/78371845/123481715-21b09080-d5d2-11eb-9110-d7bf605c620d.png)


An elbow curve is created using hvPlot to find the best value for K. 
![image](https://user-images.githubusercontent.com/78371845/123481767-2ffeac80-d5d2-11eb-81ce-508860ea29f6.png)

![image](https://user-images.githubusercontent.com/78371845/123481805-38ef7e00-d5d2-11eb-9f73-245eefacbaeb.png)


Predictions are made on the K clusters of the cryptocurrencies’ data.
![image](https://user-images.githubusercontent.com/78371845/123481830-46a50380-d5d2-11eb-8ec7-aab342a0eccb.png)

![image](https://user-images.githubusercontent.com/78371845/123481855-51f82f00-d5d2-11eb-8505-aba0d4a57f02.png)


A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class.
![image](https://user-images.githubusercontent.com/78371845/123481950-76eca200-d5d2-11eb-8e84-7aa1063008cf.png)


The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover.
![image](https://user-images.githubusercontent.com/78371845/123482000-8a980880-d5d2-11eb-9a2c-8826e39ca0b2.png)


A table with tradable cryptocurrencies is created using the hvplot.table() function.
![image](https://user-images.githubusercontent.com/78371845/123482030-98e62480-d5d2-11eb-9b35-dc98a6ec5104.png)


The total number of tradable cryptocurrencies is printed.
![image](https://user-images.githubusercontent.com/78371845/123482072-ab605e00-d5d2-11eb-989b-a31f6a3cef7f.png)


A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns.
![image](https://user-images.githubusercontent.com/78371845/123482101-b915e380-d5d2-11eb-93a9-558318c04e3d.png)


A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point.
![image](https://user-images.githubusercontent.com/78371845/123482142-c8952c80-d5d2-11eb-8249-22655f2bc5c0.png)

