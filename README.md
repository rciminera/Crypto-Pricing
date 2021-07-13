
<img src="https://github.com/rciminera/Crypto-Pricing/blob/main/Images/currency_header.png" width = "1000" >

# Crypto-Pricing

###  Collaborators:  
Bimala Basnet,
Cameron Ewan,
Bob Ciminera


## Overview

The purpose of this project is to determine if there is a clustering of factors that drive change in crypto currency pricing based on the past 12 month change in pricing using USD as the constant exchange currency.

 The team will develop a machine learning model and attempt to predict trajectory of pricing based on a dataset of features gathered from various sources.  These sources include API inputs from coingecko.com as well as other sources that may be necessary to build a rich feature set.

This topic was selected based on our belief that cryptocurrencies and their associated blockchain technologies are a new model for computing and represent a significant opportunity for value and wealth creation.  

The questions we hope to answer with the data are as follows:

- What features are indicative of the pricing of a specific coin?
- Are there specific classes of coins that have better pricing performance?
- Are there any other data that we would need beyond our initial scope to create a better model?


[A Google Slide presentation can be found by clicking this link](https://docs.google.com/presentation/d/1Ckl0IfKMgDoyJidYdW5T5Cj9Ryua9ZXZu3OqbFGXibU/edit#slide=id.p3)

## Data Sources

Sources of data for the analysis include API's from:

- www.coingecko.com for coin and market data
- www.lunarcrush.com for coin sentiment data
- www.messari.io for coin and market data

In addition other research sources were reviewed to understand categorization of crypto currencies eg https://medium.com/coinmonks/crypto-categories-you-need-to-know-9e78a5bdebc7.

## Methods

The following technology, tools, and algorithms will be used for this project

- Data extract using JSON within a Jupyter notebook with Pandas
- Cleaning data for table loads and machine learning pre-processing using Jupyter notebook
- Data load using Postgre, Colab, and AWS
- Machine Learning using the Random Forest algorithm and the imblearn and sklearn libraries
- Data visualization using Plotly and Tableau


## Project Deliverables

This project will have 4 segments of specific deliverables for each segment due on the following dates: June 27, July 11, July 18, and July 25.  

Deliverables are described below.

### Git Hub Repository

A git hub repository named Crypto-Pricing has been set up with branches for each member of the team according to their deliverables.  Additional branches will be created and merged for specific tasks and then merged into the main branch during the course of the project.

In addition to github communication among the team members will be via slack channel and scheduled zoom calls.

### Machine Learning Model

July 11 Deliverables:

#### Code for the machine learning model that: 
- Preprocesses the data provided from the database load including dropping of nulls
- Feature selection based on data consistency and frequency distribution
- Scaling of the data using Standard Scaler
- Use of the Random Forest Model due to it's efficiency and feature importance ranking

#### Description of preliminary data preprocessing:
- The first thing that we needed to do was to drop all our null values so that we can actually use our data for the model.
- Then we needed to drop certain columns that we would not be using for our model so that we are only hvaing to deal with the data that we actuualy need.
#### Description of preliminary feature engineering and preliminary feature selection:
- The features that we are selecting are ('current_price','circulating_supply', 'fully_diluted_valuation', 'total_volume', 'total_supply', 'market_cap')
- The reason that we selected these are that we have the most precise and trustworthy data for these categories. We also think that since we are trying to find a way to predict the crypto market based on certain features we believe that these are both good indicators into the financial side of cryptos, but also lend themselves to work well in our model.
- We also plan to include some sentiment data as we believe that socila media has a unique influnece on the crypto market and we are curious to see if there is some predictable trend between interaction and reactions and how well a coin does in the market.
#### Description of how data was split into training and testing sets
- We will use current price and market cap as our testing sets and then the rest as our trainable data. The reason for this is that we are interested in seeing if our model is able to prectit the price and how well a coin is doing so we want to make sure that we train our model to be tested against the features/data that we are targeting to predict.
#### Explanation of model choice, including limitations and benefits
- We will be using a random forest model for a few reasons it is Robust to outliers, Works well with non-linear data, Better accuracy than other classification algorithms.
A couple of things that we do need to be careful about are, Random forests are found to be biased while dealing with categorical variables and Not suitable for linear methods with a lot of sparse features. they also train slowly but we have plenty of time to train our model.
### Database

July 11 Deliverables:

A database has been created with three tables:
- An ERD was created and a database schema were created using Postgre and ported to AWS DB
- Colab used to load extract data into 2 tables which were then joined using SQL Alchemy into a third table for ML processing
- A csv of the merged database was also created as future input to Tableau visualization

### Dashboard

A story board has been created using Google slides
INteractive elements will include coin selection and ability to visualize coins by category and performance


## Summary

It is our desire to build a machine learning model to predict future prices over a 12 month horizon with an accuracy of 75% or higher.
