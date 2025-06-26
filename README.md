# CODSOFT Internship Projects

This repository includes the work I completed as part of the CODSOFT Data Science Internship.  
During the internship, I worked on machine learning projects that helped me build a deeper understanding of data analysis, model development, and the practical applications of machine learning using Python.

This README describes **Task 2: Movie Rating Prediction with Python**.

---

# Task 2: Movie Rating Prediction with Python

## Project Overview

This project focuses on building a regression model to predict the IMDb rating of a movie based on key attributes such as its genre, director, and lead actor.  
By analyzing historical movie data, the goal is to estimate the ratings provided by users or critics.  
This task provides hands-on experience with data preprocessing, feature engineering, and model evaluation in the context of real-world categorical data.

---

## What I Did

- Loaded and cleaned the movie dataset  
- Analyzed relationships between movie ratings and categorical features like genre, director, and lead actor  
- Applied one-hot encoding to convert categorical variables into numerical features  
- Built and trained regression models using:
  - Linear Regression  
  - Random Forest Regressor  
- Evaluated model performance using Mean Absolute Error (MAE), R-squared score, and visualizations  
- Created sample input functionality to predict the rating of new movies based on user-defined attributes

---

## What I Observed

- Certain directors and actors consistently appeared in movies with higher ratings  
- Genre played an influential role in predicting ratings, especially genres like Drama, Thriller, and Action  
- The Random Forest model performed better than Linear Regression by capturing nonlinear relationships and interactions  
- One-hot encoding was more effective than label encoding due to the categorical nature of the data  

---

## Dataset Description

Each row in the dataset represents a movie and contains the following features:

- `Genre`: The primary genre of the movie (e.g., Action, Comedy, Drama)  
- `Director`: The name of the director  
- `Actor 1`: Lead actor/actress in the movie  
- `Rating`: IMDb rating of the movie (target variable)

---

## Key Steps in the Project

### 1. Data Preprocessing

- Handled duplicates and null values  
- Standardized column names and formats  
- Applied `pd.get_dummies()` for one-hot encoding of categorical features  

### 2. Exploratory Data Analysis (EDA)

- Plotted distribution of IMDb ratings  
- Visualized average ratings across genres, directors, and actors  
- Identified top and bottom performers by rating trends

### 3. Model Training

- Split the data into training and test sets using `train_test_split`  
- Trained two regression models:
  - Linear Regression (baseline)  
  - Random Forest Regressor (improved model)

### 4. Evaluation

- Used R-squared and Mean Absolute Error for evaluation  
- Visualized actual vs predicted ratings to analyze performance

---

## Sample Prediction

You can predict ratings of new movies using this sample code:

```python
import pandas as pd

# Create sample input row with one-hot encoded structure
sample_input = pd.DataFrame(0, index=[0], columns=model.feature_names_in_)
sample_input['Genre_Action'] = 1
sample_input['Director_Christopher Nolan'] = 1
sample_input['Actor 1_Leonardo DiCaprio'] = 1

# Predict the movie rating
predicted_rating = model.predict(sample_input)
print("Predicted Movie Rating:", round(predicted_rating[0], 2))
