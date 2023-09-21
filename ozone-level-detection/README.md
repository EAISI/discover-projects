# Ozone Level Detection

Note - this is a relatively complex project, and recommended in case you are more advanced. When starting with Data Science/Python, I suggest to start with Ames (regression) or Heart Disease of PIMA Indians (classification).

## Abstract
Much work on skewed, stochastic, high dimensional, and biased datasets usually implicitly solve each problem separately. Recently, we have been approached by Texas Commission on Environmental Quality (TCEQ) to help them build highly accurate ozone level alarm forecasting models for the Houston area, where these technical difficulties come together in one single problem. Key characteristics of this problemthat is challenging and interesting include: 1) the dataset is sparse (72 features, and 2% or 5% positives depending on the criteria of “ozone days”), 2) evolving over time from year to year, 3) limited in collected data size (7 years or around 2500 data entries), 4) contains a large number of irrelevant features, 5) is biased in terms of “sample selection bias”, and 6) the true model is stochastic as a function of measurable factors. Besides solving a difficult application problem, this dataset offers a unique opportunity to explore new and existing data mining techniques, and to provide experience, guidance and solution for similar problems. Our main technical focus addresses on how to estimate reliable probability given both sample selection bias and a large number of irrelevant features, and how to choose the most reliable decision threshold to predict the unknown future with different distribution.

## Challenge
Train a classifier that can predict 8-hour ozone days with a performance of at least 50% precision with 50% recall.

## References
- [OpenML](https://www.openml.org/d/1487)
- [UCI](https://archive.ics.uci.edu/ml/datasets/ozone+level+detection)
