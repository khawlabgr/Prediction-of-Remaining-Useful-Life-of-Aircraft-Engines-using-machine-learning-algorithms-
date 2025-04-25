
                ---------------------------------------------------------------------------------------------              
                  Prediction of Remaining Useful Life of Aircraft Engines using machine learning algorithms:
                                                  Comparative Study
                ---------------------------------------------------------------------------------------------

# CMAPSS Predictive Maintenance with Machine Learning and Deep Learning

This project uses machine learning and deep learning models to predict the Remaining Useful Life (RUL) of jet engines using the "CMAPSS dataset" from NASA, obtained via Kaggle. The dataset simulates different operating conditions and fault modes in engines and is split into four subsets: FD001, FD002, FD003, and FD004.

[Kaggle Dataset Link](https://www.kaggle.com/datasets/behrad3d/nasa-cmaps)

---

##  C-MAPSS Dataset Structure

| Dataset  | Training Units | Testing Units | Operating Conditions | Fault Modes         |
|----------|----------------|----------------|-----------------------|---------------------|
| FD001    | 100            | 100            | One (Sea Level)       | One (HPC)           |
| FD002    | 260            | 259            | Six                   | One (HPC)           |
| FD003    | 100            | 100            | One (Sea Level)       | Two (HPC, Fan)      |
| FD004    | 248            | 249            | Six                   | Two (HPC, Fan)      |

Each subset simulates a different operational scenario and degradation pattern.

---

##  Models Implimented

The following models were implemented and compared:

- Gradient Boosting Machines (GBM)
- Long Short-Term Memory Networks (LSTM)
- Convolutional Neural Networks (CNN)
- Support Vector Machines (SVM)
- Gated Recurrent Units (GRU)
- Combined CNN-LSTM => (Best Performance)

##Performance Metrics

We evaluated model performance using:

- RMSE (Root Mean Square Error): Measures the standard deviation of prediction errors.
- R² Score (Coefficient of Determination): Indicates how well the model explains variance in the data.

These metrics are well-suited for regression problems such as RUL prediction, offering insight into both error magnitude and predictive power.

---

## Dataset Description

The CMAPSS dataset contains multivariate time-series sensor data for aircraft engines. Each engine runs until failure. The dataset includes:

- Train data: Time-series data of engine units until failure
- Test data: Similar sequences with unknown failure times
- RUL: Remaining Useful Life values for test sequences

Each subset (FD001 to FD004) represents different combinations of operating conditions and fault modes.

---

## Requirements

- Python 3.7+
- VS Code or any compatible IDE (Jupyter Notebook support recommended)
- Libraries: `pandas`, `numpy`, `scikit-learn`, `tensorflow`, `keras`, `matplotlib`

---

##  Performance Comparison Across Subsets

| Method     | FD001 | FD002 | FD003 | FD004 |
|------------|-------|-------|-------|-------|
| GBM        | 28.18 | 29.80 | 40.99 | 41.08 |
| LSTM       | 27.14 | 31.04 | 40.98 | 40.64 |
| SVM        | 48.18 | 56.54 | 57.79 | 62.18 |
| GRU        | 30.80 | 30.37 | 30.83 | 40.79 |
| CNN        | 27.15 | 30.80 | 30.53 | 42.00 |
| CNN-LSTM   | 24.14 | 29.50 | 35.52 | 38.74 |

---

##  Average RMSE and R² Across All Models

| Model     | GBM   | GRU   | LSTM  | CNN   | CNN-LSTM | SVM    |
|-----------|-------|-------|-------|-------|-----------|--------|
| RMSE      | 35.01 | 33.20 | 34.95 | 32.62 | **31.97** | 56.17  |
| R²        | 0.42  | 0.44  | 0.49  | 0.38  | **0.50**  | -0.42  |

---
##  Conclusion

 The CNN-LSTM model consistently shows the best predictive performance, offering a powerful balance of feature extraction (via CNN) and sequence learning (via LSTM). It's ideal for real-time predictive maintenance.

---