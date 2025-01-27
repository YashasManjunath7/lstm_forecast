# Stock Price Analysis and Forecasting with Dash and LSTM

## Project Overview
This project explores stock price forecasting using an LSTM (Long Short-Term Memory) model. The application is built using the Dash framework to provide an interactive dashboard for visualizing stock data, predictions, and market trends.

---

## Objectives
1. Develop a machine learning model (LSTM) for time-series forecasting of stock prices.
2. Create an interactive dashboard for data visualization.
3. Compare actual stock prices with LSTM predictions.
4. Include additional data visualizations, such as market volume and high/low prices for selected stocks.

---

## Methodology

### Data Preparation
- **Source**: The dataset is sourced from `NSE-Tata-Global-Beverages-Limited.csv`.
- **Preprocessing**:
  - Convert the `Date` column to a datetime object and set it as the index.
  - Create a new DataFrame with `Date` and `Close` prices.
  - Normalize the data using `MinMaxScaler`.

### Data Splitting
- **Training Data**: First 987 rows of the dataset.
- **Validation Data**: Remaining rows.

### LSTM Model
- **Architecture**:
  - Input Layer: LSTM with 50 units and return sequences enabled.
  - Dropout Layers: Two dropout layers with a 20% rate.
  - Dense Layer: Single unit for output.
- **Loss Function**: Mean Squared Error.
- **Optimizer**: Adam.
- **Training**:
  - Trained for 10 epochs with a batch size of 32.

### Prediction
- Generate predictions using the trained LSTM model.
- Reverse the normalization to obtain the predicted closing prices.

---

## Dashboard
Built using Dash, the dashboard provides the following functionalities:
1. **Tabs**:
   - `NSE-TATAGLOBAL Stock Data`:
     - Visualize actual closing prices and LSTM-predicted closing prices.
   - `Facebook Stock Data`:
     - High vs. Low prices.
     - Market volume trends.

2. **Interactive Features**:
   - Dropdown menus for selecting stocks (`Tesla`, `Apple`, `Facebook`, and `Microsoft`).
   - Date range sliders for time-based filtering.

### Key Dash Components
- `dcc.Tabs`: Enables tabbed navigation.
- `dcc.Graph`: For data visualization.
- `dcc.Dropdown`: For user input selection.

---

## Findings
- The LSTM model captures trends effectively, as seen in the comparison between actual and predicted prices.
- The dashboard provides an intuitive interface for users to explore stock data interactively.
- Additional visualizations (e.g., high/low prices and market volume) enhance the analysis.

---

## Challenges
1. **Model Training**:
   - LSTM training is computationally intensive.
   - Hyperparameter tuning could improve results further.
2. **Data Processing**:
   - Handling missing or inconsistent data.
3. **User Warnings**:
   - Chained assignment and deprecation warnings in pandas need resolution.

---

## Conclusion
This project demonstrates the integration of machine learning and web development for stock price analysis. The use of LSTM for forecasting, combined with an interactive dashboard, provides a powerful tool for financial analysis and decision-making.

---

## Recommendations
1. **Enhance the Model**:
   - Incorporate additional features, such as trading volume and external economic indicators.
   - Experiment with hybrid models (e.g., CNN-LSTM).
2. **Dashboard Features**:
   - Add functionality for real-time stock data updates.
   - Include sentiment analysis for better context.
3. **Code Optimization**:
   - Address pandas warnings for cleaner and more efficient execution.

---

