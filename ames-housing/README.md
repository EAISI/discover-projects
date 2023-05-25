![](https://storage.googleapis.com/kaggle-competitions/kaggle/5407/media/housesbanner.png)

# Ames Housing dataset

This case is inspired by Kaggle's [Getting Started Prediction Competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview). The information you need to work on this case is stored on [GitHub 'jads-nl'](https://github.com/jads-nl/discover-projects/tree/main/ames-housing). The exercises are structured based on the CRISP-DM methodology. As you'll work through the exercises, you will experience first hand that CRISP-DM is a non-linear process ;-)

## Let's get started

### Business Understanding

**Business context**: Real estate agency 'Homely Homes' incorporated in Ames, Iowa (USA), needs a good first impression of the sale price of a house as soon as it comes on the market, without having to visit the house. Today, 'Homely Homes' uses their team of real estate agents of different levels of expertise to get an estimate based on the information that is available online. The quality of the estimates differs highly depending on who is asked. And, not surprisingly, the more experienced agents are not always readily available. So, the management team of Homely Homes has decided to go full on data, and is requesting you to develop a model that can predict the sale price by the push of a button. 

**Business objective**: To become independent on real estate agents to estimate sale prices.

**Scope**: All homes in the city of Ames, IA (USA).

**Project goal**: Develop a model that predicts sale price of a house given a set of it's features,

- The performance metric for your prediction model is the `Root Mean Squared Logarithmic Error` (RMSLE), i.e., the root mean squared error between the logarithm of the predicted value and the logarithm of the observed sale price. Taking the logarithm means that errors in predicting overly expensive houses and cheaper houses will affect the result equally.

- Looking at the [public leaderboard](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/leaderboard), the top 2% have an RMSLE of 0.00044, whilst 25th-percentile and the median performance is at 0.125 and 0.14, respectively.

- As an extra challenge, you can try to trade-off the number of predictors (less is better) vs. performance. Can you make the top 10% (RMSLE 0.123) with the least number of predictors?


## Exercise 1 - Load the 'Ames Housing' dataset
### Data Understanding

Load 'AmesHousing.csv' in your Python environment, [GitHub 'jads-nl'](https://github.com/jads-nl/discover-projects/tree/main/ames-housing).

## Exercise 2 - Descriptive statistics
### Data Understanding (continued)

a. Which variables are numerical? And which are strings? How many variables are there of both types?

b. Get first feel for missing values (variable completeness) and type. Is `SalePrice` complete? (hint: use `info()`)

c. Conduct descriptive/summary statistics for numerical variables (e.g., mean, SD, range) and object variables (e.g., number of unique values, mode, and its frequency)

d. Create a frequency table counting the number of missing values per variable

## Exercise 3 - Impute missing data
### Data Preparation

There a several missing values in the dataset, which need to be tackled before we can proceed with the rest of the analysis. There are many ways to impute missing values, but for now, impute missing values as follows:

a. Impute number variables with median value in concerned number variable

b1. Impute object variables with label "other"

b2. Alternatively, impute object variables with the most frequently present label in concerned object variable

c. Concatenate the numerical and object data into a single data frame

## Exercise 4 - Explore the outcome variable (`SalePrice`) and how it correlates to other features
### Data Understanding (continued)

a. Conduct descriptive/summary statistics on the Y variable (mean, median, SD, range)

b. Investigate how neighborhood (categorical) and grand living area (continuous) relate to the Y variable; use, e.g., bar charts, scatter plots, boxplots (hint: use [`pandas.DataFrame.hist`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.hist.html), [`matplotlib.pyplot.scatter`](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.scatter.html),[`seaborn.histplot`](https://seaborn.pydata.org/generated/seaborn.histplot.html), [`seaborn.scatterplot`](https://seaborn.pydata.org/generated/seaborn.scatterplot.html), [`seaborn.boxplot`](https://seaborn.pydata.org/generated/seaborn.boxplot.html), [altair.histogram](https://altair-viz.github.io/gallery/simple_histogram.html), [altair.scatter](https://altair-viz.github.io/gallery/scatter_tooltips.html), [altair.boxplot](https://altair-viz.github.io/gallery/boxplot.html))

c. Visualize the distribution of the Y variable. What do you observe?

### Data Preparation (continued)

d. Assess the distribution of `SalePrice` in the previous exercise. What do you observe? Log-transform the outcome variable. What does it mean for the performance of the prediction model?

e. Assess grand living area ('Gr Liv Area') for all houses in previous exercise. What do you observe? Remove outliers. What does it mean for the applicability of the prediction model?

### Data Understanding (continued)

f. Draw scatter plots between Y and all numerical features (hint: use [`seaborn.pairplot`](https://seaborn.pydata.org/generated/seaborn.pairplot.html))

g. Draw correlation plots to see all correlations between Y and the independent (continuous) variables (Hint: calculate Pearson correlation coefficient and use [`seaborn.heatmap`](https://seaborn.pydata.org/generated/seaborn.heatmap.html))

## Exercise 5 - Estimate a Linear Regression, a LASSO and a kNN model
### Modeling

a. Estimate a Linear Regression model

b. Estimate a LASSO model

c. Estimate a kNN model

## Exercise 6 - Assess which model performs best
### Evaluation

The performance metric for the prediction model should be the Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sale price. This makes it the Root-Mean-Squared-Log-Error (RMSLE). By plotting a histogram of the sale price you will understand why the logarithm is recommended.

