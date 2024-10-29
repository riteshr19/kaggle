# Amazon Movie Rating Prediction

## Overview
This project investigates the relationship between star ratings and user reviews on Amazon Movie Reviews. Utilizing various features, such as a unique identifier for the product/user, the number of users who found the review helpful, the timestamp of the review, a brief summary, and the full text of the review, the goal is to predict the star rating score. Successful implementation could aid in estimating the popularity of unlisted movies and improving recommendation systems.

[Competition Link](http://www.kaggle.com/c/bu-cs506-fall-2024-midterm)

## Table of Contents
- [Exploratory Data Analysis (EDA)](#eda)
- [Missing Value Detection](#missing-value-detection)
- [Data Downsizing](#downsize-the-data-whose-score-is-50)
- [One-hot Encoding to Categorical Features](#one-hot-encoding-to-categorical-features)
- [Imputation of Missing Values](#impute-the-missing-values-by-making-blanks-as-void-strings)
- [TF-IDF Calculation and Vectorization](#calculate-tf-idf-and-vectorize)
- [Model Training](#model-training)
- [Results](#results)
- [Conclusion](#conclusion)
- [Acknowledgments](#acknowledgments)

## EDA
-----
In this section, I explored significant properties within the data through exploratory data analysis.

### Active Users
I found that the most active user in the dataset has at most 3,000 records. Compared to the total of over 1 million records, this is a small portion. Therefore, I considered whether a particular user might disproportionately influence the predictions. The same applies to the "ProductId" column, where the most frequently occurring entry also has no more than 3,000 records.

## Missing Value Detection
-----
As identified, there are missing values in our dataset. I needed to investigate their properties to ensure they did not cause distortions in the analysis.

Except for "Score" (our target variable containing test data), it appears there are almost no missing values in other features. According to the heatmap, missing values only exist in the "Summary" and "Text" columns, which are not strongly correlated with one another. So, I applied simple imputation without any more complications.

## Downsize the Data Whose Score is 5.0/5.0
-----
As previously shown, there are an excessive number of records with a score of 5.0/5.0. To prevent the predictor from biasing towards this score when predicting unknown records, I reduced the scale of the dataset containing these scores.

## One-hot Encoding to Categorical Features
-----
I implemented encoding as a method to digitize categorical features. I opted for one-hot encoding over label encoding because label encoding assigns unique identifiers based on their order of appearance, which may misrepresent non-measurable features. The only downside of one-hot encoding is its high memory consumption, which I addressed.

## Impute the Missing Values by Making Blanks as Void Strings
-----
I employed This simplest imputation method, where missing values are replaced with empty strings.

## Calculate TF-IDF and Vectorize
-----
In this baseline step, I vectorized the text values using the Term Frequency-Inverse Document Frequency (TF-IDF) method, allowing us to extract more information and achieve higher accuracy in our predictions.

## Model Training
-----
I implemented machine-learning algorithms in this section to train the model using the processed data. The chosen algorithms were evaluated based on their performance metrics: accuracy, precision, recall, and F1-score. I applied various techniques, including cross-validation, to ensure the model's robustness.

## Results
-----
I analyzed the model's performance and visualized the results using confusion matrices, ROC curves, and other relevant metrics. The results were compared across different algorithms to determine the most effective model for predicting movie ratings.

## Conclusion
-----
This project demonstrates the potential to leverage user reviews and associated features to predict star ratings for Amazon movies. The insights gained could contribute to improving recommendation systems and understanding user preferences. Future work could explore additional features, such as sentiment analysis of the text data or incorporating other user behaviors.
