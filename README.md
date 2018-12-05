# MSDS621-Final-Project


## Group Name

Bean Solution


## Group Member

Xin Sun  
Zhi Li  
Minchen Wang  
Hongdou Li  
Bowen Ma  


## Project Name

Bid: Robot or Human?


## Data Source

Our data is from Kaggle Competition: Facebook Recruiting IV: Human or Robot?
https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot

There are two datasets. One is a bidder dataset that includes a list of bidder information, including their id, payment account, and address. The other is a bid dataset that includes 7.6 million bids on different auctions. The bids in this dataset are all made by bidders from bidder dataset.


## Background 

The two datasets are from an online platform. There is a trend of today's online advertising: human bidders on the site are becoming increasingly frustrated with their inability to win auctions, compared with software-controlled counterparts(robot). As a result, usage from the site's core advertiser base is plummeting.

In order to rebuild customer happiness, the site owners should eliminate computer generated bidding from their auctions. In this project, We want to build a model to help them identify these bids using behavioral data, including bid frequency over short periods of time, etc. 


## Goal

The goal of this project is to identify online auction bids that are placed by "robots".


## Table of Content

Throughout the jupyter notebook, We describe the process of connecting two datasets, cleaning data and finding useful features. For classification modeling, We tried several different supervised classification models, including Decision Tree, Random Forest, Gradient Boosting, etc. We also use grid search to tune the parameters of different types of models, so thus to best fit the train data. After modeling, we checked with accuracy, feature importance, confusion matrix and AUC/ROC to choose the optimal model. As a result, We are able to achieve a very accurate binary classifier by Gradient Boosting Model. 


### Preprocess data

1. Join table
2. Check & Handle missing values
3. Feature engineering

### Model fitting Process

1. Decision Tree
2. Random Forest
3. Gradient Boosting

### Model Results

1. Feature importance
2. Accuracy
3. Confusion Matrix
4. AUC/ROC

### Model Comparison

1. Analysis of models
2. Compare models
3. Present and interpret best model