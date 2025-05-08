S&P500 Predictor

This project is a machine learning model that predicts the movement of the S&P 500 index based on historical data. It uses Yahoo Finance data via `yfinance` and applies a Random Forest Classifier to determine if the index is likely to go up the next trading day.

Project Highlights

- Data:
  Full historical S&P 500 data, fetched directly using the `yfinance` API.

- Approach:
  - Binary classification: whether tomorrow's price will be higher than today’s.
  - Backtesting logic to simulate real-world trading performance.
  - Feature engineering with rolling averages & trend indicators (e.g., ratios over 2, 5, 60, 250, and 1000-day windows).

- Model:
  RandomForestClassifier with tuned hyperparameters:
  - n_estimators
  - min_samples_split
  - random_state

- Performance Evaluation:
  - Precision Score: to measure the accuracy of predicting upward movements.
  - Value counts & plotting: to visualize predictions vs. actual outcomes.

Requirements

Make sure you have these libraries installed:

pip install yfinance pandas scikit-learn matplotlib

How to Run

1. Launch Jupyter Notebook:

   jupyter notebook

2. Open `Project.ipynb`.

3. Run all cells step by step:
   - The notebook will:
     - Download S&P 500 data.
     - Clean & process the data.
     - Train the Random Forest model.
     - Perform backtesting.
     - Display precision scores and prediction plots.

Core Files

- Project.ipynb: The main notebook containing all the code & visualizations.
- README.txt: This documentation file.

Key Features & Workflow

1. Fetch & Plot Data:
   - Full historical S&P 500 index data.
   - Line chart of closing prices.

2. Preprocessing:
   - Drops unused columns like dividends & stock splits.
   - Creates a target: 1 if tomorrow’s close > today’s close, otherwise 0.
   - Focuses on data from 1995 onwards.

3. Model Training:
   - Uses RandomForestClassifier on predictors: Close, Volume, Open, High, Low.
   - Adds advanced features: rolling averages & trend indicators over multiple time horizons.

4. Backtesting:
   - Splits data into training and testing in time-ordered batches.
   - Validates the model across multiple time windows to simulate real trading conditions.

5. Thresholding:
   - Sets a prediction probability threshold of 0.6 for stronger signals.

Outputs

- Precision Score: How often the model correctly predicts an upward movement.
- Prediction Plots: Side-by-side comparison of actual vs. predicted outcomes.

Disclaimer

This project is for educational purposes only.
It is not intended for live trading or financial advice.

License

This project is open-source for learning & experimentation.

Created by: AtwaniGG (https://github.com/AtwaniGG)

