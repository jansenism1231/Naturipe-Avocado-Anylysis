# **Avocado Supply Prediction Using LightGBM**

## **Introduction**
This project aims to predict avocado supply volumes using machine learning techniques with a focus on seasonality, temporal patterns, and environmental factors. By incorporating features like lagged values, rolling statistics, and Fourier-transformed seasonality indices, the model captures both short-term trends and long-term seasonal variations.

The project employs **LightGBM**, a gradient boosting framework, for efficient training and high prediction accuracy.

---

## **Features**
### **Key Components of the Dataset**
1. **Historical Supply Data**:
   - Daily avocado supply volumes.
2. **Environmental Factors**:
   - 72-day temperature and precipitation data.
3. **Temporal Features**:
   - `DayOfYear`, `WeekOfYear`, `Month`, and `DayOfWeek`.
4. **Seasonality Features**:
   - Decomposed seasonality index from historical data.
   - Fourier Transform features (`Fourier_Sin` and `Fourier_Cos`).
5. **Lag and Rolling Features**:
   - Lagged supply values (e.g., `Lag_7`, `Lag_30`).
   - Rolling mean and standard deviation of supply values over recent days.

---

## **Models Used**
The following techniques and models were utilized:
1. **LightGBM**:
   - Gradient Boosting framework for regression tasks.
   - Key features:
     - Handles large datasets efficiently.
     - Automatically manages missing values.
     - Allows regularization for preventing overfitting.
2. **Seasonality Decomposition**:
   - Additive decomposition to extract seasonal patterns from supply data.
   - Incorporated the seasonal component as a feature.
3. **Fourier Transform**:
   - Added sinusoidal and cosinusoidal features to capture periodicity.
4. **Lag and Rolling Features**:
   - Provided temporal context by incorporating lagged supply values and rolling statistics.

---

## **How the Model Works**
1. **Preprocessing**:
   - Cleaned the supply data by handling missing values and converting date formats.
   - Engineered temporal and environmental features.
2. **Feature Engineering**:
   - Included seasonality, Fourier Transform components, lagged values, and rolling statistics.
3. **Model Training**:
   - Trained a LightGBM regression model using the engineered features.
   - Optimized hyperparameters such as learning rate, regularization terms, and tree complexity.
4. **Prediction**:
   - Predicted supply volumes for future dates by extending the engineered features into the future.
   - Incorporated historical patterns for lag and rolling features during future predictions.

---

## **Usage**

### **1. Requirements**
Install the necessary libraries:
```bash
pip install numpy pandas lightgbm statsmodels matplotlib
