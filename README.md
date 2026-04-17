🏠 House Price Prediction using Machine Learning
📌 Project Overview

This project focuses on predicting house prices using Machine Learning techniques on a housing dataset. It demonstrates a complete end-to-end ML pipeline, including data cleaning, exploratory data analysis (EDA), feature engineering, model training, and evaluation.

📊 Dataset Information
Total records: 20,640 entries
Features include:
Longitude & Latitude
Housing Median Age
Total Rooms & Bedrooms
Population & Households
Median Income
Ocean Proximity (categorical)
Target variable:
Median House Value

After preprocessing, the dataset was reduced to 20,433 rows due to removal of missing values

🔍 Exploratory Data Analysis (EDA)
Checked dataset structure using .info()
Removed missing values using dropna()
Visualized data distributions using histograms
Generated correlation matrix to identify relationships

📌 Key Insight:

Median Income has the highest correlation (~0.68) with house price
⚙️ Data Preprocessing
Handled missing values
Log transformation applied to:
total_rooms
total_bedrooms
population
households
Converted categorical feature (ocean_proximity) using one-hot encoding
Removed original categorical column after encoding
🧠 Feature Engineering

Created new features:

bedroom_ratio = total_bedrooms / total_rooms
household_rooms = total_rooms / households

These features improved model understanding of housing density and space utilization

🤖 Machine Learning Models Used
1️⃣ Linear Regression
Trained using processed dataset
Initial model performance:

👉 R² Score: 0.678

2️⃣ Linear Regression with Scaling
Applied StandardScaler
Performance dropped due to preprocessing inconsistency:

👉 R² Score: -0.54

3️⃣ Random Forest Regressor
Used for better non-linear modeling

👉 R² Score: 0.47

4️⃣ Hyperparameter Tuning (GridSearchCV)
Tuned parameters:
n_estimators: [3, 10, 30]
max_features: [2, 4, 6, 8]

✅ Best Model:

RandomForestRegressor (n_estimators=30, max_features=8)

👉 Final Score: 0.50

📈 Visualization
Histogram plots for feature distribution
Correlation heatmap
Scatter plot of latitude vs longitude colored by house price

📌 Visualization shows:

Coastal areas (near ocean) tend to have higher prices
⚠️ Challenges Faced
Missing values in dataset
Feature scaling inconsistency (caused performance drop)
Handling categorical data
Model tuning complexity
🛠️ Tech Stack
Python
NumPy
Pandas
Matplotlib
Seaborn
Scikit-learn
📂 Project Workflow
1. Load dataset
2. Data cleaning (remove null values)
3. EDA (visualization + correlation)
4. Feature transformation (log scaling)
5. Encoding categorical variables
6. Feature engineering
7. Model training (Linear Regression, Random Forest)
8. Model evaluation
9. Hyperparameter tuning
🚀 Future Improvements
Use advanced models (XGBoost, Gradient Boosting)
Improve feature scaling pipeline
Deploy using Streamlit or Flask
Add cross-validation for all models
