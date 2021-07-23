
<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/currency_header.png" width = "1000" >

# Crypto-Pricing

###  Collaborators:  
Bimala Basnet,  Cameron Ewan,Bob Ciminera

## Overview

The purpose of this project is to determine whether crypto currency pricing be predicted with an accuracy >= 75% using machine learning techniques?

 The team will develop a machine learning model and attempt to predict trajectory of pricing based on a dataset of features gathered from various sources.  

This topic was selected based on our belief that cryptocurrencies and their associated blockchain technologies are a new model for computing and represent a significant opportunity for value and wealth creation.  

The questions we hope to answer with the data are as follows:

- What features are indicative of the pricing of a specific coin?
- Are there specific classes of coins that have better pricing performance?
- Are there any other data that we would need beyond our initial scope to create a better model?


[Google Slide Presentation](https://docs.google.com/presentation/d/1Ckl0IfKMgDoyJidYdW5T5Cj9Ryua9ZXZu3OqbFGXibU/edit#slide=id.ge499c0d902_0_0)


[Tableau Crypto Pricing Visualizations](https://public.tableau.com/app/profile/bob.ciminera/viz/Crypto-pricing/CryptoYTDGrowth)
## Data Sources

Sources of data for the analysis include API's from:

- www.coingecko.com for coin and market data
- www.lunarcrush.com for coin sentiment data
- www.messari.io for coin and market data

In addition other research sources were reviewed to understand categorization of crypto currencies eg https://medium.com/coinmonks/crypto-categories-you-need-to-know-9e78a5bdebc7.

## Methods

The following technology, tools, and algorithms used for this project

- Data extract using JSON within a Jupyter notebook with Pandas
- Cleaning data for table loads and machine learning pre-processing using Jupyter notebook
- Data load using Postgre, Colab, and AWS
- Machine Learning using the Random Forest Regressor algorithm.
- Data visualization using Tableau


## Project Deliverables

This project had 4 segments of specific deliverables for each segment due on the following dates: June 27, July 11, July 18, and July 25.  

Deliverables are described below.

### Git Hub Repository

A git hub repository named Crypto-Pricing was set up with branches for each member of the team according to their deliverables.  Additional branches were created and merged for specific tasks and then merged into the main branch during the course of the project.

### Machine Learning Model

Final Deliverables:

#### Code for the machine learning model that: 
- Preprocessed the data provided from the database load including dropping of nulls
- Feature selection based on data consistency and frequency distribution
- Scaling of the data using Standard Scaler
- Use of the Random Forest Regressor Model due to it's efficiency and feature importance ranking

#### Data preprocessing:
- After a number of attempts to find complete data a data set of 832 crypto currencies with 14 features was extacted, transformed, and then loaded to an AWS databse for processing by the ML model.
- All null values were dropped to prepare the data for training.
- Columns such as "ATH" (all time high) were dropped as non important.
#### Feature engineering and selection:
- The features selected are ('current_price','circulating_supply', 'fully_diluted_valuation', 'total_volume', 'total_supply', 'market_cap')
- The reason for selecing these features are: 
    - We have the most precise and trustworthy data for these categories
    - We also think that these features will enable us to that these are both good indicators into the financial side of cryptos, and also lend themselves to work well in our model.
- Sentiment data features were originally planned for the model but due to the lack of coins with this data, we eliminated these features from the model.   We continue to believe that social media has a unique influence on the crypto market and we are curious to see if there is some predictable trend between interaction and reactions and how well a coin does in the market.

The following ERD shows the features used in the model.  Note that the target feature was PercentageChangeYTDUsd

<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/QuickDBD-export-messari.png" width = "200" >


#### Description of how data was split into training and testing sets
- We will use current price and market cap as our testing sets and then the rest as our trainable data. The reason for this is that we are interested in seeing if our model is able to predict the price and how well a coin is doing so we want to make sure that we train our model to be tested against the features/data that we are targeting to predict.
#### Explanation of model choice, including limitations and benefits
The Random Forest Model was chosen for a few reasons:
-  It is robust to outliers
-  Works well with non-linear data, Better accuracy than other classification algorithms.
Areas we need to be careful about are:
- Random forests are found to be biased while dealing with categorical variables and Not suitable for linear methods with a lot of sparse features
- Model trains slowly



#### Results

The accuracy score came in at 71.23% albeit with a wide Mean Absolute Error of 436.76 degrees.  Please note that the Random Forest Regressor does not support creating a confusion matrix.


<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/ML_code_snippet.png" width = "500" >


The most important features were:


<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/feature_importance.png" width = "500" >



### Database


A database was created with four tables:
- An ERD was created and a database schema were created using Postgre and ported to AWS DB


<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/QuickDBD-export%20.png" width = "500" >

<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/crypto_merge_data.png" width = "200" >

Please see ML secion above for Messari extract ERD.

- Colab used to load extract data into 2 tables which were then joined using SQL Alchemy into a third table for ML processing

[The notebook link for the initial loads can be found here](https://github.com/rciminera/Crypto-Pricing/blob/main/Notebooks/crypto.ipynb)


- A csv of the merged database was also created as input to Tableau visualization

### Dashboard

A story board has been created using Google slides
Interactive elements will include coin selection and ability to visualize coins by category and performance


## Summary

Despite initial problems finding sufficient complete data, the Machine Learning Model delivered 70% Accuracy, albeit with wide error
- Features such as Supply and Market Cap indicative of Pricing Prediction
- Regression Model Problematic for Pricing Analysis

Our analysis indicated that Payments and Finance Coins have performed the best in terems of pricing appreciation.
- New cryptocurrency coins with low entry price have highest rate of appreciation eg. Dogecoin

Overall. the cryptocurrency market grew at 33% YTD despite recent downturn from record highs still makes this an effort worth refining
- Further analysis on coins with strong use cases eg decentralized finance, gaming, and others is required to find the best bets.
- Although sentiment data was ultimately not used in the model, we beleive there is an opportunity to improve on that in the future.





