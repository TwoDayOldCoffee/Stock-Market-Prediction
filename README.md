# Stock Price Prediction using LSTM Neural Networks
A deep learning project that predicts stock prices for Apple (AAPL), Microsoft (MSFT), and Google (GOOGL) using Long Short-Term Memory (LSTM) neural networks implemented in PyTorch.

## Project Overview
This project explores the application of LSTM networks for time series forecasting in financial markets. The model learns from historical closing prices to predict future stock movements.

## Key Results

| Stock | RMSE | MAE | MAPE | R² Score | Directional Accuracy |
|-------|------|-----|------|----------|---------------------|
| AAPL  | $8.08 | $5.76 | 2.59% | 0.920 | 46.9% |
| MSFT  | $12.80 | $10.68 | 2.30% | 0.936 | 53.6% |
| GOOGL | $14.72 | $10.94 | 4.55% | 0.928 | 48.3% |

**Highlights:**
- Achieved 92-94% R² scores across all stocks
- Low prediction error (MAPE: 2.3-4.5%)
- MSFT showed best overall performance

## Technologies Used
- **Python 3.x**
- **PyTorch** - Deep learning framework
- **yfinance** - Stock data retrieval
- **pandas** - Data manipulation
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization
- **scikit-learn** - Metrics and preprocessing

## 💡 Methodology

### Data Collection
- Historical stock data from Yahoo Finance (2020-2024)
- Focus on daily closing prices
- 80-20 train-test split

### Data Preprocessing
- MinMax scaling (0-1 normalization)
- Sequence creation with 90-day lookback window
- Separate scalers for each stock

### Model Architecture
- **Input Layer:** Sequence of 90 historical prices
- **LSTM Layers:** 2 stacked layers with 64 hidden units
- **Dropout:** 0.3 for regularization
- **Output Layer:** Single value prediction (next day's price)

### Training
- **Optimizer:** Adam (lr=0.001)
- **Loss Function:** Mean Squared Error (MSE)
- **Epochs:** 200
- **Device:** GPU (CUDA) if available, else CPU

### Evaluation Metrics
- **RMSE** (Root Mean Squared Error) - Prediction accuracy in dollars
- **MAE** (Mean Absolute Error) - Average absolute error
- **MAPE** (Mean Absolute Percentage Error) - Percentage-based error
- **R² Score** - Proportion of variance explained
- **Directional Accuracy** - Correctly predicting up/down movements

## Key Findings

### Strengths
- Strong statistical fit (R² > 0.92)
- Low prediction error (MAPE < 5%)
- Captures general price trends well

### Limitations
- Directional accuracy near 50% (close to random)
- Only uses closing prices (no volume, news, sentiment)
- Past performance doesn't guarantee future results

## 🔮 Future Improvements

- [ ] Add technical indicators (RSI, MACD, Bollinger Bands)
- [ ] Incorporate trading volume data
- [ ] Implement sentiment analysis from news/Twitter
- [ ] Try transformer-based architectures
- [ ] Add macroeconomic indicators
- [ ] Ensemble methods (combine LSTM + ARIMA)
- [ ] Real-time prediction dashboard
