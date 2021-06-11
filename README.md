# Drug_Recommendations_Sentiment_Analysis

## Requirements
- python > 3.6
- pandas
- numpy
- matplotlib
- seaborn
- sklearn
- textblob
- Wordcloud
- nltk
- xgboost
- lightgbm  
- spacy

## Problem Definition and Current Practices
  - A single ailment could have several medications and types of medications. 
  - Doctors mostly prescribe handwritten suggestions for any conditions.

## Dataset

  This Drug Review dataset is taken from UCI ML Repository, for more info check: https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+%28Drugs.com%29

## Prediction Metric
  F1 score
  
## Project Outcome
  Top 3-5 drug recommendations for an ailment

## Dataset Description
  1. drugName (categorical): name of drug
  2. condition (categorical): name of condition
  3. review (text): patient review
  4. rating (numerical): 10 star patient rating
  5. date (date): date of review entry
  6. usefulCount (numerical): number of users who found review useful

## Solution Approach
  - Sentiment analysis can be done on the reviews given by user who took the drug.
  - useful count for those reviews can be used as the feedback for our model.

## Data Understanding and Transformations
  * Train and Test data are combined into a single dataset.
  * Shape of the data.
  * Number of columns and their dtypes
  * Null value treatment (Found some Null values in condition column which are of insignificant amount, so I dropped them)
  * Converted date column to appropriate dtype.

## Descriptive Analysis
  * Exploratory Data Analysis is done for each independent column and meaningful insights are captured.
  * Wordclouds are used to visualize some frequently used words in review column for highest and least ratings.
  * From heatmap we can observe the correlation between variables.

## Pre-Processing and Encoding Data
  * An unicode character (&#039;) in review column is removed.(May be a special character that was created while gathering the data)
  * All contractions are expanded.
  * text lowering -> punctuation removal -> lemmatization -> stopwords removal
  * Label Encoding is done for columns condition, drugname.

## Feature Engineering
  * Using textblob sentiment polarity is captured for preprocessed review column.
  * Features like word count, unique word count, punctuation count, upper word count, title word count, stopwords count and mean word length are extracted from original           review column.(Compensating the loss of data in preprocessing)
  * Rating column data is converted in to binary .(1 if rating > 5 and 0 if rating < 5, now this is a classification problem)  

## Model Building
  * Two separate models are built -
    1. using all the extracted features
    2. n-gram model using review column
  * final results are ordered using usefulcount.

## Predictions
  * Finally top - 5 drugnames are predicted for a given ailment.

## Challenges Faced
  * Models may perfom even better if more info like Age of patient, severity of condition, etc are given

## Future Improvements
  * Deep Learning models may be used to reduce the Type - II errors.
  * User interface can be created and continuous feedback from users can be used to improve the model predictions.


