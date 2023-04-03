# Data Science Portfolio

Author - Taylor Chu

Fall 2022

Master of Business analytics

This repository contains the files for the Portfolio task for COMP2200/6200 in S2 2022 @ Macquarie University

The portfolio task consists of 4 parts, using the corresponding datasets:

1. Portfolio Part 1 - Epinions_test_data.csv
Box plot, groupby, removing outliers based on conditions

2. Portfolio Part 2 - Epinions_cleaned_data_portfolio_2.csv
Linear regression model, feature selection, training/test data size split, model accuracy evaluation with MSE and Rsquared

3. Portfolio Part 3 - Portfolio 3.csv 
Ordinal encoding, logistic regression, RFE for feature selection, KNN, Gridsearch CV to find optimal K, plotting error across K values

4. Portfolio Part 4 - Sales-March-2022-quarter.csv
Analysis of house sales data in NSW Mar 21 to Mar 22, trying to predict dwelling type based on mean sales price, post code and sales number. Used logistic regression, RFE, KNN, GridsearchCV, and Gaussian/Multinomial Naive Bayes, with KNN performing the best at 88.9% accuracy.


## Background for Part 4 of Portfolio - Analysis of house sales data in NSW 

Using **house sales data in NSW** department of Family and community services NSW Sales data, I combined the data from 5 consecutive quarters from March 2021 to March 2022. The dataset had postcode information, along with dwelling type (non-strata or strata) and their mean sales price, quartile sales price, number of sales, and quarterly change.

I predicted the class of dwelling type based on postcode, mean sales price and number of sales using different classication models: **logistic regression, KNN and Naive Bayes**. All these models worked relatively well on the dataset, with KNN performing the best at 88.9% accuracy.

What I found from the analysis was that dwelling type can be best predicted by number of sales, using KNN model, followed by postcode and finally mean sales price. This makes sense as whether a house is non-strata or strata is highly correlated with the number of them available for sales. There would be many more strata sales than non-strata.

On the other hand, postcodes can have both non-strata and strata sales, so it's hard to predict whether dwelling type is non-strata or strata just knowing postcode. However, we know that city centeres have a lot more strata than non-strata, while rural areas have more non-strata. That's why the models still did well using postcode as an input. The accuracy was 63.5% with sales number as input, and 68.7% with postcode as input. Eventhough RFE suggested sales number as the best feature, post code seems to work well as well.

Meanwhile, sales price is not a good predictor of dwelling type, as there could be very expensive non-strata houses, as well as expensive strata houses. It is hard to predict type by price, as it could be dependent on where the house is located and what the quality of the house is.
