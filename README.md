# Project_4

## Overview
This project uses sentiment analysis and builds supervised machine learning models to predict the outcome of positive versus negative ratings based on their corresponding reviews.

## Business Understanding
McDonald's is the most famous American fast food chain, with stores all over the country. This data was scraped from Google reviews of various McDonald's stores and what people thought. This project aims to better understand what makes a store a positive or negative experience. 

## Repository Navigation
The repository has three notebooks and a data folder. You will find the appropriate information within each specific file.

Data
- McDonald_s_Reviews.csv
- cleaned.csv
- processed.csv

Notebooks
- Data Cleaning Notebook
- Pre-processing Notebook
- Final Notebook

## Presentation and Data Source
- McDonald's Store Reviews from Kaggle - [Link](https://www.kaggle.com/datasets/nelgiriyewithana/mcdonalds-store-reviews/data)
- Presentation - [Link](https://docs.google.com/presentation/d/1OddwYnX868sd40jGoYtPFh3qaavq7Pyz0MscA0Kis3s/edit?usp=sharing)

## Data and Model Analysis
The data for this project has been cleaned and sorted for the final analysis.
Many tools were used in this process of analysis, including but not limited to pandas, sklearn, nltk, etc.
After cleaning the data, I set the target variable to "nps_rating" as its values are binary (0 or 1) where 0 means negative, and 1 means positive.
This was done because even after addressing class imbalance, the original models (ComplementNB, MultinomialNB) had a difficult time accuractly predicting the more neutral ratings (2,3,4).
From here, I generated wordclouds to get a sense of the most common terms for both negative and positive reviews.
For negative reviews, the terms that stood out were: order, food, service, wait, time, bad, etc.
For positive reviews, the terms that stood out were: good, food, service, excellent, fast, great, clean, etc.
Next, I ran three models including: Logistic Regression, Random Forest, and Gradient Boosting Classifier.
For each of the models, I used a Count Vectorizer and ran a Grid Search to determine the best parameters specific to that model.
The best performing model was the Random Forest Classifier, with an accuracy of 89%.
This model's Count Vectorizer used a min df = 0.003, and the classifiers parameters worked with n_estimators=200.

## Conclusion
By the end of the process, the Random Forest Classifier was the most effective model, with a test set accuracy score of 0.89, n_estimators (number of trees in the forest) set to 200, and no max depth.
The key features were "rating" and "review".
To improve this model further, I would like to dig deeper into features like "latitude", "longitude", and "review_time" to get a better sense of which McDonald's stores performed well and which ones didn't, and see if there are other factors at play (economic conditions, time of day, urban evironments, traffic, etc.)
