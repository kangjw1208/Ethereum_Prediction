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
###ARIMA
The baseline model I used was the ARIMA model. I used both daily data and weekly data to forecast prices.
Daily ARIMA model with order of (2, 1, 3)

![download](https://user-images.githubusercontent.com/92397140/151518692-ef775115-ba0a-44de-aad7-2fa882b8d85e.png)

Weekly ARIMA model with order of (3, 1, 3)

![download (1)](https://user-images.githubusercontent.com/92397140/151518780-af745e11-9f48-40ff-ae70-95de6c20a2ab.png)

At a quick glance this model seems to perform extremely well on both daily and weekly data with a small error. However, when we take a closer look at the results, we can see that this model is only mirroring past Ether prices. As you can see in the graph, a drastic increase or decrease in the price is predicted only after it has already happened.

###LSTM
To combat the simplicity of the traditional time series model, Long Short Term Memory (LSTM) network, a type of recurrent neural network, was used. This modeling technique was chosen because it is currently one of the most sophisticated models that can handle sequential data. To briefly explain the benefit of this architecture, LSTM neuron takes information from previous cells and combines it with newly input datas. It then quickly determines how much of the combined information is worth “retaining” or “forgetting”. This constant adjustment of weights produces a deep learning model that could potentially identify the underlying random patterns.
![image](https://user-images.githubusercontent.com/92397140/151519371-865f1381-1fae-4b5b-9f33-37b56c7b5ae3.png)
This LSTM model was trained through 3 hidden layers. 2 of them includes the acutal LSTM cells with decreaing number of neurons. One of the layer consists of the dropout layer in order to regulate the model controlling the possibility of overfit. The best performing lstm model had a both epoch size and batch size of 100.

Daily resampled data was used to train the model with a 8:2 train test split and 100 days of look back step.
![download (2)](https://user-images.githubusercontent.com/92397140/151519775-7d445986-9eb9-4718-a374-212d08a96f00.png)
**RMSE range of 350~650**

2000 historical hours were used to train the model with a 8:2 train test split and 100 hours of look back step.
![download (3)](https://user-images.githubusercontent.com/92397140/151520532-781aa9a6-e774-40a2-9421-738570874309.png)
**RMSE range of 120~250**

## Conclusion
In Conclusion, it is almost impossible to accurately predict the exact price ahead of time as we are well aware that numerous factors have to be taken into account when trying to explain the dynamic market prices. In fact, all the analytic models are predicting prices from hindsight. However, these models do provide an insight to the general trend of market prices exclusively from the data perspective. As a result, for the improvement of this project, incorporating News keywords and trending tweets can help explain the variance and volatility of Ethereum and consequently it could produce a better performing model.
## Repository Structure
```
├── [data]
├── [images]
├── .gitignore
├── README.md
└── notebook.ipynb
```
