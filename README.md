# Stock Analysis and Prediction using Ridge Regression and LSTM
![image](https://github.com/user-attachments/assets/a8743c7d-c5db-4bcb-bce1-2c1a83e05c5b)

## Project Description:

This project aims to provide a comprehensive analysis of valuable stock information listed on Vietnam’s HOSE stock exchange, while also forecasting stock prices for the VN30 stocks using two different methods: Ridge Regression and Long Short-Term Memory (LSTM). Using historical closing price data, we built models that can predict short-term future prices. This project combines traditional machine learning (Ridge Regression) with deep learning (LSTM) to compare and evaluate the performance of each approach.

## Data Description:

Bộ dữ liệu được thu thập từ website cafef, ghi nhận thông tin về giá trị của tất cả các loại cổ phiếu trong khoảng thời gian từ 30/12/2012 đến 18/10/2024. 

## Process:

1. **Stock Price Analysis**

- First, I will import the data from the file csv, then do some cleaning actions to serve for the stock analysis. 

- After cleaning, I visualized the closing price trends to understand each stock's performance over time. I also calculated the Moving Average to smooth out short-term fluctuations and observe longer-term trends.

- Additionally, I computed the daily return for each stock to capture the day-to-day price change, providing insights into each stock’s volatility and growth patterns. Furthermore, I calculated the correlation among different stocks, allowing an analysis of interdependencies and trends within the VN30 group.

2. **Data Pre-Processing**: 

- To accurately forecast stock prices, historical data on closing prices must be prepared before being put into the models.

- The preprocessing step involves removing missing values or outliers that could introduce noise into the model, normalizing the data to ensure uniform scaling across columns, and formatting date data appropriately for model usage. 

- Additionally, to use the LSTM model, the data is split into fixed-length sequences based on a specified number of days (window size) to provide context on previous trends when predicting the next day’s price. These careful data preparation steps ensure the accuracy and generalizability of the model when training and testing with real data.

3. **Stock Price Forecasting**: 

- The preprocessed historical data was divided into a training set (95%) and a test set (5%). This split aims to allow the model to learn from the training data and then test its predictive power on the new test data. Forecasting methods include both Ridge Regression and LSTM. In Ridge Regression, past price sequences are used to predict the closing price for the next 15 days, leveraging a regularized linear regression approach to avoid overfitting.

- Meanwhile, the LSTM model processes time-series data, capturing long-term dependencies in the data to forecast future price fluctuations. This forecasting process provides predicted values compared to actual prices, enabling a detailed analysis and evaluation of each model's performance.

4. **Model Evaluation**: 

- Upon completing the stock price predictions, each model's performance is evaluated using accuracy metrics such as Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE).

- MSE evaluates the average squared difference between predicted and actual values, while RMSE, the square root of MSE, provides a more interpretable measure of the average deviation from the actual prices. MAE measures the average absolute difference between predicted and actual values, assessing the prediction error in practical terms.

- Using all three metrics provides a comprehensive view of each model's performance, helping to identify the best approach for predicting stock prices for the VN30 dataset.

## Prediction Results:

- Below are sample prediction charts for the FPT stock by each model:

![image](https://github.com/user-attachments/assets/b2ba4cc3-681d-401a-b164-4e699fd75674)

![image](https://github.com/user-attachments/assets/d2cd7225-e4fb-4246-aaae-d0217747e60b)






