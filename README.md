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
In this section, I will explore significant properties within the data by performing an exploratory data analysis.

### Active Users
I found that the most active user in the dataset has no more than 3,000 records. Compared to the total of over 1 million records, this is not a significant portion. Therefore, we need to consider whether a particular user might disproportionately influence the overall predictions. The same applies to the "ProductId" column, where the most frequently occurring entry also has no more than 3,000 records.

## Missing Value Detection
-----
As the overview suggests, there are missing values in our dataset. It is essential to investigate their properties to ensure they do not cause distortions in our analysis.

Except for "Score" (our target variable containing test data), it appears there are almost no missing values in other features. According to the heatmap, missing values only exist in the "Summary" and "Text" columns, which are not strongly correlated with one another. Thus, I can apply simple imputation without further complications.

## Downsize the Data Whose Score is 5.0/5.0
-----
As previously shown, there are an excessive number of records with a score of 5.0/5.0. To prevent the predictor from biasing towards this score when predicting unknown records, I will reduce the scale of the dataset containing these scores.

## One-hot Encoding to Categorical Features
-----
Encoding is a method to digitize categorical features. I opted for one-hot encoding over label encoding because label encoding assigns unique identifiers based on their order of appearance, which may misrepresent non-measurable features. The only downside of one-hot encoding is its high memory consumption, which I will address.

## Impute the Missing Values by Making Blanks as Void Strings
-----
This is the simplest imputation method, where missing values are replaced with empty strings.

## Calculate TF-IDF and Vectorize
-----
This baseline step involves vectorizing the text values using the Term Frequency-Inverse Document Frequency (TF-IDF) method, allowing us to extract more information and achieve higher accuracy in our predictions.

## Model Training
-----
In this section, I will implement machine learning algorithms to train the model using the processed data. The chosen algorithms will be evaluated based on their performance metrics, such as accuracy, precision, recall, and F1-score. Various techniques, including cross-validation, will be applied to ensure the model's robustness.

## Results
-----
The model's performance will be analyzed and visualized using confusion matrices, ROC curves, and other relevant metrics. The results will be compared across different algorithms to determine the most effective model for predicting movie ratings.

## Conclusion
-----
The project demonstrates the potential to leverage user reviews and associated features to predict star ratings for Amazon movies. The insights gained could contribute to improving recommendation systems and understanding user preferences. Future work could explore additional features, such as sentiment analysis of the text data or incorporating other user behaviors.
