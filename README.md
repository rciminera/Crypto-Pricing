
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


[A Google Slide presentation can be found by clicking this link](https://docs.google.com/presentation/d/1Ckl0IfKMgDoyJidYdW5T5Cj9Ryua9ZXZu3OqbFGXibU/edit#slide=id.ge50b36afca_0_0)

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
- Machine Learning using the Random Forest algorithm and the imblearn and sklearn libraries
- Data visualization using Plotly and Tableau


## Project Deliverables

This project has 4 segments of specific deliverables for each segment due on the following dates: June 27, July 11, July 18, and July 25.  

Deliverables are described below.

### Git Hub Repository

A git hub repository named Crypto-Pricing has been set up with branches for each member of the team according to their deliverables.  Additional branches will be created and merged for specific tasks and then merged into the main branch during the course of the project.

In addition to github communication among the team members will be via slack channel and scheduled zoom calls.

### Machine Learning Model

July 18 Deliverables:

#### Code for the machine learning model that: 
- Preprocesses the data provided from the database load including dropping of nulls
- Feature selection based on data consistency and frequency distribution
- Scaling of the data using Standard Scaler
- Use of the Random Forest Model due to it's efficiency and feature importance ranking

#### Preliminary data preprocessing:
- All null values were dropped to prepare the data for training.
- Columns such as "ATH" (all time high) were dropped as non important.
#### Preliminary feature engineering and preliminary feature selection:
- The features selected are ('current_price','circulating_supply', 'fully_diluted_valuation', 'total_volume', 'total_supply', 'market_cap')
- The reason for selecing these features are: 
    - We have the most precise and trustworthy data for these categories
    - We also think that these features will enable us to that these are both good indicators into the financial side of cryptos, and also lend themselves to work well in our model.
- Sentiment data features will also be added to the model as we believe that social media has a unique influence on the crypto market and we are curious to see if there is some predictable trend between interaction and reactions and how well a coin does in the market.
#### Description of how data was split into training and testing sets
- We will use current price and market cap as our testing sets and then the rest as our trainable data. The reason for this is that we are interested in seeing if our model is able to predict the price and how well a coin is doing so we want to make sure that we train our model to be tested against the features/data that we are targeting to predict.
#### Explanation of model choice, including limitations and benefits
- We will be using a random forest model for a few reasons it is Robust to outliers, Works well with non-linear data, Better accuracy than other classification algorithms.
- A couple of things that we do need to be careful about are, Random forests are found to be biased while dealing with categorical variables and Not suitable for linear methods with a lot of sparse features. they also train slowly but we have plenty of time to train our model.
### Database

July 18 Deliverables:

A database has been created with three tables:
- An ERD was created and a database schema were created using Postgre and ported to AWS DB


<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/QuickDBD-export%20.png" width = "500" >

<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/crypto_merge_data.png" width = "200" >

- Colab used to load extract data into 2 tables which were then joined using SQL Alchemy into a third table for ML processing

[The notebook link can be found here](https://github.com/rciminera/Crypto-Pricing/blob/main/Notebooks/crypto.ipynb)

- A csv of the merged database was also created as future input to Tableau visualization

### Dashboard

A story board has been created using Google slides
Interactive elements will include coin selection and ability to visualize coins by category and performance


## Summary

It is our desire to build a machine learning model to predict future prices over a 12 month horizon with an accuracy of 75% or higher.
