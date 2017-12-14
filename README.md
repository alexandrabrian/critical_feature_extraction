# Predicting Trading Signals using KPCA and SVD

Alexandra Brian

see iPython notebooks for raw code for each pipeline.

## Introduction

### Domain and Data:
This project uses historical pricing data from the S&P500 with the following terms:

- `Close` : A securities closing price on a specified day of trading.
- `Open`: The price of a stock on a given day.
- `High`: The highest price at which a stock traded during the course of a day. 
- `Low`: The lowest price a stock traded during the course of a day. 

#### Feature engineering:
We use the historical pricing data to generate the following 47 features, technical indicators (TI):

- `ADX`
    n:(14)
    n_ADX:(50)
- `ATR`
    -n:(14)
- `BollingerB_5`
- `Bollinger%b_5`
- `BollingerB_20` 
- `Bollinger%b_20`
-`Copp`
    n:(10)
-`Chaikin`
-`EMA`
    - n:(5,20)
-`Force_2`
-`KST` 
    r: (10,10,10,15)
    n: (10,15,20,30)
-`MA` 
    n:(5,20) 
-`MACD_12_26`
-`MACDsign_12_26`
-`MACDdiff_12_26`
-`MFI`
    n:(14)
-`Momentum_1`
-`Mass Index`
-`OBV`
    n:(5,20)
-`PP`
-`R1`
-`R2`
-`R3`
-`S1`
-`S2`
-`S3`
-`ROC`
    n:(5,20)
-`RSI`
    n:(6,12)
-`STD`
    n:(5,20)
-`SO%d_5`
-`SO%d_20`
-`SO%k`
-`Trix`
    n:(5,20)
-`TSI`
    r:(25)
    n:(13)

### Problem Statement: 
All investors seek to predict stock positions (buy, hold and sell) that generate a profitable return. There are many different methods employed to accomplish this goal, such as fundamental, sentiment  and technical analysis. Financial forecasting has many challenges because financial time series data are noisy, non-stationary and volatile. Due to the many features and noisy features associated with historical pricing data many investors have turned to machine learning, statistical and computational perspectives.    

### Solution Statement: 
This study aims to reduce the inherently noisy nature of the features assocaited with the time-series data. First, naive PCA will be used for feature selection . 


### Metric

### Benchmark

## Methods

### Building the Benchmark: 

### Feature Selection using KPCA

### GridSearch tuned KPCA and SVD

### Results

### Conclusion 