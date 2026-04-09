# Lab7-Logistic-Regression-Assignment

# Logistic Regression on the Advertising Dataset

## Overview

This project applies a Logistic Regression model to predict whether a user clicks on an advertisement based on demographic and behavioral features from the advertising dataset.

## Objective

The main objective is to classify users into:

* 0: Did not click on the ad
* 1: Clicked on the ad

## Dataset

The dataset used in this project is `advertising.csv`.

It includes the following columns:

* Daily Time Spent on Site
* Age
* Area Income
* Daily Internet Usage
* Ad Topic Line
* City
* Male
* Country
* Timestamp
* Clicked on Ad

## Steps Performed

### 1. Importing Libraries

The required libraries were imported:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn

### 2. Loading the Data

The dataset was loaded into a pandas DataFrame named `ad_data`.

### 3. Data Exploration

Initial exploration was performed using:

* `head()`
* `info()`
* `describe()`

This helped in understanding the structure, data types, and summary statistics of the dataset.

### 4. Exploratory Data Analysis (EDA)

Several visualizations were created using seaborn and matplotlib, including:

* Histogram of Age
* Jointplot of Age vs Area Income
* KDE jointplot of Age vs Daily Time Spent on Site
* Jointplot of Daily Time Spent on Site vs Daily Internet Usage
* Pairplot with hue defined by `Clicked on Ad`

These plots helped reveal clear patterns and separation between users who clicked on the ad and those who did not.

### 5. Feature Selection

The following numerical features were selected for training:

* Daily Time Spent on Site
* Age
* Area Income
* Daily Internet Usage
* Male

Target variable:

* Clicked on Ad

### 6. Train-Test Split

The data was split into training and testing sets using:

* 70% training data
* 30% testing data
* `random_state=101`

### 7. Model Training

A Logistic Regression model was trained on the selected features.

### 8. Prediction and Evaluation

Predictions were made on the test set, and the model was evaluated using:

* Classification Report
* Confusion Matrix

## Results

The model achieved strong performance, with an accuracy of approximately **93%**.

### Classification Report Summary

* Precision: high for both classes
* Recall: high for both classes
* F1-score: balanced and strong
* Accuracy: 0.93

### Confusion Matrix

```text
[[149   8]
 [ 14 129]]
```

## Tools and Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## Notes

* Only numerical features were used for model training.
* Text-based columns such as `Ad Topic Line`, `City`, `Country`, and `Timestamp` were excluded from the model.
* A convergence warning may appear when training Logistic Regression with the default number of iterations. This can be improved by setting:
  `LogisticRegression(max_iter=1000)`
