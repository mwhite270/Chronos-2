# Ethereum Forecasting using Chronos-2

## Project Overview
This notebook demonstrates how to forecast Ethereum (ETH) prices using Amazon Science's Chronos-2 model. It utilizes historical price data from CoinGecko, preprocesses the data, trains the Chronos-2 model, and evaluates its forecasting performance.

## Key Features
*   **Data Acquisition**: Loads historical Ethereum price data.
*   **Data Preprocessing**: Cleans and prepares the time series data for Chronos-2, including handling missing values and setting a datetime index.
*   **Chronos-2 Forecasting**: Leverages the pre-trained Chronos-2 pipeline for probabilistic time series forecasting.
*   **Evaluation & Visualization**: Splits data into context and test sets, generates predictions, and visualizes the forecast against actual values.

## Libraries Used
*   `chronos-forecasting`: For Chronos-2 model integration.
*   `pandas`: For data manipulation and analysis.
*   `numpy`: For numerical operations.
*   `matplotlib`: For plotting and visualization.

## Data Source
Ethereum pricing data was obtained from CoinGecko, specifically the `eth-usd-max.csv` file. The data file is included in this repository.

## Notebook Structure
1.  **Installation and Imports**: Installs necessary libraries and imports modules.
2.  **Data Loading and Cleansing**: Reads ETH price data, drops unneeded columns, sets `snapped_at` as a daily frequency index, fills missing values, and adds an `id` column.
3.  **Chronos-2 Model Initialization**: Loads the pre-trained `amazon/chronos-2` model.
4.  **Chronos-2 Evaluation**: 
    *   Splits the `eth_df` into `context_df` (training) and `test_df` (ground truth for evaluation).
    *   Defines `prediction_length` (24 days).
    *   Generates probabilistic forecasts using `pipeline.predict_df()` with quantile levels (0.1, 0.5, 0.9).
5.  **Visualization**: Plots the historical data, actual future prices, and the Chronos-2 forecast (including prediction intervals) to visually assess model performance.
