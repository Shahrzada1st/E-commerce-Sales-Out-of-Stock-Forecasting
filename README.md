# E-commerce-Sales-Out-of-Stock-Forecasting

#### Introduction and background
This project is created based on a real business problem at a Food company. 
The daily e-commerce sales day for 10,000 products is available from 2012 to 2016. In addition, daily out of stock product is known (this is a binary value of 0 or 1, associated with product out/in stock.
Each product belongs to a broad brand. There are total of 100 brands that the products are mapped to. 
Searching through SQL database, there is history of marketing campaign available with start dates and binary campaign features.

#### Data
There are 5 datasets available that are all tied to product sales and in/out of stock status:
1. Daily sales data by products (missing some values) 
2. A mapping of products to brands 
3. Daily out-of-stock signal by product 
4. Marketing campaign start dates and binary features for products 
5. Marketing campaign start dates and binary features for entire brands.

#### Objective
The goal is to predict when will each product go out of stock given the history of sales, marketing campaigns on brand and product promotions, and other key findings in the dataset.

#### Results
A Random Forest classifier is built to predict when a given product will go out of stock given the number of days since the last product promotion started, number of days since the last brand promotion started, the cumulative sales on a given day, and the unspecified features from the product and brand promotions (f0 through f29).

On average, across a random sampling of ~100 products, the model achieved an average hold-out set accuracy of 85%, average F1 score of 0.86, average precision of 0.85, and average recall of 0.86. These are good measures of generalization performance, as they were measured on a 33% hold out set. 

The feature importances from the trained Random Forest showed that in most cases the recency of a product promotion, the cumulative product sales until the day in question were more strongly predictive of a product being out of stock than a brand promotion associated with that product.  The unspecified features of the promotions were not strong predictors of whether a product was out of stock.
