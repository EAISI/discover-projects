![](https://storage.googleapis.com/kaggle-competitions/kaggle/5407/media/housesbanner.png)

# Ames Housing dataset

This case is inspired by Kaggle's [Getting Started Prediction Competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview). The information you need to work on this case is stored on [GitHub 'jads-nl'](https://github.com/jads-nl/discover-projects/tree/main/ames-housing)


### Business Understanding

**Business context**: Real estate agency 'Homely Homes' incorporated in Ames, Iowa (USA), needs a good first impression of the sales price of a house as soon as it comes on the market, without having to visit the house. Today, 'Homely Homes' uses their team of real estate agents of different levels of expertise to get an estimate based on the information that is available online. The quality of the estimates differs highly depending on who is asked. And, not surprisingly, the experienced agents are not always readily available. So, the management team of Homely Homes has decided to go full on data, and is requesting a data science expert to develop a model that can predict the sales price by the push of a button. 

**Business objective**: To become independent on real estate agents to estimate sales prices.

**Scope**: All homes in the city of Ames, IA (USA).

**Project goal**: Develop a model that predicts sales price of a house given a set of it's features,

- The performance metric for your prediction model is the `Root Mean Squared Logarithmic Error` (RMSLE), i.e., the root mean squared error between the logarithm of the predicted value and the logarithm of the observed sales price. Taking the logarithm means that errors in predicting expensive houses and cheap houses will affect the result equally.

- Looking at the [public leaderboard](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/leaderboard), the top 2% have an RMSLE of 0.00044, whilst 25th-percentile and the median performance is at 0.125 and 0.14, respectively.

- As an extra challenge, you can try to trade-off the number of predictors (less is better) vs. performance. Can you make the top 10% (RMSLE 0.123) with the least number of predictors?


### Data Understanding

#### Exercise 1

Provide a table with descriptive statistics for all included variables and check:

a. The variable that can be used as the 'Y' variable, a.k.a the dependent or outcome variable. Which is it?

b. Classes of each variable. Which variables are categoric and which are continuous?

c. Descriptive/summary statistics for continuous variables (e.g., mean, SD, range) and categorical variables (e.g., frequencies)
  
d. Missing values


### Exercise 2

Explore the Y variable in terms of:

a. Descriptive/summary statistics, e.g., mean, SDs, range

b. Visualize the distribution of Y

c. Visualize the distribution of Y by looking at various subgroups, e.g., create scatter plots for continuous variables and box plots for categorical variables

d. Look at differences between neigbourhoods

e. Look at differences between housing style

f. Draw a correlation plot to see all correlations between Y and the independent (continuous) variables (Hint: use [`df.plotting.scatter_matrix`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.plotting.scatter_matrix.html) or [`seaborn.pairplot`](https://seaborn.pydata.org/generated/seaborn.pairplot.html))

g. Draw a correlation plot to see all correlations between dependent variables that relate to surface area, indicated by 'SF' in variable name.

### Data Preparation



Remove outliers

One hot enconding

g. Draw a correlation plot to see correlations between Y and the neighborhoods.

### Exercise 4
There a several missing values in the dataset, which need to be tackled before we can proceed with the rest of the analysis. There are many ways to impute missing values, but for now, impute missing values as follows:

  - Use the median for continuous variables
  - Use the label "100" in all factor variables


### Modeling

### Evaluation

The performance metric for the prediction model should be the Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sales price. This makes it the Root-Mean-Squared-Log-Error (RMSLE). By plotting a histogram of the sale price you will understand why the logarithm is recommended.


#============================================================================================================


  
### Exercise 1
Provide a table with descriptive statistics for all included variables and check:
  
  - Classes of each of the variables (e.g. factors or continuous variables)
  - Descriptive/summary statistics for all continuous variables (e.g. mean, SD, range) and factor variables (e.g. frequencies)
  - Explore missing values

### Exercise 2
There a several missing values in the dataset, which need to be tackled before we can proceed with the rest of the analysis. There are many ways to impute missing values, but for now, impute missing values as follows:

  - Use the median for numeric variables
  - Use the label "100" in all factor variables
  
### Exercise 3
The variable "SalePrice" refers to the price at which a property was sold and hence is the variable of interest for our prediction model ("Y" or dependent variable). Explore Y in terms of:

  - Descriptive/summary statistics (e.g. mean, SDs, range)
  - Visualize the distribution of Y (e.g. matplotlib or seaborn)
  - Visualize the distribution of Y by looking at various subgroups (e.g. create boxplot or scatterplot using matplotlib or seaborn)
  - Look at differences between neigbourhoods
  - Look at differences between housing style
  - Draw a correlation plot to see all correlations between Y and the independent (numeric) variables (Hint: use [`df.plotting.scatter_matrix`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.plotting.scatter_matrix.html) or [`seaborn.pairplot`](https://seaborn.pydata.org/generated/seaborn.pairplot.html))
  
  
### Exercise 4

  - Estimate a LASSO model and a kNN model
  - Assess which model performs best
