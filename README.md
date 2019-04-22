# Facebook Recruiting IV: Human or Robot?

> > https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot/overview

Bean Solution: Xin Sun, Zhi Li, Minchen Wang, Hongdou Li, Bowen Ma  

## Table of Content

- [Project Goal](#Project Goal)
- [Data Source](#Data Source)
- [Data Preprocessing](#Data Preprocessing)
  - [Data Cleaning]()
  - [EDA]()
  - [Feature Engineering]()
- [Modeling](#Modeling)
  - [Pre-modeling]()
  - [Decision Tree]()
  - [Random Forest]()
  - [Gradient Boosting]()
- [Evaluation](#Evaluation)
  - [Model Comparison]()
- [Summary](#Summary)

Throughout the jupyter notebook, We describe the process of connecting two datasets, cleaning data and finding useful features. For classification modeling, We tried several different supervised classification models, including Decision Tree, Random Forest, Gradient Boosting, etc. We also use grid search to tune the parameters of different types of models, so thus to best fit the train data. After modeling, we checked with accuracy, feature importance, confusion matrix and AUC/ROC to choose the optimal model. As a result, We are able to achieve a very accurate binary classifier by Gradient Boosting Model. 

## Project Goal

The goal of this competition is to identify online auction bids that are placed by "robots", helping the site owners easily flag these users for removal from their site to prevent unfair auction activity.

## Data Source

Our data is from Kaggle Competition: [Facebook Recruiting IV: Human or Robot?](https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot)

There are two kinds of datasets. One is a **bidder dataset** that includes a list of bidder information, including their id, payment account, and address. The other is a **bid dataset** that includes 7.6 million bids on different auctions. The bids in this dataset are all made by mobile devices.

- **Bidder datasets**
  - **train.csv** - the training set from the bidder dataset
  - **test.csv** - the test set from the bidder dataset
- **Bid dataset**
  - **bids.csv** - the bid dataset

## Data Preprocessing

1. Join table
2. Check & Handle missing values
3. Feature engineering

## Modeling

1. Decision Tree
2. Random Forest
3. Gradient Boosting

## Evaluation

### Model Results

1. Feature importance
2. Accuracy
3. Confusion Matrix
4. AUC/ROC

### Model Comparison

1. Analysis of models
2. Compare models
3. Present and interpret best model

## Summary

From the feature importance, we can see that in the online bidding, human being are more likely come from a random url into a certain aution, however, the robots are more likely come from few specific url. And compared with human beings robots are more likely to use different ip addresses for online bidding. Thus if for a user, it using multi-ip addresses and come from few certain url, we might consider it is a robots.