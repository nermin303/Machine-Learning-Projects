# 🏡 Bengaluru House Price Prediction

This project performs data cleaning, exploration, feature engineering, outlier removal, and predictive modeling to estimate housing prices in Bengaluru, India. The dataset used comes from Kaggle and includes various housing attributes like size, location, total square footage, and more.

## 📦 Dataset

The dataset used is: `Bengaluru_House_Data.csv`  
Download from [Kaggle](https://www.kaggle.com/datasets/amitabhajoy/bengaluru-house-price-data)

---

## 📊 Project Workflow

### 1. Data Preprocessing
- Loaded the data with `pandas`.
- Dropped irrelevant columns: `area_type`, `availability`, `society`, `balcony`.
- Removed rows with missing values.

### 2. Feature Engineering
- Extracted number of bedrooms (`bhk`) from `size` column.
- Computed `price_per_sqft` from `price` and `total_sqft`.
- Cleaned up location labels and grouped rare locations under `other`.

### 3. Outlier Detection and Removal
- Removed listings where `total_sqft / bhk < 300`.
- Removed price per sqft outliers per location.
- Compared 2 BHK and 3 BHK prices in the same area and removed illogical entries.
- Removed listings where `bathrooms > bhk + 2`.

### 4. Data Preparation for Modeling
- Used `pandas.get_dummies()` for one-hot encoding of locations.
- Defined features (`x`) and target (`y`).
- Split the dataset using `train_test_split`.

### 5. Model Building and Evaluation
- Trained a **Linear Regression** model.
- Performed **cross-validation** using `ShuffleSplit`.
- Used **GridSearchCV** to find the best model:
  - Linear Regression
  - Lasso Regression
  - Decision Tree Regressor

### 6. Prediction Function
- Created `predict_price(location, sqft, bath, bhk)` that returns the predicted price for given input features.

---

## 🧪 Sample Usage

```python
predict_price('Rajaji Nagar', 1000, 2, 2)

