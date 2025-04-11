# 🫀 Heart Failure Prediction using Machine Learning

## 🔍 Introduction  
Heart failure prediction aims to identify individuals at risk of developing this condition using clinical data and machine learning techniques. Heart failure occurs when the heart cannot pump blood effectively, often as a consequence of underlying cardiovascular diseases.

Cardiovascular diseases (CVDs) are the leading cause of death worldwide, responsible for approximately **17.9 million deaths per year**, which represents **31% of all global deaths**. Four out of five CVD deaths are due to heart attacks and strokes, and **one-third occur prematurely in people under 70 years old**. Heart failure is a common outcome related to these conditions.

Machine learning models can assist in **early detection and clinical decision-making**, especially for individuals with risk factors such as hypertension, diabetes, hyperlipidemia, or a history of cardiovascular disease.

---

## 🎯 Objective  
- Identify the **most relevant clinical features** to predict heart failure  
- Train a **supervised machine learning model** capable of accurately classifying heart failure risk  

---

## 🧠 Dataset — Features

| Feature | Description |
|--------|-------------|
| **Age** | Patient's age (years) |
| **Sex** | Gender *(0: Female, 1: Male)* |
| **ChestPainType (cp)** | Type of chest pain *(TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal Pain, ASY: Asymptomatic)* |
| **RestingBP (trtbps)** | Resting systolic blood pressure *(mm Hg)* |
| **Cholesterol (chol)** | Cholesterol level *(mg/dl)* |
| **FastingBS (fbs)** | Fasting blood sugar *(0: normal, 1: > 120 mg/dl)* |
| **RestingECG (restecg)** | Resting electrocardiogram result *(0: normal, 1: ST-T abnormality, 2: left ventricular hypertrophy)* |
| **MaxHR (thalach)** | Maximum heart rate *(between 60 and 202 bpm)* |
| **ExerciseAngina (exng)** | Exercise-induced angina *(0: Yes, 1: No)* |
| **Oldpeak** | ST depression induced by exercise (numeric value) |
| **ST_Slope (slp)** | Slope of the ST segment *(0: upsloping, 1: flat, 2: downsloping)* |
| **caa** | Number of major coronary vessels obstructed *(0 to 4)* |
| **thall** | Thallium stress test result *(0: undefined, 1: fixed defect, 2: reversible defect, 3: normal)* |
| **HeartDisease** | Target class *(1: High risk, 0: Normal)* |

---

## 📐 Modeling and Evaluation

This project followed an experimental approach with several classification algorithms, applying **pipelines for preprocessing, feature selection, and cross-validation**. Main steps:

- Data scaling using `StandardScaler`  
- Feature selection with `SelectKBest(f_classif)`  
- Hyperparameter tuning with `GridSearchCV`  
- Evaluation using `StratifiedKFold` and classification metrics

### 🧪 Algorithms Tested
- Random Forest  
- Extra Trees Classifier  
- K-Nearest Neighbors (KNN)  
- Gaussian Naive Bayes  
- Quadratic Discriminant Analysis (QDA)  
- Logistic Regression  
- Support Vector Machine (SVM)  
- Initial benchmarking using `LazyClassifier`

### ✅ Final Model Selected
The best performance was achieved with **QDA (Quadratic Discriminant Analysis)**.  
This model was selected based on a combination of classification performance and simplicity.

- **Pipeline:** `StandardScaler + QDA`  
- **Hyperparameter tuned:** `reg_param` via `GridSearchCV`  
- **Test accuracy:** around **87%**

### 📊 Metrics Used
- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Confusion Matrix

---

## 💾 Model Saving

The final trained model was saved using `joblib` for future use:

```python
joblib.dump(model.best_estimator_, 'Heart_Failure_Prediction_QDA_model.joblib')
```

---

## 🧠 Conclusion

Machine learning proved to be effective for heart failure prediction using clinical data. The QDA model offered solid performance and efficiency, making it suitable for real-world triage applications.

Future improvements may include:
- Explainability with SHAP/LIME  
- Testing in production environments  
- Deployment as an API or clinical application

---

### 👨‍💻 About the Author

**André Rizzo**  
📊 Senior Data Scientist | Statistician | MBA in AI and Big Data (USP)  
🧠 Expert in Machine Learning, Deep Learning and Statistical Modeling  
📍 Rio de Janeiro, Brazil  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-0077B5?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andrerizzo1)  
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?logo=github&logoColor=white)](https://github.com/andrerizzo)  
[![Email](https://img.shields.io/badge/Email-andrerizzo@hotmail.com-D14836?logo=gmail&logoColor=white)](mailto:andrerizzo@hotmail.com)

---

*Last updated: March 28, 2025*
