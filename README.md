# **Avocado Supply Prediction**

## **Introduction**
This project aims to predict avocado supply volumes using machine learning techniques with a focus on seasonality, temporal patterns, and environmental factors. By incorporating features like lagged values, rolling statistics, and Fourier-transformed seasonality indices. the model succeed in capture both short-term trends and long-term seasonal variations uwith the past data. However, the futue data prediction encounter difficulties due to lack of data and useful features.

## **Project Objectives**
1. Develop a robust forecasting solution for supply volume trends.
2. Leverage state-of-the-art models (machine learning, time series, neural networks) to identify patterns and provide reliable future predictions.
3. Provide interpretable results to Naturipe through a mix of statistical analyses and visualizations.

---

## **Models Implemented**
The repository includes the following models, each tailored to address specific aspects of forecasting:

### **1. ETS (Exponential Smoothing)**
- **File**: `850_ets.ipynb`
- Implements classical exponential smoothing for time-series forecasting.
- Provides interpretable seasonality and trend decomposition.
- 

### **2. LightGBM**
- **Files**: `lightgbm.ipynb`, `lightgbm-modified final.ipynb`, `trial on lightgbm.ipynb`
- Leverages gradient boosting with tree-based models.
- Implements L1 and L2 regularization to reduce overfitting.
- Supports advanced feature engineering (e.g., temporal features).
- #### Get the best peformance by far.

### **3. ARIMA**
- **File**: `ARIMA.ipynb`
- Auto-Regressive Integrated Moving Average model for univariate time series.
- Suitable for capturing autocorrelations and trends in stationary data.

### **4. SARIMA**
- **File**: `SARIMA.ipynb`
- Seasonal extension of ARIMA for modeling seasonality in the data.
- Captures complex seasonal patterns in supply data.

### **5. LSTM (Long Short-Term Memory)**
- **File**: `LSTM.ipynb`
- Neural network model designed for sequential data.
- Captures long-term dependencies and non-linear patterns in time series.

### **6. Random Forest**
- **File**: `randomforest.ipynb`
- A tree-based ensemble model suitable for handling non-linear relationships.
- Provides robust predictions by averaging results across multiple decision trees.

### **7. XGBoost**
- **File**: `xgboost.ipynb`
- Gradient boosting framework optimized for speed and performance.
- Handles missing values and outliers effectively.

### **8. ETS + Ridge Regression**
- **File**: `ets_ridgeregression.ipynb`
- Combines ETS for capturing seasonality with Ridge Regression for robust linear modeling.

### **9. Tiny Time Mixer**
- **File**: `tinytimemixer.ipynb`
- A novel approach that blends neural architectures with traditional forecasting techniques.

### **10. XGBoost + SARIMA**
- **File**: `xgboost+sarima.ipynb`
- Hybrid model combining machine learning and time-series components for improved accuracy.

---

## **Analysis Conducted**
In addition to the models, we conducted detailed data analysis to enhance understanding and performance:

### **1. Data Preprocessing**
- Handled missing values by averaging differences across data points.
- Scaled features using `MinMaxScaler` for models requiring normalized input.

### **2. Feature Engineering**
- Extracted temporal features such as `DayOfYear`, `WeekOfYear`, `Month`, and `DayOfWeek`.
- Used lagged features (e.g., `Supply_lag_1`, `Supply_lag_7`) to capture dependencies in sequential data.

### **3. Regularization**
- Applied L1 and L2 regularization in LightGBM to reduce overfitting and improve generalization.

### **4. Evaluation Metrics**
- **R²** (Coefficient of Determination): Assesses model fit quality.
- **RMSE** (Root Mean Squared Error): Measures prediction accuracy.
- **MAE** (Mean Absolute Error): Evaluates prediction consistency.

### **5. Visualization**
- Plotted actual vs. predicted supply trends for all models.
- Included future supply forecasts with adjustable time periods.

---

## **How to Use**
1. **Clone the Repository**:
   ```bash
   git clone <repository_url>


2. **Dependencies**:
    ```bash
   pip install -r requirements.txt
    
3. **Run Notebooks**:
- Use any Jupyter Notebook `(.ipynb)` to explore specific models or analyses.
  
4. **Adjust Forecasting Horizon**:
- For future predictions, set `time_period` in the respective notebook (e.g., LightGBM, SARIMA, ETS):
   ```bash
   time_period = 30  # Predict for the next 30 days

---

## **Results Summary**
1. **Model Comparison**:
   - **Best Model**: The **Current-Best Model**, as highlighted in the analysis, achieved:
     - **R²**: 0.9365
     - **RMSE**: 1,742,280.99
   - This model effectively captures historical trends and makes reliable future predictions with minimal error.
   - Example models that underperformed:
     - ETS: Deviated from historical trends.
     - SARIMA: Inconsistent with future supply predictions.

2. **Insights**:
   - Supply trends did show seasonality captured effectively by time-series models (ETS, SARIMA), so embed more feature align with seasonality may help these model on prediction.
   - Machine learning models (LightGBM, XGBoost) outperform in handling non-linear relationships and external factors (e.g., weather), but need greater amount of data to predict more effectively.

---

## **Next Steps**
1. **Gather More Data**:
   - Embed longer period of data so that model like `LightGBM`can perform better on prediction
   - Embed other useful features so that model like `ETS` can capture more pattern in data.
     
2. **Further Model Optimization**:
   - Hyperparameter tuning (e.g., learning rates, regularization parameters).
   - Experiment with hybrid models for improved performance.

3. **Integration**:
   - Deploy the best-performing models into a real-time forecasting pipeline.

4. **Client-Specific Customization**:
   - Tailor predictions to useage needs (e.g., different forecasting horizons, specific supply chain factors).

---

## **Contact**
For any inquiries, feel free to reach out:

- **Email**: [hzheng238@wisc.edu]
- **GitHub**: [Jansenism1231]
- **LinkedIn**: [Hanwen Zheng]
