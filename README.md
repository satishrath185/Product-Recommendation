# Product-Recommendation
## Business Value: 

Customers who are prompted with personalized product recommendations drive 24% of the orders and 26% of the revenues. This signifies how much significance product recommendation has on order volume and overall sales revenue. A product recommender system is a system with the goal of predicting and compiling a list of items that the customer is likely to purchase.

Here we are gooing to produce a list of recommendations:based on collaborative filtering method.

__Collaborative filtering:__ It is a method based on previous user behaviours such a pages they viewed, products they purchased or ratings they have given to different items. The assumption here is that a user is likely to purchase or view similar type of contents that they have viewed or purchased in the past.

In this process we first develop a user to item matrix where individual users are represented in rows and individual items in columns, and then compute the similarities between users by using the cosine similarity equation.

<img src="https://github.com/satishrath185/Product-Recommendation/blob/master/Images/Cosine.PNG" width="250" height="85" />

U1 and U2 represents user 1 and user 2
P1i and P2i represent product i that user 1 and user 2 have purchased.

## Problem Statement

To build a product recommender system with the goal of predicting and commpiling a list of items that a customer is likely to purchase.

## Data

![](Images/Online%20Retail.PNG)

Each row of data represents a transaction for a particular item and the attributes correspond to the following:

__InvoiceNo__ : Unique identifier for transaction 

__StockCode__ : Unique identifier for the stock item being purchased

__Description__ : Description of item

__Quantity__ : Number of units purchased

__InvoiceDate__ : Date of purchase

__UnitPrice__ : Cost of one unit of the item

__CustomerID__ : Unique Identifier for customer 

__Country__ : Country of transaction

## Approach

+ Importing Necessary Dependencies

+ Loading Data

+ Data Processing
	- Removing Product Returns
	- Identifying Null Rows
	- Handling Nan CustomerID
	- Creating Customer-item Matrix

+ Collaborative Filtering
	- User-based Collaborative filtering
		- Making Recommendations
	- Item-based Collaborative filtering
      - Making Recommendations

## Data Processing 

__Removing Product Returns__ : The negative value in quantity column are products that were returned after purchase and hence will not be considered as purchase.

__Identifying and Handling NaN__ : Without correct or missing values in dataset we will not be able to buld a proper recommendation system.

__Creating Customer_Item Matrix__ : Tabular data where each column represents each product or item and each row represents a customer and the valule in each cell represents whether the customer purchased the given product or not. 

![](Images/Cutomer%20Item%20Matrix.PNG)

## Collaborative Filtering

+ User-based

We compute the cosine similarity from the customer item matrix to determine similarity between user's purchase behaviour.

![](Images/Cosine%20Similarity.PNG)

Customers having high similarity with CustomerId 12350 is given as

![](Images/Demo%20Cosine%20Similarity.PNG)

For reference we take Cusstomer 12350 as A and Customer 17935 as B 
So Identifying the items purchased by Customer A and Customer B and the remainder of Items of Customer A over Customer B, we can safely assume that since there is high similarity between the customers the remainder of the priducts purchased by customer A is also likely to be purchased by customer B. Hence we make the recommendation of those remaining products to Customer B.

![](Images/Recommend%20B.PNG)

![](Images/Items%20Description.PNG)

- Item based Filtering

We take the transpose of the customer-item matrix to get the item similarity matrix and proceed with same steps in order to make recommendations for similar items bought by customers.

![](Images/Item%20Recommend.PNG)

## Conclusion

Using user-based collaborative filtering we can can do targeted product recommendations for individual customers. We can also custom-tailor and also include these products that each target customer is likely to purchase in marketing messages which can potentially drive more conversions from customers. However it is limited to only existing customers, however item-based colloborative filtering method overcomes this drawback and can be applied to both new and existing customers to drive higher conversion from customers.



