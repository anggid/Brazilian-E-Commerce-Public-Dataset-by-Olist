# Final Project - Customer Segmentation Using KMeans Clustering based on RFM (Recency, Frequency, Monetary)Analytics
Contributor:
- Anggi Dwifiani
- Muhamad Faroja Sa'dan
- Triyoga Tyas Utama

This notebook is about customer segmentation of Olist, which is a Brazilian e-commerce. The data is from a public dataset accessed through [Kaggle](https://www.kaggle.com/olistbr/brazilian-ecommerce).

# Background
E-commerce is a business model that allows companies or individuals to buy or sell goods via the internet. E-commerce customers have unimaginable variety personalities, a potential market is usually not characterized singularly nor easily. It becomes important to know your target customer base in order to make sure your communications are both effective (attractive, action-promoting) and appropriate (non-offensive, timely, and relevant).[1]  RFM analysis is a customer behavior segmentation technique. Based on customers' historical transactions, RFM analysis focuses on 3 main aspects of customers' transactions: recency, frequency and purchase amount. Understanding these behaviors will allow businesses to cluster different customers into groups.[2]

# Problem Identification
## 1. Problem Definition
Customers visit eCommerce sites to accomplish a goal. The goal can be simple (for example
buying a coffee machine) or complex (such as fixing a hole in the wall). Complex goals typically
involve a combination of several simple goals. Goals manifest themselves through user behavior,
such as search queries, clicks, page views, and purchases. By analyzing user behavior, we can infer
common strategies that users follow to achieve a goal. At the most granular level, user behavior
manifests itself as search queries and interactions.<sup>[3]<sup>

The problem is from data we haven't yet calculated the RFM value, to make the data analysis clear we need to further analyze the RFM value and divide the customer into segments based on RFM Analytics.
## 2. Business Objectives
Based on the available dataset, we found that  we can use RFM analytics for development of olist e-commerce is to find out the habits of each customer segment. The customer segmentation that will be generated by this project will later be able to help the olist to implement advertising / marketing strategies for each segment.
The expectation in this machine learning project is to create an algorithm based on RFM analytic for  customer grouping so that it can help olist know the characteristics of olist users.
The main goal of this project is to help meet the expectations of the algorithm to be created for the grouping of each user segment through the following objectives:

◉ Group customers based on their behavior so that they are divided into several segments based on RFM Analytics.

◉ Find out the defining characteristics in each customer segment

With these two objectives, it can help the Olist business team in finding marketing / advertising strategies based on the type or characteristics of each clusters that we formed.


## 3. Data Requirements
We want to segment our customer by RFM analytics and find out the defining characteristics of each group, so we need to determine the RFM value to make the segmentation.

## 4. Analytic Approach
### a. Domain Knowledge Techniques
After determine the Rencency, Frequency, and Monetary value for each customer, we segmen customers based on quantile value of Monetary and Recency, but frequency we used elbow method for relevancy.
### b. Machine Learning Techniques
We using KMeans method after determine the Recency,Frequency and Monetary value for each customer, then we apply customer segmentation. For comparison we also use DBScan but the different is for DBScan we only use 
more or less 10%.Each of segment will represent how customer behavior based on RFM analytics.



### b. Risk
Because customer segmentation is usually used to do targeted marketing, the risk of falsely predicting the customer groups are:
- Marketing budget loss
- Innacurate target advertisement
- Irrelevant customer segmentation

The aftermath false targeted marketing, is that future increase in sales is lost.

### c. Performance Measure
The performance measures used to evaluate the ML model are  silhouette score for KMeans and for DBScan Is noise, epsilon, & min samples.

## 5. Action
The business user can use the segmentation result to further understand the customers, and to do better marketing or promotions to the customers so that they can increase revenue.

## 6. Value
This project will save some marketing costs because now the business user is able to do marketing to only certain groups of customers that have the highest chance of buying the products, rather than marketing to all customers that may not be interested in the product at all. This can also increase customer engagement rate because each customer can feel the personalization from the business.


# Data Understanding and Data Preparation
We started by importing the needed dataset. Then we analyzed each columns, created new features where needed, and converted the formats of some features to a more usable format. After that we merged some of the tables into one analytics base table. This table is then used for EDA, handling missing data points, and choosing relevant features to be used for modelling.
We are generating some new features, including RFM, which stands for Recency, Frequency, and Monetary value. Recency is the interval of time between the latest customer purchase and the present, frequency refers to the customers’ buying frequency, and monetary value represents the total customers’ consumption of money.
# Modeling
With domain knowledge clusters we make it 4 clusters based on their RFM score value, each RFM value have been determine by their quantile except frequency then their being accumulative for scoring. Then we define as passive, regular, valuable, and royal


We are using K-Means Clustering for the model because this is one of the most well-known models for clustering, and it is also relatively low-cost in regards to computational power. K-means clustering is one of the clustering algorithms based on division.
After determine the RFM value we began the modeling phase befor we apply the modeling we scaled the features because they dont have normal distributions with Standar Scaler, we using numbers 6 clusters according by the silhoutte score. there are passive, regular, occation, valuable, loyal, and best. Passive is when frequency, recency, and monetary values are the lowest.

For comparison we used DBScan for another modeling but because we dont have resource of high computational power we used only more or less 10% of the data then pick the segmentation based on noise, min samples, epsilon. After that we get 7 clusters, there are passive, regular, occation, valuable, loyal, golden and best. Passive is when frequency, frequency, and monetary values are the lowest.

# Evaluation
Based on cluster segmentation using non-model framework, k-means clustering, and dbscan clustering, we will used segment from k-means clustering with 6 cluster, that are passive, regular, occation, valuable, loyal, and best. K-means can group more clearly of every cluster, with minimize similarity with other clusters. With this clearly segmentation, Olist can analize customer more accurate so more get a company profit. Clearly segmentation can be an important thing in relationship marketing, because can increase understanding of customer necessities.

Badly, using other methods, segmentation division is not good as k-means clustering. Using non modeling, the lowest cluster is still mixed with middle clusters and middle clusters are mixed with the highest cluster. This is make hard to analyze every cluster. Positive thing of this segmentation is clusters are only divide into 4 groups which is make easy to understand every customer necessities.

In the meantime, using dbscan clustering, there are seven clusters that are making hard to understand every clusters even this model more clearly group every cluster than non modeling. But, impossible of the lowest cluster joined with the second highest cluster and the middle cluster in recency - monetary relation. The good things of this model are recency - frequency and frequency - monetary is clearly group every cluster.

While using k-means clustering, cluster is the most clearly. Even though, in recency-monetary relation, some point of middle cluster is in the low value like the lowest and the second lowest but it is still not problem because it is just a few of point of middle cluster. Even this model is grouping more than non modeling cluster, but it is still low than dbscan clustering.


# References
1. https://www.ada.cx/customer-segmentation

2. https://towardsdatascience.com/simple-customer-segmentation-using-rfm-analysis-1ccee2b6d8b9#:~:text=RFM%20analysis%20is%20a%20customer,cluster%20different%20customers%20into%20groups.

3. Manos,Tracy et al. Challenges and Research Opportunities in eCommerce Search and Recommendations.2020.ACM SIGIR FORUM. Vol 54 No 1

