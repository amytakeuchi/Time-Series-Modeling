# Time-Series-Modeling
## Introduction:
In today’s fast-paced and competitive manufacturing environment, organizations are increasingly shifting towards more effective, demand-driven supply chains to quickly adapt to changing market demands.
Demand forecasting plays a critical role in inventory management, as stock levels are directly influenced by demand predictions. Inaccurate demand estimation can result in significant financial losses for organizations. <br/>
This document aims to provide a comprehensive overview of the technical aspects and feasibility of the Rapid Predict modeling platform. It also explains how the platform delivers highly accurate forecasting results. Rapid Predict utilizes an additive modeling approach that captures the influence of multiple independent factors on the target (dependent) variable. <br/>
The document outlines the modeling methodology and the necessary preprocessing steps that must be completed prior to model development. The primary objective of this project is to model and forecast the dependent variable using the Box–Jenkins time series framework, with a particular focus on the ARIMA method. This is made possible by leveraging a large and consistent set of historical data.


## ARIMA (p, d, q) and Seasonal ARIMA (SARIMA)
ARIMA is a widely used statistical model for time series forecasting. It combines three components:
- AR (autoregressive): uses past values,
- I (integrated): applies differencing to make the data stationary,
- MA (moving average): uses past forecast errors.

The model assumes linearity, is computationally efficient, and is suitable for short-term forecasting even with relatively short datasets.

$$
\varphi(L)(1 - L)^d y_t = \theta(L)\varepsilon_t, \text{ i.e., } \\
\left( 1 - \sum_{i=1}^{p} \varphi_i L^i \right) (1 - L)^d y_t = \left( 1 + \sum_{j=1}^{q} \theta_j L^j \right) \varepsilon_t
$$

ARIMA(p, d, q):
- p: order of AR terms,
- d: degree of differencing to achieve stationarity,
- q: order of MA terms.

When d = 0, ARIMA reduces to ARMA; ARIMA(0,1,0) is a random walk model.

To ensure stationarity (no trend or changing variance), data often needs to be differenced. The model's residuals should resemble white noise—random, with zero mean and constant variance.

SARIMA (Seasonal ARIMA) extends ARIMA to handle seasonality by adding seasonal parameters (P, D, Q, s):
- P, D, Q: seasonal counterparts of ARIMA,
- s: length of the seasonal cycle (e.g., 12 for monthly, 4 for quarterly).
- Seasonal differencing (e.g., subtracting current observation from that of the previous year) removes seasonal trends.

The table provided lists several model configurations with different values of AR and MA terms. In all cases, d and D (non-seasonal and seasonal differencing) are assumed to be 0, indicating the input data is already stationary.

