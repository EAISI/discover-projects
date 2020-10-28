![](https://storage.googleapis.com/kaggle-competitions/kaggle/5407/media/housesbanner.png)

Following Kaggle's [Getting Started Prediction Competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview), the goal for this discover project is to predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable. 

The performance metric for your prediction model is the _Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sales price_. (Taking logs means that errors in predicting expensive houses and cheap houses will affect the result equally.)

Looking at the [public leaderboard](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/leaderboard), the top 2% have RMSLE of 0.00044, whilst 25th-percentile and and median performance is at 0.125 and 0.14, respectively.

As an extra challenge, you can try to trade-off the number of predictors (less is better) vs. performance. Can you make the top 10% (RMSLE 0.123) with the least number of predictors?

Things to try and explore:
  - Feature selection
  - Feature engineering
  - Ensemble models
  - Stacked models
