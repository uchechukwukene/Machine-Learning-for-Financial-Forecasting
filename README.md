# **FactorVAE for Financial Data Analysis**

This repository contains an implementation of FactorVAE, adapted for financial time-series data such as stock prices. The goal of this project is to leverage disentangled latent factors for tasks like asset price prediction, market regime identification, and portfolio risk analysis.

## **Table of Contents**
1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
   - [Data Preprocessing](#data-preprocessing)
   - [Training](#training)
   - [Evaluation](#evaluation)
5. [Project Structure](#project-structure)
6. [Contributing](#contributing)
7. [License](#license)

## **Introduction**

Factorized Variational Autoencoder (FactorVAE) is a variant of the VAE designed to improve disentangled representation learning. This project adapts FactorVAE for financial data, focusing on time-series datasets such as stock prices. The model learns latent factors that represent different interpretable features of the data (e.g., market trends, volatility), which can be used for various financial applications.

### Key Applications:
- **Asset Price Prediction**
- **Market Regime Identification**
- **Portfolio Risk Decomposition**

## **Features**
- Preprocessing and normalization of stock data using `yfinance`.
- Disentangled latent factor representation using FactorVAE.
- Ability to train the model on financial time-series data.
- Visualization of reconstructed data and latent factors.

## **Installation**

### 1. Clone the repository:
```bash
git clone https://github.com/YourUsername/FactorVAE-Finance.git
cd FactorVAE-Finance
```

### 2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## **Usage**

### 1. Download Financial Data
We use the yfinance library to download stock market data. You can specify the stock symbol, time range, and frequency. The example below fetches S&P 500 data:
```bash
import yfinance as yf

# Download S&P 500 data
data = yf.download('^GSPC', start='2010-01-01', end='2020-01-01')

# Preprocess the data by normalizing it
adj_close = data['Adj Close'].pct_change().dropna()  # Daily percentage change
normalized_data = (adj_close - adj_close.mean()) / adj_close.std()  # Standardization
```



