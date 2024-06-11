# Fuel Efficiency Regression Model

## Overview
This project investigates the factors affecting fuel efficiency in vehicles. Using a dataset from Carnegie Mellon University's StatLib data collection, we perform a multiple linear regression analysis to identify the most significant predictors of miles per gallon (mpg). Additionally, we apply statistical tests and transformations to ensure the reliability and accuracy of our model.

## Table of Contents
- [Overview](#overview)
- [Introduction](#introduction)
- [Datasets](#datasets)
- [Methodology](#methodology)
- [Techniques Used and Their Justification](#techniques-used-and-their-justification)
- [Guiding Questions and Visualizations](#guiding-questions-and-visualizations)
- [Results](#results)
- [Things to Note](#things-to-note)
- [Acknowledgments](#acknowledgments)
- [References](#references)

## Introduction
The daily commute for many individuals requires the use of a motor vehicle, and gas-powered vehicles remain the most common method of transportation. This report aims to identify the features of a car that have the most significant effect on its fuel efficiency. We focus on the independent variable, miles per gallon (mpg), and its relationship with dependent variables such as the number of cylinders, engine displacement, horsepower, weight, acceleration, and the car's origin (American, European, Japanese).

## Datasets
We used the "Fuelcar" dataset, which contains 399 rows and 9 columns. The dataset was obtained from Carnegie Mellon University and is publicly available for educational purposes. It includes the following variables:
- mpg: Fuel efficiency measured in miles per gallon (Quantitative)
- cylinders: Number of cylinders in the engine (Qualitative)
- displacement: Engine displacement in cubic inches (Quantitative)
- horsepower: Horsepower (Quantitative)
- weight: Vehicle weight in pounds (Quantitative)
- acceleration: Time to accelerate from 0 to 60 mph in seconds (Quantitative)
- model.year: Model year (Qualitative)
- origin: Origin of the car (1: American, 2: European, 3: Japanese) (Qualitative)
- car.name: Car name (Qualitative)

## Methodology
We performed multiple linear regression analysis to determine the significance of each predictor on fuel efficiency (mpg). The process involved:
1. Creating a full model with all predictors.
2. Conducting stepwise regression, backward elimination, and forward selection procedures.
3. Checking for multicollinearity using VIF (Variance Inflation Factor).
4. Creating reduced models based on significance tests and multicollinearity results.
5. Testing interaction effects between variables.
6. Transforming the data using Box-Cox transformation to meet model assumptions.

## Techniques Used and Their Justification
### Interactions
- **Use:** Introducing interaction terms to account for the combined effect of two or more variables.
- **Justification:** Helps capture non-additive relationships.

### Individual t-tests
- **Use:** Testing the hypothesis that the coefficient for a specific variable is significantly different from zero.
- **Justification:** Determines the significance of individual predictors.

### Global and Partial F-Tests
- **Use:** Assessing the overall significance of the regression model and subsets of variables.
- **Justification:** Ensures the model as a whole is significant and evaluates the importance of specific variables.

### Statistical Tests of Residuals
- **Use:** Diagnostic tests to assess model assumptions.
- **Justification:** Ensures residuals meet the assumptions of the regression model.

## Guiding Questions and Visualizations
### Guiding Question 1: Is CPI correlated with Average Income for Canada?
- **Visualization:** Scatter plots and linear regression lines to examine the correlation between CPI and Average Income. Linear regression analysis and assumption tests (normality and homoscedasticity).

### Guiding Question 2: Are there any income disparities between different provinces?
- **Visualization:** Bar plots comparing average income across selected provinces (ON, BC, NS, PEI). Statistical tests to determine significant differences in income means.

## Results
### Full Model
- The p-value for the full model is 2.2e-16, indicating a significant relationship between the predictors and mpg.
- Displacement and acceleration were found to be non-significant and were removed in the reduced model.

### Reduced Model
- Two reduced models were created: one with and one without the cylinders variable.
- The model with the cylinders variable was found to be better despite multicollinearity issues.

### Interaction Model
- An interaction effect was found between horsepower and origin, leading to the inclusion of this interaction term in the model.

### Higher Order Models
- A Box-Cox transformation was applied to address issues with normality and homoscedasticity.
- The transformed model showed improved adjusted R-squared and reduced standard error.

## Things to Note
- The analysis treated the dataset as sample data and focused on two variables: CPI and Average Income.
- An alpha value of 0.05 was used for all statistical tests.
- The Box-Cox transformation was crucial in meeting model assumptions and improving prediction accuracy.

## Acknowledgments
This project was inspired by various statistical and data science resources. Special thanks to the open-source community for providing the tools and libraries used in this project. We also acknowledge Carnegie Mellon University for providing the dataset used in this analysis.

# References
- StatLib - Datasets Archive: http://lib.stat.cmu.edu/datasets/
