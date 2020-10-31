# JADS Discover Machine Learning projects

## A selection of 'discovery projects' for getting hands-on experience in machine learning
This repository was developed as part of the Discover track at the [Jheronimus Academy of Data Science (JADS)](https://www.jads.nl/professionaleducation.html). The aim of these 'discovery projects' is to facilitate the participants in getting hands-on experience in building a model following the CRISP-DM framework. Learning-by-doing is arguably the best way to get through the [valley of despair](https://mensenengedrag.nl/2019/06/05/the-dunning-kruger-effect-in-innovation/) as quickly as possible.

![CRISP-DM framework](https://exde.files.wordpress.com/2009/03/crisp_visualguide.png?w=768)

## A curated selection of public datasets, notebooks, articles and other stuff from the commons
[Made with creative commons in mind](https://creativecommons.org/use-remix/made-with-cc/), we have used and remixed what we think are the most useful datasets, notebooks, articles available in the public domain. Each folder contains a set of materials for a given dataset, with specific assignments and questions. Examples of solutions and best practices are included in R and Python notebooks. In due course we aim to add [H2O Flow](https://docs.h2o.ai/h2o/latest-stable/h2o-docs/flow.html) for those preferring to work with a graphical UI.

### [Ames Housing dataset by Dean de Kock (2011)](http://jse.amstat.org/v19n3/decock.pdf)
An alternative, more detailed and rich dataset than the Boston housing dataset (which dates from 1978). Available on Kaggle's [Getting Started Prediction Competition](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview) with a lot of useful tutorials. Alternatively, use the [AmesHousing R package](https://cran.r-project.org/web/packages/AmesHousing/AmesHousing.pdf).

### [UCI Heart Disease dataset (2008)](https://archive.ics.uci.edu/ml/datasets/heart+disease)
Four combined databases compiling heart disease information. This database contains 76 attributes, but all published experiments refer to using a subset of 14 of them. In particular, the Cleveland database is the only one that has been used by ML researchers to this date. The "goal" field refers to the presence of heart disease in the patient. It is integer valued from 0 (no presence) to 4. Also available on [Kaggle](https://www.kaggle.com/ronitf/heart-disease-uci), [data.world](https://data.world/uci/heart-disease) and included in the [kmed R package](https://cran.r-project.org/web/packages/kmed/index.html)


### [Pima Indians Diabetes database (2006)]()
This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective of the dataset is to diagnostically predict whether or not a patient has diabetes, based on certain diagnostic measurements included in the dataset. Several constraints were placed on the selection of these instances from a larger database. In particular, all patients here are females at least 21 years old of Pima Indian heritage. Interestingly, the objective of the [original study by Schulz et al. in 2006](https://github.com/dkapitan/jads-discover-projects/blob/main/pima-indians-diabetes/schulz2006effects.pdf) was to determine genetic and environmental determinants for type 2 diabetes and obesity. To this purpose, the effects of different environments on these diseases in Pima Indians in Mexico and Available on [Kaggle](https://www.kaggle.com/uciml/pima-indians-diabetes-database), [data.world](https://data.world/data-society/pima-indians-diabetes-database) and included in the [mlbench R package](https://cran.r-project.org/web/packages/mlbench/index.html). Note there is a different [UCI diabetes dataset](https://archive.ics.uci.edu/ml/datasets/diabetes)

### [Credit Card Fraud dataset](https://mlg.ulb.ac.be/wordpress/portfolio_page/defeatfraud-assessment-and-validation-of-deep-feature-engineering-and-learning-solutions-for-fraud-detection/)
The datasets contains transactions made by credit cards in September 2013 by european cardholders and was compiled by the Machine Learning group of Université Libre de Bruxelles in collaboration with Worldline. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation, as due to confidentiality issues the original features cannot be provided. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise. Available on [Kaggle](https://www.kaggle.com/mlg-ulb/creditcardfraud), [data.world](https://data.world/vlad/credit-card-fraud-detection) and [datahub.io](https://datahub.io/machine-learning/creditcard).

### [UCI SECOM dataset](https://www.kaggle.com/paresh2047/uci-semcom)
Data from a semi-conductor manufacturing process. A complex modern semi-conductor manufacturing process is normally under consistent surveillance via the monitoring of signals/variables collected from sensors and or process measurement points. However, not all of these signals are equally valuable
in a specific monitoring system. The measured signals contain a combination of useful information, irrelevant information as well as noise. It is often the case
that useful information is buried in the latter two. Engineers typically have a much larger number of signals than are actually required. If we consider each type of signal as a feature, then feature selection may be applied to identify the most relevant signals. The Process Engineers may then use these signals to determine key factors contributing to yield excursions downstream in the process. This will enable an increase in process throughput, decreased time to learning and reduce the per unit production costs.

To enhance current business improvement techniques the application of feature selection as an intelligent systems technique is being investigated.

The dataset presented in this case represents a selection of such features where each example represents a single production entity with associated measured features and the labels represent a simple pass/fail yield for in house line testing, figure 2, and associated date time stamp. Where .1 corresponds to a pass and 1 corresponds to a fail and the data time stamp is for that specific test point. Available on [Kaggle](https://www.kaggle.com/paresh2047/uci-semcom) and the [UCI Machine Learning repository](https://archive.ics.uci.edu/ml/datasets/SECOM).


  
## Using this repository
  - Each dataset and its accompanying material is put in a separate folder.
  - Copies of articles are included for convenience.
  - Non-open-access journals are referenced.
  - Notebooks can be opened directly in Google Colab, to make it easier to get started directly without having to install Anaconda etc.
  
### License

[JADS Discover project](https://www.github.com/dkapitan/jads-discover-projects) by [Daniel Kapitan](https://www.linkedin.com/in/dkapitan) and [Joran Lokkerbol](https://www.linkedin.com/in/joran-lokkerbol-7a68063/) is licensed under under a
[Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

[![CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)]([http://creativecommons.org/licenses/by-sa/4.0/) 
