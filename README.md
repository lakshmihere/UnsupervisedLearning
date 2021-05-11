# UnsupervisedLearning

# 1. Credit Card Customer Segmentation Dataset: 
## Description 🔈

The dataset chosen for the current project is Credit Card Dataset from Kaggle. The link to the dataset is as follows, https://www.kaggle.com/arjunbhasin2013/ccdata. This case requires to develop a customer segmentation to define marketing strategy. The sample Dataset summarizes the usage behavior of about 9000 active credit card holders during the last 6 months. The file is at a customer level with 18 behavioral variables.

# 2. Attribute List: 

** The credit card dataset attributes for each customer as listed below. **

CUST_ID : Identification of Credit Card holder (Categorical)
BALANCE : Balance amount left in their account to make purchases
BALANCE_FREQUENCY : How frequently the Balance is updated, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated)
PURCHASES : Amount of purchases made from account
ONEOFF_PURCHASES : Maximum purchase amount done in one-go
INSTALLMENTS_PURCHASES : Amount of purchase done in installment
CASH_ADVANCE : Cash in advance given by the user
PURCHASES_FREQUENCY : How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased)
ONEOFFPURCHASESFREQUENCY : How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased)
PURCHASESINSTALLMENTSFREQUENCY : How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done)
CASHADVANCEFREQUENCY : How frequently the cash in advance being paid
CASHADVANCETRX : Number of Transactions made with "Cash in Advanced"
PURCHASES_TRX : Numbe of purchase transactions made
CREDIT_LIMIT : Limit of Credit Card for user
PAYMENTS : Amount of Payment done by user
MINIMUM_PAYMENTS : Minimum amount of payments made by user
PRCFULLPAYMENT : Percent of full payment paid by user
TENURE : Tenure of credit card service for user

# 3. Part I: Data Preprocessing 

Summary:

- All the relevant libraries for the project were imported and the data was read into the file
- A basic exploratory data analysis reveals the summary of the data along with the data types and the descriptive statistics
- Then we accounted for missing values.  Two columns had missing values and they were replaced with mean values
- One of the columns customer ID was removed from further analysis as there were no unique values
- Univariate analysis was conducted to understand the distribution of various attributes
- Obtained Correlation Heat Map to understand correlation of variables and also to extract some important features

# 4. Part II: Machine Learning

Summary:

- The data was first standardized.
- Application of Clustering Methods for Analysis
- Evaluation and Model Selection
- Visualization of Clusters
- Interpretation of Clusters

Models:

	(A). KMeans
        - The tuned hyperparameters for KMeans are n_clusters = 3, n_init=1000, max_iter=400, init='k-means++’
        - The silhouette score Kmeans is 0.2509
	(B). Agglomerative Hierarchical
        - The tuned hyperparameters for Agglomerative Clustering are n_clusters = 3, affinity='euclidean’, linkage="ward"
        - The silhouette score Agglomerative Clustering is 0.1731
	(C). DBSCAN
        - The tuned hyperparameters for DBSCAN are eps=4, metric="euclidean", and min_samples=3
        - The silhouette score DBSCAN is 0.6239
	(D). Gaussian Mixture
        - The tuned hyperparameters for Gaussian Mixture Models are n_clusters = 3, affinity='euclidean’, linkage="ward"
        - The silhouette score Gaussian Mixture Models is 0.1657

Final Model Selection for dataset:

- For the final selection of models, we compared the silhouette scores of all the models
- From the silhouette scores, DBSCAN is the best model but PCA reveals a different story. DBSCAN clusters are 
not distinct and most values are clustered as noise. 
- KMeans is the dest model for the current dataset

# 5. Conclusions:
 
- In this project, we have performed data preprocessing, feature extraction with PCA, looked at various clustering metrics (inertias, silhouette scores), experimented with various Clustering algorithms (KMeans Clustering, Agglomerative Hierarchical Clustering, DBSCAN Clustering, and Gaussian Mixture Clustering), data visualizations.
- In this dataset we have segmented the customers into three smaller groups: the Active Users, the Cautious Spenders, and the Average Joe.

# 6. Future Goals:

- Advanced data preparation: Building an enriched customer profile by deriving “intelligent” KPIs like limit usage(balance to credit limit ratio), average amount per purchase can be used for to improve accuracies.
- Using dimensionality reduction not just for visualization but actual reduction of features could potentially improve the cluster analysis and hence the accuracy associated.