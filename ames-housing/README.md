---
title: Ames Housing
subtitle: Predicting Sales Prices with Machine Learning
author: Pieter Overdevest
email: pieter@innovatewithdata.nl
date: Sept 9, 2026
version: 1.2.0
---

<p align="center">
  <img src="images/banner.jpg" alt="Ames Housing">
</p>



This case is inspired by Kaggle's [Getting Started Prediction Competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview). The exercises are structured based on the CRISP-DM framework. As you'll work through the exercises, you will experience first hand that CRISP-DM is a non-linear process.

# Let's get started

## Business Understanding

**Business context**: Real estate agency 'Homely Homes' incorporated in Ames, Iowa (USA), needs a good first impression of the sale price of a house as soon as it comes on the market, without having to visit the house. Today, 'Homely Homes' uses their team of real estate agents of different levels of expertise to get an estimate based on the information that is available online. The quality of the estimates differs highly depending on who is asked. And, not surprisingly, the more experienced agents are not always readily available. So, the management team of Homely Homes decides to go full on data and requests you to develop a model that can predict the sale price by the push of a button.

**Business objective**: To become independent of real estate agents to estimate sale prices.

**Scope**: All homes in the city of Ames, IA (USA). Though, with good reasons you may scope down the houses.

**Project goal**: Develop a model that predicts the sale price of a house given a set of its features:

- The recommended performance metric for your prediction model is the `Root Mean Squared Logarithmic Error` (`RMSLE`). In housing data, the outcome variable is rarely symmetrically (normally) distributed; it is heavily right-skewed, with many moderately priced homes and a few exceptionally high-priced homes. Under standard RMSE, an error of $50,000 on a $1,000,000 mansion is penalized just as heavily as a $50,000 error on a $100,000 starter home. By taking the logarithm of the observed and predicted prices, RMSLE measures relative percentage differences, ensuring both cheap and expensive houses impact the metric fairly.

- Looking at the [public leaderboard](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/leaderboard), the top 2% have an RMSLE of 0.00044, whilst the 25th percentile and the median performance are at 0.125 and 0.14, respectively.

- As an extra challenge, you can try to trade-off the number of predictors (less is better) vs. performance. Can you make the top 10% (RMSLE 0.123) with the least number of predictors?

## Polars vs Pandas

Pieter's solution notebooks provide reference implementations in both [Pandas](https://pandas.pydata.org/docs/reference/index.html) and [Polars](https://docs.pola.rs/api/python/stable/reference/index.html) for data manipulation. Polars is a blazingly fast data manipulation library. It is an Apache Arrow DataFrame library implemented in Rust. Because Pandas is the foundational industry standard, it is essential that every participant becomes comfortable with it. If you are new to Python or data manipulation, stick with Pandas to build solid fundamentals. If you already have experience with Python and Pandas, you are strongly encouraged to take on the challenge of using Polars throughout the exercises to explore its modern syntax and speed.

