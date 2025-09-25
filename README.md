# Advisor-Neural-Network

Implementation of an **Advice Unit Optimization System** for stock forecasting and recommendation.

## Project Overview
This project focuses on the Indonesian stock market using a selected set of 18 tickers:

**BMRI.JK, BBCA.JK, ARTO.JK, BRIS.JK, BBNI.JK, BBTN.JK, BBRI.JK, TLKM.JK, GOTO.JK, ISAT.JK,  
EXCL.JK, ASII.JK, UNTR.JK, PGEO.JK, UNVR.JK, INDF.JK, HMSP.JK, GGRM.JK**

Dataset timeframe: **January 1, 2025 – September 22, 2025**.

## Methodology
- **Model**: LSTM-based forecasting to predict daily closing prices. (This is because, my model was good at predicting close price rather than daily return)
- **Advice Unit**: Each market day, the system selects **2 stocks** with the highest predicted return (based on close price movements).  
- **Additional Data**: News sentiment and related features were collected using **BeautifulSoup** web scraping from **Detik.com**, covering the same timeframe (Jan 1, 2025 – Sep 22, 2025) and filtered by the above stocks.  

## Dataset Split
📊 The dataset was divided as follows:
- **TRAIN**: 1 Jan 2025 – 31 May 2025  
- **VALIDATION**: 1 Jun 2025 – 31 Jul 2025  
- **TEST**: 1 Aug 2025 – 31 Aug 2025  

## Evaluation Results
Model performance on the **test set** (closing price prediction):

- **RMSE**: 3163.59  
- **MAE**: 1254.93  
- **MAPE**: 0.222.01 %  

⚠️ The high MAPE indicates that relative error is large for some low-priced stocks, even though RMSE and MAE remain within an acceptable absolute range.  

## Results
Results of the implementation of the LSTM model on 18 IDX shares (period **1 Jan 2025 – 22 Sep 2025**):

<img width="752" height="516" alt="image" src="https://github.com/user-attachments/assets/e51b0ddf-0d05-4414-aadf-2638197d1c75" />

➡️ Every trading day, the system provides **recommendations for 2 stocks** with the highest predicted returns.  

## Dependencies
The project was implemented in **Python 3.9+** with the following key libraries:
- TensorFlow / Keras (for LSTM model)
- Scikit-learn (for scaling and evaluation metrics)
- Pandas & NumPy (for data processing)
- Matplotlib / Seaborn (for visualization)
- BeautifulSoup4 & Requests (for news scraping)

## Assumptions
- Stock data is clean, continuous, and without missing trading days.  
- News scraped from **Detik.com** is relevant and provides sentiment signals related to the chosen tickers.  
- We directly used **IndoFinSent**, an Indonesian financial sentiment model, to compute sentiment scores from the scraped news data.  

  IndoFinSent : https://arxiv.org/pdf/2310.09736
---
