# ❤️ Heart Disease Prediction using Machine Learning

## 📌 Project Description

This project aims to build a **Machine Learning** model to predict the risk of **Heart Disease** based on patients' clinical and demographic characteristics.

The project follows a complete data mining workflow, including:

- Data Understanding
- Data Preprocessing
- Exploratory Data Analysis (EDA)
- Model Training
- Hyperparameter Tuning
- Cross Validation
- Model Evaluation
- Feature Importance Analysis
- New Patient Prediction
- Streamlit Web Application Deployment

---

# 📂 Project Structure

```text
HeartDisease/
│
├── app.py                      # Streamlit Web Application
├── heartV3.csv                 # Dataset
├── model_rf.pkl                # Trained Random Forest Model
├── scaler.pkl                  # StandardScaler Object
├── feature_names.pkl           # Feature Names
├── DataMiningPra-Uas.ipynb     # Main Jupyter Notebook
├── README.md
└── requirements.txt
```

---

# 📖 Dataset

The project uses a **Heart Disease** dataset containing patients' medical information along with a binary target indicating whether the patient has heart disease.

## Target Variable

```text
HeartDisease
```

- **0** = No Heart Disease
- **1** = Heart Disease

---

## Dataset Features

The dataset includes several important clinical features, such as:

- Age
- Gender
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Maximum Heart Rate
- Exercise Angina
- Smoking
- BMI
- Family History
- Stress Level
- Physical Activity
- Chest Pain Type

---

# ⚙️ Data Mining Workflow

## 1. Data Understanding

The first stage focuses on understanding the dataset before building the prediction model.

The following analyses were performed:

- Loading the dataset using Pandas
- Displaying the first five records
- Inspecting dataset information using `info()`
- Generating descriptive statistics using `describe()`
- Checking for missing values, especially in the **Gender** column

The objective of this stage is to understand the dataset structure and identify any potential data quality issues.

---

## 2. Data Preprocessing

Data preprocessing prepares the dataset for machine learning algorithms.

The preprocessing pipeline includes:

### Categorical Encoding

Categorical variables are converted into numerical values.

Example:

```text
Male   → 1
Female → 0

Yes → 1
No  → 0
```

The following columns are encoded:

- Gender
- ExerciseAngina
- Smoking
- FamilyHistory

---

### One-Hot Encoding

The **Chest Pain Type** feature is transformed using One-Hot Encoding, resulting in features such as:

- ChestPain_Typical
- ChestPain_Atypical
- ChestPain_Non-anginal

---

### Feature Scaling

Feature scaling is performed using

```text
StandardScaler
```

to normalize feature values and improve model performance.

---

### Train-Test Split

The dataset is divided into:

- Training Dataset
- Testing Dataset

This allows the model to be evaluated on unseen data.

---

# 🤖 Machine Learning Models

Two machine learning algorithms are implemented and compared.

## 1. Logistic Regression

The first model uses Logistic Regression with the initial parameters:

- solver = liblinear
- class_weight = balanced

Hyperparameter optimization is performed using **Grid Search**.

Parameters tuned include:

- C
- penalty

---

## 2. Random Forest

The second model uses the Random Forest algorithm.

The following parameters are optimized:

- n_estimators
- max_depth
- min_samples_split
- class_weight

The best hyperparameters are selected using **GridSearchCV**.

---

# 🔍 Hyperparameter Tuning

Both models are optimized using

```text
GridSearchCV
```

with

```text
ROC-AUC Score
```

as the evaluation metric to automatically determine the optimal parameter combination.

---

# 🔁 Cross Validation

Model performance is validated using

```text
10-Fold Stratified Cross Validation
```

Advantages of this method include:

- Reducing evaluation bias
- Producing more reliable performance estimates
- Preserving class distribution across all folds

---

# 📊 Exploratory Data Analysis (EDA)

Several visualizations are created to better understand the dataset.

### Age Distribution

A histogram is used to visualize the relationship between patient age and heart disease occurrence.

---

### Cholesterol vs Resting Blood Pressure

A scatter plot is used to observe the relationship between cholesterol levels and resting blood pressure with respect to heart disease.

---

# 🏆 Best Model Selection

After hyperparameter tuning and cross validation, both models are compared based on their ROC-AUC scores.

The model with the best performance is selected for:

- Final evaluation
- New patient prediction
- Streamlit web application deployment

---

# 📈 Model Evaluation

The selected models are evaluated using several performance metrics:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC Score

Performance is also visualized using:

- ROC Curve

Evaluation is performed on the testing dataset to measure the model's generalization capability.

---

# 📌 Model Interpretation

## Logistic Regression

Model interpretation is performed using

```text
Odds Ratio
```

to measure the influence of each feature on the probability of heart disease.

Higher Odds Ratio values indicate stronger contributions to heart disease prediction.

---

## Random Forest

Model interpretation is performed using

```text
Feature Importance
```

to identify the most influential features in the prediction process.

The results are visualized using a bar chart.

---

# 🔮 New Patient Prediction

The trained model is tested using new patient data.

Example input features include:

- Age
- Blood Pressure
- Cholesterol
- BMI
- Family History
- Physical Activity
- Stress Level
- Chest Pain Type
- Other clinical features

The prediction output includes:

- Heart Disease Risk
- No Heart Disease Risk

along with the predicted probability.

---

# 🌐 Web Application

The best-performing model is saved using

```text
pickle
```

and deployed as an interactive web application using

```text
Streamlit
```

Application features include:

- Patient data input form
- Prediction button
- Prediction probability
- Heart disease risk classification

---

# 📸 Application Preview

## Positive Prediction

<img src="images/positive.png" width="800">

---

## Negative Prediction

<img src="images/negative.png" width="800">

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/username/HeartDiseasePrediction.git
```

---

## 2. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 3. Run the Streamlit Application

```bash
streamlit run app.py
```

---

# 📦 Libraries Used

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Streamlit

---

# 🎯 Conclusion

This project successfully develops a heart disease prediction system using a complete machine learning pipeline, including data understanding, preprocessing, exploratory data analysis, model training, hyperparameter optimization, evaluation, and deployment.

Two machine learning algorithms, **Logistic Regression** and **Random Forest**, are compared using **10-Fold Stratified Cross Validation** and **GridSearchCV** to determine the best-performing model. The selected model is then deployed as an interactive **Streamlit** web application, allowing users to predict heart disease risk based on patient information efficiently and accurately.