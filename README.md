❤️ Heart Disease Prediction using Machine Learning.
📌 Overview

This project builds an end-to-end machine learning pipeline to predict the likelihood of heart disease based on clinical patient data. The goal is to assist early risk detection using data-driven decision support.

Multiple classification models were trained, evaluated, and optimized using cross-validation and hyperparameter tuning. The final system is designed to be deployment-ready and interpretable for healthcare use cases.
📊 Problem Statement

Heart disease is one of the leading causes of mortality worldwide. Early prediction using patient health parameters can significantly improve preventive care.

This project aims to:

Analyze clinical health indicators
Identify key risk factors
Build a predictive classification model for heart disease detection

📁 Dataset
Source: Cleveland Heart Disease Dataset
Samples: ~300 patient records
Features:
Age
Sex
Chest pain type (cp)
Resting blood pressure (trestbps)
Cholesterol (chol)
Maximum heart rate (thalach)
Exercise induced angina (exang)
ST depression (oldpeak)
Slope, ca, thal, etc.

🧠 Workflow
1. Exploratory Data Analysis (EDA)
Distribution analysis of clinical variables
Relationship between features and target variable
Visualization of key risk indicators (age, cholesterol, chest pain, etc.)
2. Data Preprocessing
Feature selection based on medical relevance
Encoding categorical variables
Standardization for Logistic Regression
3. Model Building

Implemented multiple classification algorithms:

Logistic Regression
Random Forest Classifier
XGBoost Classifier
4. Model Evaluation
Stratified K-Fold Cross Validation
Accuracy, Precision, Recall, F1-score
ROC-AUC analysis
5. Hyperparameter Tuning
GridSearchCV applied to Random Forest
Optimized model complexity for better generalization
Model Performance
Model	CV Accuracy	Notes
Logistic Regression	~0.80	Stable baseline model
Random Forest	~0.845	Best performing model
XGBoost	~0.73	Higher recall, lower accuracy

Final selected model: Random Forest Classifier

Best Model Configuration
RandomForestClassifier(
    n_estimators=200,
    max_depth=3,
    min_samples_split=2,
    random_state=42
)


Key Insights
Chest pain type is one of the strongest predictors of heart disease
Maximum heart rate (thalach) shows strong inverse relationship with disease risk
ST depression (oldpeak) is a significant severity indicator
Simpler models performed better due to dataset size

💾 Model Deployment

The final trained model is saved using joblib for reuse in real-world applications:
import joblib
joblib.dump(final_model, "heart_disease_model.pkl")

🔍 Prediction Example
sample = pd.DataFrame([X.iloc[0]], columns=X.columns)
final_model.predict(sample)
final_model.predict_proba(sample)

Output:

Prediction: 0 (No disease)
Probability: [0.65, 0.35]

🛠️ Tech Stack
Python
Pandas
NumPy
Scikit-learn
XGBoost
Matplotlib / Seaborn
Jupyter Notebook

📌 Future Improvements
Deploy using Streamlit for real-time predictions
Integrate SHAP for model explainability
Expand dataset for better generalization
Try deep learning models for comparison

Author

Lokesh Waran
MSc Biochemistry | Aspiring AI/ML Practitioner
Focused on Healthcare Data Science & AI Applications
If you like this project

Feel free to star ⭐ the repository and connect for collaboration opportunities.

