![5d07c76a696bfc4b3cb88294_cryptocurrency](https://user-images.githubusercontent.com/75695931/123559701-9a972000-d76b-11eb-84b8-0a63a1619eb3.jpg)
# Crypto-Pricing

###  Collaborators:  
Bimla Basnet,
Cameron Ewan,
Bob Ciminera


## Overview

The purpose of this project is to determine if there is a clustering of factors that drive pricing of crypto currencies over a specific time period (to be determined).  The team will develop a machine learning model based on inputs from a variety of sources.  These sources will be used to create a database and interactive dashboard.

The reason this topic was selected is based on our belief that cryptocurrencies and their associated blockchain technologies are a new model for computing and represent a significant opportunity for value and wealth creation.  While investing in this technology is still speculative due to the pricing volatility, we are interested in determining if there are features that could be predictive of the future pricing of a specific coin.

The questions we hope to answer with the data are as follows:

What features are indicative of the pricing of a specific coin?
Are there specific classes of coins that have better pricing performance?
Are there any other data that we would need beyond our initial scope to create a better model?

## Project Deliverables

### Git Hub Repository

A git hub repository named Crypto-Pricing has been set up with branches for each member of the team according to their roles.  Additional branches will be created and merged for specific tasks and then merged into the main branch during the course of the project.

Communication among the team members will be via slack channel and scheduled zoom calls.

June 27 Deliverables:
- At least one branch for each team member
- Each team member has at least four commits from the duration of the first segment
- Note: The descriptions and explanations required in all other project deliverables should also be in your README.md as part of your outline, unless otherwise noted.

### Machine Learning Model

June 27 Deliverables:

A machine learning model will be created by to stand in for the final machine learning model and will accomplish the following:
- Takes in data in from the provisional database
- Outputs label(s) for input data

### Database

June 27 Deliverables:

A provisional database will be created as a mockup for the final database to accomplish the following:
- Sample data that mimics the expected final database structure or schema
- Draft machine learning module is connected to the provisional database



## Blockchain Technology Background

Historically, new models of computing have tended to emerge every 10–15 years: mainframes in the 60s, PCs in the late 70s, the internet in the early 90s, and smartphones in the late 2000s. Each computing model enabled new classes of applications that built on the unique strengths of the platform. For example, smartphones were the first truly personal computers with built-in sensors like GPS and high-resolution cameras. Applications like Instagram, Snapchat, and Uber/Lyft took advantage of these unique capabilities and are now used by billions of people.

Blockchain computers were first proposed in 2008 by Satoshi Nakamoto in the (Bitcoin whitepaper)[https://bitcoin.org/bitcoin.pdf]. Those original ideas have since been dramatically expanded by developers and researchers around the world. Blockchain computers are new types of computers where the unique capability is trust between users, developers, and the platform itself. This trust emerges from the mathematical and game-theoretic properties of the system, without depending on the trustworthiness of individual network participants. 

Although the Bitcoin whitepaper is now more than 10 years old, we believe we are still early in the crypto movement. Crypto is purely a software movement and doesn’t depend on a hardware buildout, in contrast to, say, the internet, which required laying cables and building cell towers. Second, the space is developing extremely rapidly, partly because the code, data, and knowledge is largely open source, and partly because of the increasing inflow of talent.


## Description of preliminary data preprocessing:
- The first thing that we needed to do was to drop all our null values so that we can actually use our data for the model. 
- Then we needed to drop certain columns that we would not be using for our model so that we are only hvaing to deal with the data that we actuualy need.

## Description of preliminary feature engineering and preliminary feature selection, including their decision-making process 
- The features that we are selcting are ('current_price','circulating_supply', 'fully_diluted_valuation', 'total_volume', 'total_supply', 'market_cap')
- The reason that we selected these are that we have the most precise and trustworthy data for these categories. We also think that since we are trying to find a way to predict the crypto market based on certain features we believe that these are both good indicators into the financial side of cryptos, but also lend themselves to work well in our model. 
- We also plan to include some sentiment data as we believe that socila media has a unique influnece on the crypto market and we are curious to see if there is some predictable trend between interaction and reactions and how well a coin does in the market. 

## Description of how data was split into training and testing sets 
- we will use current price and market cap as our testing sets and then the rest as our trainable data. The reason for this is that we are interested in seeing if our model is able to prectit the price and how well a coin is doing so we want to make sure that we train our model to be tested against the features/data that we are targeting to predict. 

## Explanation of model choice, including limitations and benefits
- We will be using a random forest model for a few reasons it is Robust to outliers, Works well with non-linear data, Better accuracy than other classification algorithms.
- A couple of things that we do need to be careful about are, Random forests are found to be biased while dealing with categorical variables and Not suitable for linear methods with a lot of sparse features. they also train slowly but we have plenty of time to train our model. 
