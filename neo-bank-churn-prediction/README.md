![](neo_bank_2020.png)

# Neo Bank Churn prediction

## Description
Your stakeholders set a very high priority to explainability and do not trust black box modelling, thus it has been decided that you can only deploy a single supervised model architecture: No blending, no stacking. At least the data scientist, whose role you are replacing, has been able to convince the stakeholders that model orchestration is not a black box before he left.

In this competition we expect participants to create a solution that uses a single model architecture per model type only. I.e. you may use Logistic Regression, Xgboost, Catboost or a neural network, but you are not allowed to train more than one model architecture and use more than one model per prediction. However you are allowed to train multiple models if their predictions are not blended and if they are from the same model architecture. Also you are allowed to define a rule system or use unsupervised methods. Model orchestration is allowed in general.

I.e.:

### Blending/Ensembling
```
row_1 : avg (Catboost & Xgboost predictions)
row_2 : avg (Catboost & Xgboost predictions) 
```
-> not allowed

```
row_1 : avg (Xgboost & Xgboost predictions)
row_2 : avg (Xgboost & Xgboost predictions) 
```
-> not allowed

### Single model

```
row_1 :Xgboost
row_2 : Xgboost 
```
-> allowed

### Orchestration
```
row_1 :Xgboost
row_2 : Catboost 
```
-> not allowed
```
row_1 : Xgboost model 1
row_2 : Xgboost model 2 
```
-> allowed

### Combination

You are also allowed to combine manually defined rules with a model, i.e.:

row_1 : rule col_1 * col_2 > 500
row_2 : Xgboost
-> allowed

You are also allowed to combine manually defined rules and unsupervised models with a model, i.e.:
```
row_1 : rule col_1 * col_2 > 500 if outlier_score >= -0.5
row_2 : Xgboost
```
-> allowed

or:
```
row_1 : Xgboost model 1 (because outlier score decided which model to use)
row_2 : Xgboost model 2 (because outlier score decided which model to use)
```
-> allowed

## Evaluation

Submission will be evaluated using the logloss.

Logarithmic loss measures the performance of a classification model where the prediction input is a probability value between 0 and 1. A perfect model would have a log loss of 0. Log loss increases as the predicted probability diverges from the true label:

$$
− \frac{1}{𝑁} \sum_{i=1}^{N}[y_i \log(p_i) + (1 - y_1)\log(1-p_i)]
$$

where $y_i$ is the label (0 and 1 for binary) and $p_i$ is the predicted probability of the data point being 1 for all N points.

## Data

The dataset is synthetic, but has not been synthesized from another dataset. Instead it has been created based on domain knowledge. Instead of modelling columns with distributions, personas of customers have been defined and applied when generating the rows. Also dynamic changes in the economy or business strategy of Neo bank had an impact on the data.

The dataset is classic tabular, but has a nested list in the touchpoints column and a nested dictionary in the CSAT column.

The data can be downloaded [here](https://www.kaggle.com/competitions/neo-bank-non-sub-churn-prediction/data).

