![](https://storage.googleapis.com/kaggle-competitions/kaggle/5407/media/housesbanner.png)

# Ames Housing dataset

This case is inspired by Kaggle's [Getting Started Prediction Competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview). The exercises are structured based on the CRISP-DM framework. As you'll work through the exercises, you will experience first hand that CRISP-DM is a non-linear process.

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

Load 'AmesHousing.csv' in your Python environment.

## Exercise 2 - Descriptive statistics
### Data Understanding (continued)

a. Which variables are numerical? And which are categorical? How many variables do we have of both types?

b. How many missing values do each of the variables have (variable completeness) and what are the variable types? Is `SalePrice` complete?

c. Create a frequency table counting the number of missing values per variable

d. Conduct descriptive/summary statistics for numerical variables (e.g., mean, median, std, range) and for categorical variables (e.g., number of unique values, mode, and their frequency)


## Exercise 3 - Impute missing data
### Data Preparation

There a several missing values in the dataset, which need to be tackled before we can proceed with the rest of the analysis. There are many ways to impute missing values, but for now, impute missing values as follows:

a. Impute the numerical variables with the median value of the available data

b1. Impute the categorical variables with the label "other"

b2. Alternatively, impute the categorical variables with the mode (most frequent value) of the available data

c. Concatenate the numerical and the categorical data into a single data frame

d. Reduce memory usage by converting string type data to category type and downcast numerical data to their smallest container size. Tip: see Pandas' [astype() method](https://pandas.pydata.org/docs/user_guide/categorical.html) and [to_numeric() method](https://pandas.pydata.org/docs/reference/api/pandas.to_numeric.html). TO BE UPDATED TO USING POLARS.

## Exercise 4 - Explore the outcome variable (`SalePrice`) and how it correlates to other features
### Data Understanding (continued)

a. Conduct descriptive/summary statistics on the Y variable (mean, median, std, range)

b. Plot the distribution of the Y variable. What do we observe? Tip: see Altair's [histogram](https://altair-viz.github.io/gallery/simple_histogram.html)

c. Investigate how `Gr Liv Area` (numerical) relates to the Y variable. Tip: see Altair's [scatter plot](https://altair-viz.github.io/gallery/scatter_tooltips.html)

d. Investigate how `Neighborhood` (categorical) relates to the Y variable. Tip: see Altair's [histogram](https://altair-viz.github.io/gallery/simple_histogram.html) and [boxplot](https://altair-viz.github.io/gallery/boxplot.html)


### Data Preparation (continued)

e. Assess the distribution of `SalePrice` in exercise 4b. What did you observe? What does it mean for the performance of the prediction model? Log-transform the outcome variable

f. Assess `Gr Liv Area` for all houses in exercise 4d. What do you observe? Remove outliers. What does it mean for the scope of the prediction model?

### Data Understanding (continued)

g. Draw scatter plots between Y and each of the numerical features. Tip: see Altair's [scatter plot](https://altair-viz.github.io/gallery/scatter_tooltips.html)

h. Create a table showing the Pearson correlation coefficients between Y and each of the numerical variables. Tip: see [pearsonr()](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html)

i. Create correlation plots showing the correlations between each pair of numerical variables, incl. Y. Tip: see Seaborn's [heatmap](https://seaborn.pydata.org/generated/seaborn.heatmap.html) and [Fritz' Blog](https://fritz.ai/seaborn-heatmaps-13-ways-to-customize-correlation-matrix-visualizations/)

## Exercise 5 - Estimate a Linear Regression, a LASSO and a kNN model
### Modeling

a. Estimate a Linear Regression model, see sklearn's [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)

b. Estimate a LASSO model, see sklearn's [Lasso](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html) and [LassoCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html)

c. Estimate a kNN model, see sklearn's [Nearest Neighbors](https://scikit-learn.org/stable/modules/neighbors.html)

## Exercise 6 - Assess which model performs best
### Evaluation

The performance metric for the prediction model should be the Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sale price. This makes it the Root-Mean-Squared-Log-Error (RMSLE). By plotting a histogram of the sale price you will understand why the logarithm is recommended.

## Exercise 7 - Use SHAP values to explain how features contribute to Sale Price prediction

See 'exercise-7-shape.ipynb' in the folder 'ames-housing\'. 

