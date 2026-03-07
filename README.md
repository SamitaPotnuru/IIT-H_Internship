# IIT-H_Internship
# Ferroelectric Material Property Prediction using Machine Learning

## Overview
This project uses **Machine Learning (Random Forest Regressor)** to predict important **ferroelectric material properties** based on the composition of elements such as **Barium, Calcium, Zirconium, Titanium, and Oxygen**.

The dataset is stored in **Google Sheets** and accessed using **Google Colab authentication**. The model predicts multiple material properties including remanent polarization, coercive field, dielectric constant, and energy density.

---

## Features
- Import dataset directly from **Google Sheets**
- Automatic **data cleaning and unit removal**
- **Missing value handling** using mean imputation
- **Multi-output regression model** using Random Forest
- Save and load trained model using **joblib**
- Predict material properties from element composition

---

## Technologies Used
- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- GSpread
- Joblib

---

## Dataset
The dataset is stored in a **Google Spreadsheet** named:

```
samita1
```

### Input Features
- Barium
- Calcium
- Zirconium
- Titanium
- Oxygen

### Target Properties
- Remanent Polarization
- Coercive Field
- Dielectric Constant
- Max Polarization
- Efficiency
- Saturation
- d33
- Recoverable Energy Density

---

## Data Preprocessing
The preprocessing steps include:

1. Removing measurement units such as:
   - µC/cm²
   - kV/cm
   - mJ/cm³
   - pC/N
   - pm/V

2. Converting values to numeric format.

3. Handling missing values using **SimpleImputer (mean strategy)**.

---

## Machine Learning Model

The model used:

```
RandomForestRegressor
```

Parameters:

```
n_estimators = 100
random_state = 42
```

The model performs **multi-output regression**, predicting multiple material properties simultaneously.

---

## Model Training Process

1. Load dataset from Google Sheets
2. Clean and preprocess data
3. Handle missing values
4. Split dataset into training and testing sets
5. Train Random Forest model
6. Evaluate model using **R² Score**

---

## Model Saving and Loading

The trained model is saved using **joblib**.

```
trained_model.joblib
```

Example:

```python
joblib.dump(model, 'trained_model.joblib')
model = joblib.load('trained_model.joblib')
```

---

## Prediction Example

Example composition:

```
Barium = 0.7
Calcium = 0.3
Zirconium = 0.2
Titanium = 0.8
Oxygen = 3
```

Conditions checked before prediction:

```
Barium + Calcium = 1
Zirconium + Titanium = 1
```

Predicted outputs:
- Remanent Polarization
- Coercive Field
- Dielectric Constant
- Max Polarization
- Efficiency
- Saturation
- d33
- Recoverable Energy Density

---

## Evaluation Metric

Model performance is evaluated using:

```
R² Score
```

Higher R² indicates better prediction performance.

---

## Project Workflow

```
Google Sheets Dataset
        ↓
Data Cleaning
        ↓
Unit Removal
        ↓
Missing Value Imputation
        ↓
Train/Test Split
        ↓
Random Forest Model Training
        ↓
Model Evaluation
        ↓
Model Saving
        ↓
Prediction
```

---

## Future Improvements
- Increase dataset size for better accuracy
- Add hyperparameter tuning
- Create a web interface for predictions
- Deploy the model using Flask or Streamlit

---
