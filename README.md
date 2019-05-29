# Facebook Recruiting IV: Human or Robot?

> https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot/overview   
> Bean Solution: Xin Sun, Zhi Li, Minchen Wang, Hongdou Li, Bowen Ma   
> [Report](https://docs.google.com/presentation/d/1J6CYlZcH6qdpIOIxzyUXR9cpnSkneKLx59BNYdVXR2E/edit?usp=sharing)

## Table of Content

- Project Goal
- Data Source
- Data Preprocessing
  - [Data Cleaning](<https://github.com/crystalxs/human-or-robot/blob/master/data_cleaning.ipynb>)
  - [EDA](<https://github.com/crystalxs/human-or-robot/blob/master/EDA.ipynb>)
  - [Feature Engineering](<https://github.com/crystalxs/human-or-robot/blob/master/feature_engineering.ipynb>)
- [Modeling](#Modeling)
  - [Pre-modeling](<https://github.com/crystalxs/human-or-robot/blob/master/pre-modeling.ipynb>)
  - [Decision Tree](<https://github.com/crystalxs/human-or-robot/blob/master/modeling_decision_tree.ipynb>)
  - [Random Forest](<https://github.com/crystalxs/human-or-robot/blob/master/modeling_random_forest.ipynb>)
  - [Gradient Boosting](<https://github.com/crystalxs/human-or-robot/blob/master/modeling_gradient_boosting.ipynb>)
- [Model Comparison](<https://github.com/crystalxs/human-or-robot/blob/master/model_comparison.ipynb>)
- [Summary](#Summary)

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

The bids data is extremely imbalanced data, where bids made by human v.s. bids made by robot is 30:20.

## Modeling

For classification modeling, We tried several different supervised classification models, including Decision Tree, Random Forest, Gradient Boosting, etc. We also use grid search to tune the parameters of different types of models, so thus to best fit the train data. After modeling, we checked with:
1. Feature importance
2. Accuracy   
	Accuracy is not a good metric for extremely imbalanced dataset, since the ratio of made by robot vs. bids made by human in data set is 3:20, if we label all the bids as human, we still could get 86.75% accuracy, however, it doesn't target anything.
3. AUC/ROC   
	AUC/ROC is a good metric for imbalanced dataset.
4. Confusion Matrix   
	+ We care about the precision because we don't want to miss any robot.  
	+ We care about the recall because we don't want to label any human user as robot to make users disappointed with the service. 


|Metrics        |Decision Tree|Random Forest|Gradient Boosting|
|:-------------:|:-----------:|:-----------:|:---------------:|
|Accuracy_score |0.834        |0.922        |0.981            |
|Precision_score|0.443        |0.657        |0.887            |
|Recall_Score   |0.928        |0.877        |0.983            |
|F1_score       |0.599        |0.752        |0.932            |
|ROC_AUC_score  |0.873        |0.903        |0.982            |
|Time(s)        |1.228        |75.841       |75.273           |

## Summary

From the feature importance, we can see that in the online bidding, human being are more likely come from a random url into a certain aution, however, the robots are more likely come from few specific url. And compared with human beings robots are more likely to use different ip addresses for online bidding. Thus if for a user, it using multi-ip addresses and come from few certain url, we might consider it is a robots.
