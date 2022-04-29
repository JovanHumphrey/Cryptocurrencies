### Cryptocurrencies

## Project Overview

<p>Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they asked me to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.</p>

<p>The data I was given wasn't ideal, so it needed to be processed to fit the machine learning models. Since there is no known output for what my client is looking for, we chose to use unsupervised learning. To group the cryptocurrencies, I decided on a clustering algorithm. Then I used data visualizations to share my findings with the board.</p>

### Preprocessing Data for PCA

<p>I prepared the data by performing the following steps on the crypto DataFrame:</p>
•	Removed all cryptocurrencies that aren't being traded.
•	Removed the IsTrading column, (since the remaining row are all "True").
•	Removed all rows will at least one null value.
•	Removed all rows that don't have coins being mined.
•	Remove the CoinName column as that info isn't being used in the clustering algorithm. (However, I kept the index information.) 

<p>I created a DataFrame to store all cryptocurrency names.</p>
![Name](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable%201_CoinName.JPG)

<p>I then used the get_dummies method to create variables for Algorithim and ProofType, and stored in a new DataFrame. Lastly I took the features from that new DataFrame and standardized them using the StandardScaler fit_transform() function.</p>
![StandardScaler](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable%201_StandardScaler.JPG)

### Reducing Data Dimensions Using PCA

<p>With the data processed, I then used PCA to reduce the dimensions to three principal components, and then used the fit_transform function to scale the results.</p>
![PCA](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable%202_PCA.JPG)

### Clustering Cryptocurrencies Using K-means

<p>Using my knowledge of the K-means algorithm I created an elbow curve using hvplot to find the best value from my new DataFrame</p>
![Elbow](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_3_Elbow.JPG)

<p>Then I ran the K-means algorithm to predict the K clusters for the cryptocurrencies' data</p>
![Prediction](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_3_Prediction_Array.JPG)
![Cluster](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_3_Cluster.JPG)

## Results

<p>The last few steps required me to create a 3D-Scatter plot, print the total number of tradeable cryptocurrencies, create a new DataFrame that scaled the data from the cluster DataFrame index, and create an additional scatter plot using hvplott.scatter().</p>
![3D](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_4_3D_Scatter.JPG)
![532](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_4_532.JPG)
![tradeable](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_4_Tradable_Crypto.JPG)
![hvplot](https://github.com/JovanHumphrey/Cryptocurrencies/blob/main/images/Deliverable_4_hvplot.JPG)

## Summary

<p>The benefit of unsupervised learning is that it can find trends when the desired results are open-ended. In this situation my client wanted to be advised of the best cryptocurrency options in the dataset. In the end we identified 532 cryptocurrencies and clustered them into 4 classes. More research will be needed to determine the best options for my client's investment portfolio, but now they're equipped with trend information.</p>
