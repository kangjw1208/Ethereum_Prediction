# Ethereum Price Prediction

## Overview
Cryptocurrency market has first emerged during the start of last decade and has evolved into a widely accepted asset class with a promising potential of becoming a hedge against the traditional fiat currency. Moreover, it is the driving force towards the next industrial revolution that will create the ubiquity of Web 3.0, metaverse, and smart contracts. These evolutionary trends will play a key role in decentralizing vast amounts of data ultimately protecting the privacy of individuals. Although cryptocurrency itself has a bad reputation while deemed as volatile and dangerous, it has been the single most highest returning investment asset in the past decade. After the Covid-19 pandemic, both corporate and individual investors faced the harsh reality of a fragile traditional market. As a result, many people and firms opened up to the posibility of crypto investments and ignited the influx of capital which raised the market caps to trillions of dollars.

## Business Understanding
Bitcoin and Ethereum are the two most widely traded crypto assets. Both assets mirrored each other during the bull and bear markets in the past. As a result, individual investors often consider the two as similar assets, yet there are some key differences to the functionality of each crypto asset. While Bitcoin’s main function includes storing of values through the blockchain technology, Ethereum’s main function includes an endorsement of smart contracts that provides the ecosystem for the development of other crypto currencies. This Ethereum’s huge upside potential interested many investors and now deviated from the it’s reputation as a cheaper bitcoin substitute. Similar to the Bitcoin price, the price of Ethereum is still extremely volatile and many investors wish to understand the trending price and its volatility. This project could give an insight into the price of Ethereum solely from the data perspective.

## Main Objectives

* Use time series analysis
* Understand the underlying trend of Ethereum price
* Use time series model to forecast future prices
* Use other deep learning algorithm to predict future prices
* Analyze the results

## Data Cleaning
Ethereum data from the Binance trading platform has been obtained through the third party cryptocurrency database. The raw csv files have all its data as an object form. Therefore the time of each row had to be transformed into a date time object and all the prices had to be transformed into a float type. To achieve this, I have written two functions that takes in the dataframe and returns the desired dataframe suitable for time series analysis. Although the database had several features including the highs, lows, and volumes of Ethereum trade, only the closing price was considered for this analysis. 

## Data Exploration
I used the returned dataframe to run decomposition analysis to identity its trend and seasonality. Then I transformed the data to remove those trends to get a stationary data. I used the Augmented Dickey-Fuller test to make sure that the data was stationary. Finally I used Auto Correlation and Partial Auto Correlation to interpret the order of Autoregressive(AR) and Moving Average(MA).

## Model

## Result

## Conclusion

## Repository Structure
```
├── [data]
├── [images]
├── .gitignore
├── README.md
└── notebook.ipynb
```