Although Polars is often described as an alternative or even a 'drop-in replacement' for Pandas, in practice it is not simply a matter of replacing `pd.` with `pl.`. The syntax, idioms, and mental model are genuinely different, and certain data manipulations can feel more concise in Pandas. Pandas is mature and established (dating back to [2008](https://pandas.pydata.org/about/)), whereas Polars dates back to [2020](https://pola.rs/posts/company-announcement/). Despite being younger, Polars evolves rapidly and enjoys significant traction thanks to its remarkable speed and memory efficiency.

# Exercise 1 - Load the 'Ames Housing' dataset
## Data Understanding

a. Load `AmesHousing.csv` from your `ames-housing/data/` folder.

b. Load 'Neighborhood names.xlsx' from your `ames-housing/data/` folder and merge the two-column table with the Ames Housing data. What does 'Neighborhood_full' enable you to do?

# Exercise 2 - Descriptive statistics
## Data Understanding (continued)

a. Which variables are numerical? And which are strings? How many variables do we have of both types? How many observations do we have? Suggestion: Split the original data in a data frame containing the numerical data and a data frame containing the string data. 

b. How many missing values do each of the variables have (variable completeness) and what are the variable types? Is `SalePrice` complete? And what other, missing-like values do you observe in the string data? What different behavior do you observe using the `read_csv()` function from both Pandas and Polars and using the default settings? Create a frequency table of missing data per variable.

c. Conduct descriptive/summary statistics for numerical variables (e.g., mean, median, std, and range) and for string variables (e.g., number of unique values, mode, and their frequency)

# Exercise 3 - Train/test split data
## Data Preparation

Before transforming or imputing any data, we must protect ourselves against data leakage. The test set must act as unseen future data.

a. Split the dataset into a training set (70%) and a test set (30%). Set `random_state=42` to ensure reproducible results.

> [!IMPORTANT]
> From this point on, all exploratory analysis and calculation of preprocessing statistics (mean, median, mode) must be learned strictly from the training set and then applied to both the training and test sets.

# Exercise 4 - Impute missing data
## Data Preparation

There are several missing values in the dataset, which need to be tackled before we can proceed with the rest of the analysis. There are many ways to impute missing values, but for now, impute missing values as follows:

a. Impute numerical missing values in both the training and test sets using the median values computed from the training set.

b1. Impute string missing values in both the training and test sets using the label `"other"`.

b2. Alternatively, impute string missing values in both sets using the mode (most frequent value) computed from the training set. In case you use Pandas, why does `df_pd.select_dtypes(include='str').mode()` result in a DataFrame with two rows?

c. Concatenate the imputed numerical (b.) and string (c2.) subsets into a combined training set and a combined test set.

d. Reduce memory usage by casting string type to category type data and numerical data to their smallest container size. Tip: see Pandas' [astype()](https://pandas.pydata.org/docs/user_guide/categorical.html) and [to_numeric()](https://pandas.pydata.org/docs/reference/api/pandas.to_numeric.html) methods, or Polars' [cast()](https://docs.pola.rs/api/python/stable/reference/series/api/polars.Series.cast.html#polars.Series.cast) method. How much memory do we save by downcasting?

# Exercise 5 - Explore the outcome variable (`SalePrice`) and how it correlates to other variables
## Data Understanding (continued)

a. Conduct descriptive/summary statistics on the outcome variable (mean, median, std, and range).

b. Plot the distribution of the outcome variable. What do we observe? Tip: see Altair's [histogram](https://altair-viz.github.io/gallery/simple_histogram.html).

c. Investigate how `Gr Liv Area` (numerical) and the outcome variable correlate. Tip: see Altair's [scatter plot](https://altair-viz.github.io/gallery/scatter_tooltips.html).

d. Investigate how `Neighborhood_full` (categorical) relates to the outcome variable. Tip: see Altair's [histogram](https://altair-viz.github.io/gallery/simple_histogram.html) and [boxplot](https://altair-viz.github.io/gallery/boxplot.html).

## Data Preparation (continued)

e. Assess the distribution of `SalePrice` in exercise 4b. What do you observe? How does this skewed distribution motivate using RMSLE instead of RMSE as our evaluation metric, without needing to transform `SalePrice`?

f. Assess `Gr Liv Area` for all houses in exercise 4c. What do you observe? Remove outliers. What does it mean for the scope of the prediction model?

## Data Understanding (continued)

g. Draw scatter plots between the outcome variable and each of the numerical features. Tip: see Altair's [scatter plot](https://altair-viz.github.io/gallery/scatter_tooltips.html).

h. Create a table showing the Pearson correlation coefficients between the outcome variable and each of the numerical variables. Tip: see [pearsonr()](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html).

i. Create correlation plots showing the correlations between each pair of numerical variables, incl. the outcome variable. Tip: see Seaborn's [heatmap](https://seaborn.pydata.org/generated/seaborn.heatmap.html) and [Fritz' Blog](https://fritz.ai/seaborn-heatmaps-13-ways-to-customize-correlation-matrix-visualizations/).

# Exercise 6 - Estimate a Linear Regression, a LASSO and a kNN model
## Modeling

> [!TIP]
> Because we keep `SalePrice` in its original currency (which keeps our predictions and later SHAP values easily interpretable), use scikit-learn's [`root_mean_squared_log_error()`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.root_mean_squared_log_error.html) to evaluate `y_test` against `y_pred` for each model you train.

a. Estimate a Linear Regression model, see sklearn's [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html).

b. Build a pipeline including imputation, encoding, scaling, and modelling - see sklearn's [Pipeline](https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html). Estimate a Linear Regression model based on `Neighborhood` and three numerical features of your choice. Tip: use sklearn's [ColumnTransformer](https://scikit-learn.org/stable/modules/generated/sklearn.compose.ColumnTransformer.html) to apply different preprocessing steps to numerical and categorical features (imputation + scaling vs. imputation + one-hot encoding). We use this pipeline on Day 6 of the Introduction program (Deployment).

c. Estimate a LASSO model, see sklearn's [Lasso](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html) and [LassoCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html).

d. Estimate a kNN model, see sklearn's [Nearest Neighbors](https://scikit-learn.org/stable/modules/neighbors.html).

# Exercise 7 - Assess which model performs best
## Evaluation

Compare the test performance (RMSLE) across all estimated models (e.g., in a summary table or bar chart).

a. Which model performs best on the test set? What RMSLE do you observe?

b. How does your best model compare to the Kaggle benchmark percentiles listed in the introduction section?

# Exercise 8 - Use SHAP values to explain how features contribute to Sale Price prediction

See `exercise-8-shap.ipynb` in the `ames-housing/code/` folder.