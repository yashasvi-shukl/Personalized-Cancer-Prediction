<h1> Personalized-Cancer-Prediction </h1>

# Business Problem

#### Data: Memorial Sloan Kettering Cancer Center (MSKCC)
Download training_variants.zip and training_text.zip from Kaggle.

#### Context:
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/discussion/35336#198462

### Problem statement :
### ** Classify the given genetic variations/mutations based on evidence from text-based clinical literature **

### - Real-world/Business objectives and constraints.
- No low-latency requirement.
- Interpretability is important.
- Errors can be very costly.
- Probability of a data-point belonging to each class is needed.

### - Data Overview
- Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/data
- We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that human experts/pathologists use to classify the genetic mutations.
- Both these data files are have a common column called ID
- Data file's information:
    - training_variants (ID , Gene, Variations, Class)
    - training_text (ID, Text)

## Mapping the real-world problem to an ML problem
1. Type of Machine Learning Problem
      There are nine different classes a genetic mutation can be classified into => Multi class classification problem
2. Performance Metric
    - Multi class log-loss ( by source )
    - Confusion matrix
3. Train, CV and Test Datasets
Split the dataset randomly into three parts train, cross validation and test with 64%,16%, 20% of data respectively.

## Featurization techniques used
1. OneHot-Encoding
2. Response Coding (using laplace smoothing)

# Breakdown of techniques used in project:
1. Exploratory Data Analysis
2. Preprocessing of text (cleaning, removing stopwords & merging)
3. Test, Train and Cross Validation Split (We split the data into train, test and cross validation data sets, preserving the ratio of class distribution in the original data set)
4. Prediction using Random Model.
5. Built model for each feature to check how good the feature is in predicting y_i. Features are encoded using onehotencoded and response coding (using laplace smoothing)
6. Trained model on featurized (onehotencoding and response coding) train data and perform prediction on test data.
7. Predicted probability score for each class as Interpretability and confidence is important constraint.
8. Extracted important features

# Result
Random Forest on response coded features seems to be performing best. Below is the result obtained.

![image](https://user-images.githubusercontent.com/22805226/160758557-5717cee2-6d17-43ef-94c4-55c3fb736bc3.png)

![image](https://user-images.githubusercontent.com/22805226/160758608-61d6f6b9-36f9-41a0-a7a0-20049a0d8e9a.png)


