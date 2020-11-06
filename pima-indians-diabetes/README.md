# Pima Indians Diabetes dataset

Predict the onset of diabetes based on diagnostic measures.

## Data description
This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective is to predict based on diagnostic measurements whether a patient has diabetes.

Several constraints were placed on the selection of these instances from a larger database. In particular, all patients here are females at least 21 years old of Pima Indian heritage.

- Pregnancies: Number of times pregnant
- Glucose: Plasma glucose concentration a 2 hours in an oral glucose tolerance test
- BloodPressure: Diastolic blood pressure (mm Hg)
- SkinThickness: Triceps skin fold thickness (mm)
- Insulin: 2-Hour serum insulin (mu U/ml)
- BMI: Body mass index (weight in kg/(height in m)^2)
- DiabetesPedigreeFunction: Diabetes pedigree function
- Age: Age (years)
- Outcome: Class variable (0 or 1)

## Exercises

### Exercise 1
 - Provide a table with descriptive statistics for all included variables and check:
   - Classes of each of the variables (e.g. factors or continuous variables).
   - Change the class of the "Outcome" variable such that it is a binary factor
   - Descriptive/summary statistics for all continuous variables (e.g. mean, SD, range) and factor variables (e.g. frequencies).
 - Explore missing values
 
### Exercise 2
The variable "Outcome" refers to the presence of diabetes and hence is the variable of interest for our prediction model ("Y" or dependent variable). The frequency of the outcomes (diabetes yes/no) was already determined in the previous code block Please further explore Y in terms of:

  - Describe X-variables separately for both outcome categories 
  - Draw a correlation plot to see all correlations between Y and the independent (numeric) variables 
  - Visualize the relation between Y and a few correlated X-variables 

### Exercise 3
  - Estimate a linear model, LASSO model and a kNN model on the train set. Inspect the outcomes of the model. Which model performs best?
  - Interpret the different models and argue which one is more easily explainable. Use any of the following libraries for interpreting models: [SHAP](https://shap.readthedocs.io/en/latest/), [lime](https://github.com/marcotcr/lime), [sklearn partial dependence plot](https://scikit-learn.org/stable/modules/partial_dependence.html), [ELI5](https://eli5.readthedocs.io/en/latest/)
  

## Acknowledgements
**Spoiler alert:** the links below contain solutions to this project. Make sure you have tried your best before snooping.
  - [PIR's complete ML pipeline tutorial](https://www.kaggle.com/pouryaayria/a-complete-ml-pipeline-tutorial-acu-86)
  - [Ashwini Swain's](https://www.kaggle.com/ash316) has written a [notebook with a comprehensive explaination](https://www.kaggle.com/ash316/ml-from-scratch-part-2)
  - [Parul Pandey's](https://www.kaggle.com/parulpandey) notebook with an excellent explanation of [interpreting machine learning models](https://www.kaggle.com/parulpandey/intrepreting-machine-learning-models).

