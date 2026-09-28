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

Pieter's solution notebooks provide reference implementations in both [Pandas](https://pandas.pydata.org/docs/reference/index.html) and [Polars](https://docs.pola.rs/api/python/stable/reference/index.html) for data manipulation. Polars is a blazingly fast data manipulation library. It is an Apache Arrow DataFrame library implemented in Rust. Because Pandas is/was the foundational industry standard, it is essential that every participant becomes comfortable with it. If you are new to Python or data manipulation, stick with Pandas to build solid fundamentals. If you already have experience with Python and Pandas, you are strongly encouraged to take on the challenge of using Polars throughout the exercises to explore its modern syntax and speed.

Although Polars is often described as an alternative or even a 'drop-in replacement' for Pandas, in practice it is not simply a matter of replacing `pd.` with `pl.`. The syntax, idioms, and mental model are genuinely different, and certain data manipulations can feel more concise in Pandas. Pandas is mature and established (dating back to [2008](https://pandas.pydata.org/about/)), whereas Polars dates back to [2020](https://pola.rs/posts/company-announcement/). Despite being younger, Polars evolves rapidly and enjoys significant traction thanks to its remarkable speed and memory efficiency.

# Exercise 1 - Load the 'Ames Housing' dataset
## Data Understanding

> [!NOTE]
> In the section `Set up Project Folder` of [Installation instruction – Visual Studio Code, Python 3.12, and Virtual Environments](https://github.com/EAISI/introduction-track-for-participants/blob/main/installation-instruction-vscode-pyenv-python-uv-ve.md#set-up-project-folder) you copied data files to your `ames-housing/data/raw/` folder.

a. Load `AmesHousing.csv` from your `ames-housing/data/raw/` folder.

b. Load 'Neighborhood names.xlsx' from your `ames-housing/data/raw` folder and merge the two-column table with the Ames Housing data. What is the primary key in 'Neighborhood names.xlsx' and what is the foreign key in 'AmesHousing.csv'? What is their role?

# Exercise 2 - Perform descriptive statistics
## Data Understanding (continued)

a. How many variables and observations does the dataset have?

b. What data types are the variables, and how many are there of each data type?

c. Split the original dataset into two DataFrames: one containing the numeric variables and one containing the string variables. Which variables belong to each type? Do the shapes of both DataFrames match your answers from the previous two questions?

d. Create a frequency table of missing data per variable for both the numeric and string DataFrames. How many missing values do each of the variables have? Include: variable name, total number of missing values, %completeness, and variable type.

e. Is `SalePrice` complete?

f. Only for those who use Polars - What missing-like values do you observe in the string data? What different behavior do you observe using the `read_csv()` function from both Pandas and Polars while using the default settings?

g. g. Conduct descriptive statistics for numeric variables (including: mean, median, std, and range) and for string variables (including: number of unique values, mode, and their frequency).

h. Optional - Test `f_describe()` from utils_pieter package.

# Exercise 3 - Split training and test set
## Data Preparation

Before transforming or imputing any data, we must protect ourselves against data leakage. The test set must act as unseen future data, not as a means to train the model.

a. Split the original dataset into a training set (70%) and a test set (30%). Set random_state=42 to ensure reproducible results. The split should result in four objects:

  1. A DataFrame containing the feature variables of the training set

  2. A DataFrame containing the feature variables of the test set

  3. A Series containing the target variable of the training set

  4. A Series containing the target variable of the test set

> [!IMPORTANT]
> From this point on, all exploratory analysis and calculation of preprocessing statistics (mean, median, mode) must be learned strictly from the training set and then applied to both the training and test sets.

# Exercise 4 - Impute missing data
## Data Preparation

There are several missing values in the dataset, which need to be tackled before we can proceed with the rest of the analysis. There are many ways to impute missing values, but for now, impute missing values as follows:

a. Impute numeric missing values in both the training and test sets using the median values computed from the training set.

b1. Impute string missing values in both the training and test sets using the label `"other"`.

b2. Alternatively, impute string missing values in both training and test sets using the mode (most frequent value) computed from the training set. In case you use Pandas, why does `df_pd.select_dtypes(include='str').mode()` result in a DataFrame with two rows?

c. Concatenate the imputed numeric and string subsets from exercises (a.) and (b.2) into a combined training set and a combined test set.

d. Reduce memory usage by casting string type to category type data and numeric data to their smallest container size. How much memory do we save by downcasting?

> [!TIP]
> Refer to Pandas' [astype()](https://pandas.pydata.org/docs/user_guide/categorical.html) method and [to_numeric()](https://pandas.pydata.org/docs/reference/api/pandas.to_numeric.html) function, or Polars' [cast()](https://docs.pola.rs/api/python/stable/reference/series/api/polars.Series.cast.html#polars.Series.cast) method for downcasting.

# Exercise 5 - Explore the outcome variable (`SalePrice`) and how it correlates to feature variables
## Data Understanding (continued)

a. Conduct descriptive statistics on the outcome variable (`SalePrice`), include: mean, median, std, and range.

b. Plot the distribution of the outcome variable. What do we observe and what does that mean for training a machine learning model on this outcome variable?

> [!TIP]
> See Altair's [histogram](https://altair-viz.github.io/gallery/simple_histogram.html).

c. Investigate how `Gr Liv Area` (numeric) relates to the outcome variable `SalesPrice`.

> [!TIP]
> See Altair's [scatter plot](https://altair-viz.github.io/gallery/scatter_tooltips.html).

d. Investigate how `Neighborhood_full` (string) relates to the outcome variable `SalesPrice`.

> [!TIP]
> See Altair's [histogram](https://altair-viz.github.io/gallery/simple_histogram.html) and [boxplot](https://altair-viz.github.io/gallery/boxplot.html).

## Data Preparation (continued)

e. Assess the distribution of `SalePrice` in exercise 5b. What do you observe? How does this shape motivate choosing RMSLE over RMSE as your performance metric without having to create a log-transformed outcome variable?

f. Assess the distribution of Gr Liv Area in exercise 5c. What do you observe? Identify and remove the extreme outliers. What does excluding these properties imply for the operational scope of your prediction model?

## Data Understanding (continued)

g. Draw scatter plots between the outcome variable and each of the numeric features.

> [!TIP]
> See Altair's [scatter plot](https://altair-viz.github.io/gallery/scatter_tooltips.html).

h. Create a table showing each numeric variable and its Pearson correlation with the outcome variable. Sort the table by the extent of the correlation. How do you account for positive versus negative correlations when sorting?

> [!TIP]
> See [pearsonr()](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html).

i. Create three correlation heatmaps for numeric variables: (1) All numeric features, (2) The top 10 features most strongly correlated with the outcome variable, and (3) Features referring to surface area (i.e., containing 'SF').

> [!TIP]
> See Seaborn's [heatmap](https://seaborn.pydata.org/generated/seaborn.heatmap.html) and [Fritz' Blog](https://fritz.ai/seaborn-heatmaps-13-ways-to-customize-correlation-matrix-visualizations/).

# Exercise 6 - Fit a Linear Regression, a LASSO and a kNN model
## Modeling

> [!TIP]
> Standard regressors minimize squared error (RMSE) on the target scale. How can you trick a standard regressor into optimizing for RMSLE without manually managing transformed target columns? This keeps predicted outcome variables in the orginal unit (USD) and makes interpreting the SHAP (see Exercise 8) much easier, but that's for later. First, check out Scikit-Learn's [`TransformedTargetRegressor()`](https://scikit-learn.org/stable/modules/generated/sklearn.compose.TransformedTargetRegressor.html) paired with input arguments, `func = np.log1p` and `inverse_func = np.expm1`.

> [!TIP] 
> In this exercise we will fit three different machine learning models. The specific questions are the same in each case. I suggest you read through all questions and design an approach that you can apply to each machine learning model evaluating the given scenarios.

a. Fit a Linear Regression model while considering the following steps:

  1. Start simple with one or more numerical variables to fit `LinearRegression()`. What are your lead candidate(s), and why? Ensure all features are properly scaled.

  2. Expand your feature set by adding a string variable, such as `Neighborhood`.

  3. Investigate the impact on model performance (RMSLE) when restricting the data to homes with a ground living area below 4,000 sq ft (i.e., `Gr Liv Area` < 4000).


> [!TIP]
> See sklearn's [`LinearRegression()`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html), article on [Linear Models](https://scikit-learn.org/stable/modules/linear_model.html) and [`OneHotEncoder()`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html). Further, as reference see ['Sklearn Linear Regression: A Complete Guide with Examples' by DataCamp](https://www.datacamp.com/tutorial/sklearn-linear-regression).

b. Build a pipeline that includes imputation, one-hot encoding, scaling, and a target-transformed linear regression model (optimizing for the log scale of the outcome variable). Train the model on `Overall Qual`, `Gr Liv Area`, `Garage Cars` (numeric variables), and `Neighborhood` (string variable), and evaluate the resulting test predictions using the RMSLE metric.

> [!TIP]
> See sklearn's [`Pipeline()`](https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html) and [`ColumnTransformer()`](https://scikit-learn.org/stable/modules/generated/sklearn.compose.ColumnTransformer.html) to apply different preprocessing steps to numeric and string features.

> [!NOTE]
> We use this pipeline on Day 6 of the Introduction program (Deployment).

c. Fit a Lasso regression model while considering the following steps:

  1. Start with all numeric features and tune the hyperparameter $\alpha$ using `LassoCV()`. What do you observe? What is the optimal $\alpha$? Ensure all features are properly scaled.

  2. Expand your feature set by adding a string variable, such as `Neighborhood`.

  3. Investigate the impact on model performance (RMSLE) when restricting the data to houses with a ground living area below 4,000 sq ft (i.e., `Gr Liv Area` < 4000).

> [!TIP] 
> See sklearn's [LassoCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html) and article on [Lasso](https://scikit-learn.org/stable/modules/linear_model.html#lasso).

d. Fit a kNN regression model while considering the following steps:

  1. Start with all numeric features and tune the hyperparameter `n_neighbors` using `KNeighborsRegressor()`. What do you observe? What is the optimal `n_neighbors`? Ensure all features are properly scaled.

  2. Expand your feature set by adding a string variable, such as `Neighborhood`.

  3. Investigate the impact on model performance (RMSLE) when restricting the data to houses with a ground living area below 4,000 sq ft (i.e., `Gr Liv Area` < 4000).

> [!TIP]
> See sklearn's [KNeighborsRegressor()](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html) and article on [Nearest Neighbors](https://scikit-learn.org/stable/modules/neighbors.html).

# Exercise 7 - Assess which model performs best
## Evaluation

a. Compare the test performance (RMSLE) across all trained models (e.g., in a summary table or bar chart).

b. Which model performs best on the test set? What RMSLE do you observe?

c. How does your best model compare to the Kaggle benchmark percentiles mentioned in the Business Understanding section above?

# Exercise 8 - Use SHAP values to explain how features contribute to Sale Price prediction

See `exercise-8-shap.ipynb` in the `discover-projects/ames-housing/code/` folder.