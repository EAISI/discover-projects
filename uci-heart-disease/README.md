![](https://github.com/jads-nl/discover-projects/blob/main/uci-heart-disease/jesse-orrico-Us3AQvyOP-o-unsplash.jpg)

## Context

This database contains 76 attributes, but all published experiments refer to using a subset of 14 of them. In particular, the Cleveland database is the only one that has been used by ML researchers to this date. The "goal" field refers to the presence of heart disease in the patient. It is integer valued from 0 (no presence) to 4.

## Content
Attribute Information:

```code
1. age
2. sex
3. chest pain type (4 values)
4. resting blood pressure
5. serum cholestoral in mg/dl
6. fasting blood sugar > 120 mg/dl
7. resting electrocardiographic results (values 0,1,2)
8. maximum heart rate achieved
9. exercise induced angina
10. oldpeak = ST depression induced by exercise relative to rest
11. the slope of the peak exercise ST segment
12. number of major vessels (0-3) colored by flourosopy
13. thal: 3 = normal; 6 = fixed defect; 7 = reversable defect
```

The names and social security numbers of the patients were recently removed from the database, replaced with dummy values. One file has been "processed", that one containing the Cleveland database. All four unprocessed files also exist in this directory.


## Exercises

### Exercise 1
Provide a table with descriptive statistics for all included variables and check:

  - Classes of each of the variables (e.g. factors or continuous variables)
  - Change the class of the "target" variable such that it is a binary factor
  - Descriptive/summary statistics for all continuous variables (e.g. mean, SD, range) and factor variables (e.g. frequencies)
  - Explore missing values
  
### Exercise 2
The variable "target" refers to the presence of heart disease and hence is the variable of interest for our prediction model ("Y" or dependent variable). The frequency of the outcomes (heart disease yes/no) was already determined in the previous code blocks. Please further explore Y in terms of:

  - Describe X-variables separately for both outcome categories
  - Draw a correlation plot to see all correlations between Y and the independent (numeric) variables
  - Visualize the relation between Y and a few correlated X-variables (i.e. create boxplot or scatterplot)

### Exercise 3

  - Estimate a linear model, LASSO model, a kNN model and a Random Forests model
  - Assess which model performs best

## Acknowledgements
Creators:

  - Hungarian Institute of Cardiology. Budapest: Andras Janosi, M.D.
  - University Hospital, Zurich, Switzerland: William Steinbrunn, M.D.
  - University Hospital, Basel, Switzerland: Matthias Pfisterer, M.D.
  - V.A. Medical Center, Long Beach and Cleveland Clinic Foundation: Robert Detrano, M.D., Ph.D.

Donor: David W. Aha (aha@ics.uci.edu)

Photo by [Jesse Orrico](https://unsplash.com/@jessedo81?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/collections/9716108/doctors?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)
