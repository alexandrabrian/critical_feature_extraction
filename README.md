# Predicting Trading Signals using KPCA and SVR

Alexandra Brian

see iPython notebooks for raw code for each pipeline.

## Introduction

### Problem Statement: 
All investors seek to predict stock positions (buy, hold and sell) that generate a profitable return. There are many different methods employed to accomplish this goal, such as fundamental, sentiment  and technical analysis. Financial forecasting has many challenges because financial time series data are noisy, non-stationary and volatile. Due to the many features and noisy features associated with historical pricing data many investors have turned to machine learning, statistical and computational perspectives.    

### Solution Statement: 
This study aims to reduce the inherently noisy nature of the features associated with the time-series data. First, naive PCA and Linear Regression will be used for our benchmark. Next, KPCA and SVR will be used as our model. 

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
    n:(14)
- `BollingerB_5`
- `Bollinger%b_5`
- `BollingerB_20` 
- `Bollinger%b_20`
- `Copp`
     n:(10)
- `Chaikin`
- `EMA`
     n:(5,20)
- `Force_2`
- `KST` 
     r: (10,10,10,15)
     n: (10,15,20,30)
- `MA` 
     n:(5,20) 
- `MACD_12_26`
- `MACDsign_12_26`
- `MACDdiff_12_26`
- `MFI`
     n:(14)
- `Momentum_1`
- `Mass Index`
- `OBV`
     n:(5,20)
- `PP`
- `R1`
- `R2`
- `R3`
- `S1`
- `S2`
- `S3`
- `ROC`
     n:(5,20)
- `RSI`
     n:(6,12)
- `STD`
     n:(5,20)
- `SO%d_5`
- `SO%d_20`
- `SO%k`
- `Trix`
     n:(5,20)
- `TSI`
     r:(25)
     n:(13)
     
### Creating Targets:
In order to create the targets for the model we will use Piecewise linear representation (PLR) to generate trading signals. 


![](doc/img/trading_signal_2.png)


### Metric
We will use two metrics, r^2 and mean squared error to score and compare our models. r^2 will show how much (0-1) of our model explains the variance. We will also use mean squared error to measure the difference between the estimator (y_test) and what is estimated (y_pred).

## Methods

### Building the Benchmark: 

1. Train, Test, Split
2. Create a Pipeline:
	- Standardize data 
	- Naive PCA
	- Linear Regression

#### Benchmark Results:  

Mean squared error: 0.07

Variance score: -2.95


### GridSearch tuned KPCA and SVD
1. Train, Test, Split
2. Create Pipeline:
	-  Standardize data
	- KPCA
	- SVR
3. GridSearch:
	- Tuned Hyperparameters:
		- KPCA:
			- Kernels: (rbf, sigmoid, cosine) 
			- n_components: (2-11)
			- Gamma: (10 evenly spaced numbers .1-1) 
		- SVR:
			- Kernels: (rbf, sigmoid)

### Results

Mean squared error: 0.16

Variance score: -7.43


### Conclusion
The benchmark has outperformed the Gridsearch, which suggests we should look further into improving our model. 

Possible future steps:
1. Categorize trading signals into 3 categories:
	 - Buy (1) 
	- Hold (0)
	- Sell  (-1) 
1. Go through technicals to check accuracy or improve hyperparameters
1. Figure out TSNE for visualization 
