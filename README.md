<div style="gap: 20px; max-height:200px;">
  <img src="https://learn.utoronto.ca/themes/custom/de_theme/logo.svg" alt="UofT Logo" height="50">
  <img src="https://datasciences.utoronto.ca/wp-content/uploads/2021/12/Logo.png" alt="Data Sciences Logo" height="50" ">
</div>

# UofT | DSI - Team Project: 🔎 Heart Failure Prediction

![Heart](https://blog.bswhealth.med/wp-content/uploads/2019/06/thoracic-aorta-2000x1200.jpg)

## 🔍 Business Question
> Can heart failure be accurately predicted using only demographic and baseline pre-stress test data, without the need to conduct exercise stress tests? The goal is to explore whether machine learning models can predict heart disease risk by utilizing only basic data available prior to stress testing.

## 🛠️ Why Address This Problem?

### Value to Patients
- **Accessible Screening**: Early detection for high-risk patients without stress testing, benefiting remote or resource-limited settings.
- **Reduced Burden**: Stress tests can be physically and emotionally taxing; using baseline data streamlines diagnosis and supports proactive care.

### Value to Healthcare Providers
- **Efficiency**: Baseline data models allow quick preliminary screening, saving time for acute cases.
- **Data-Driven Decisions**: Machine learning insights enhance diagnostic accuracy and care quality.

### Value to the Healthcare System
- **Cost Savings**: Reducing unnecessary stress tests can save significant resources (e.g., Ontario spends ~C$300M annually on ~500,000 non-invasive cardiac tests).

---

## 🎯 Project Overview
This project analyzes a dataset containing clinical and demographic features to predict heart disease events. The goal is to create a machine learning model capable of predicting the likelihood of heart disease using only basic patient data, improving accessibility to heart disease screening and potentially reducing mortality rates.

---

## 📊 Dataset
We are using the [Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/data) which includes:
* 11 clinical features (2 demographic and 9 medical measurements)
* Binary classification target (Heart Disease: Yes/No)

---

## 👥 Team Members

- **[Alfredo Natal](https://github.com/asnjunior)**
- **[Calen Lau](https://github.com/514ccmtl)**
- **[Juan Jimenez-Valero](https://github.com/actually-not-an-username)**
- **[Sehroz Khan](https://github.com/sehroz)
  <a href="https://www.linkedin.com/in/sehroz" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" alt="LinkedIn" height="20"></a>
  <a href="https://sehroz.com" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/c/c4/Globe_icon.svg" alt="Website" height="20"></a>**
- **[Vivien Yuen](https://github.com/vivyuen)**

---

## 🎥 Project Video

- [Sehroz Khan: Video](https://drive.google.com/file/d/1pRQOlk_Dy2iykZyWfIYfJ85DiYqEu5u5/view?usp=drive_link)
- [Calen Lau: Video](https://1drv.ms/v/c/42d723503c0d79fe/EezWu4Ir16BNureapc3NyeQByXwRV8TmCHuu9V0iU0cXeg?e=wfnKN2)
- [Vivien Yuen: Video](https://youtu.be/Ee52x14EkmY)

---

## 🏗️ Project Folder Structure

```markdown
|-- data
|   |-- processed     
|   |-- raw           
|-- experiments
|   |-- model_development  
|-- models
|   |-- logistic_regression  
|   |-- neural_networks      
|   |-- xgboost            
|-- reports
|   |-- figures   
```

---

## 🏁 Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/sehroz/heart-failure-prediction.git
cd heart-failure-prediction
```

2. Create and activate conda environment:
```bash

conda env create -f environment.yml

conda activate heart-ml
```

3. Run Jupyter Notebook:
```bash
jupyter notebook
```

----

## 💡 Project Context

Cardiovascular diseases (CVDs) are the number 1 cause of death globally, taking an estimated 17.9 million lives each year, which accounts for 31% of all deaths worldwide. Four out of 5 CVD deaths are due to heart attacks and strokes, and one-third of these deaths occur prematurely in people under 70 years of age. Heart failure is a common event caused by CVDs, and this dataset contains 11 features that can be used to predict a possible heart disease.

People with cardiovascular disease or at high cardiovascular risk (due to the presence of one or more risk factors such as hypertension, diabetes, hyperlipidemia, or already established disease) need early detection and management, where a machine learning model can be of great help.

---

## 📋 Attribute Information

- **Age:** Age of the patient [years]
- **Sex:** Sex of the patient [M: Male, F: Female]
- **ChestPainType:** Chest pain type [TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal Pain, ASY: Asymptomatic]
- **RestingBP:** Resting blood pressure [mm Hg]
- **Cholesterol:** Serum cholesterol [mg/dl]
- **FastingBS:** Fasting blood sugar [1: if FastingBS > 120 mg/dl, 0: otherwise]
- **RestingECG:** Resting electrocardiogram results [Normal: Normal, ST: ST-T wave abnormality, LVH: Left ventricular hypertrophy]
- **MaxHR:** Maximum heart rate achieved [Numeric]
- **ExerciseAngina:** Exercise-induced angina [Y: Yes, N: No]
- **Oldpeak:** ST depression induced by exercise [Numeric]
- **ST_Slope:** The slope of the peak exercise ST segment [Up: upsloping, Flat: flat, Down: downsloping]
- **HeartDisease:** Target class [1: heart disease, 0: Normal]

---

## 📋 Main Findings

### Insights
1. **Stress Testing**: Baseline data offers reasonable predictions, but incorporating stress tests enhances diagnostic accuracy.
2. **Model Performance**: XGBoost outperformed other models, showing robust predictive ability. Neural Networks required more tuning but captured complex relationships.
3. **Minimizing False Negatives**: Prioritized recall to reduce the risk of undiagnosed heart disease.

### Challenges & Solutions
- **Feature Encoding**: Used one-hot encoding for categorical variables like `ChestPainType`.
- **New Model Adoption**: Successfully implemented XGBoost using documentation and GridSearch, despite limited prior experience.
- **Explainability**: Enhanced interpretability of Neural Networks using SHAP values.

---

## 🧪 Results and Insights

### Model Performance:
The **XGBoost model** demonstrated the highest accuracy (**92%**) and F1-score, making it the best-performing algorithm among the models tested (Logistic Regression, Neural Networks, and XGBoost).

### Feature Importance:
The top predictors of heart disease include:
1. **Age**: Higher age groups show increased risk.
2. **ST_Slope**: A flat or down-sloping ST segment strongly correlates with heart disease.
3. **ChestPainType**: Asymptomatic cases exhibit the highest risk factor.
4. **ExerciseAngina**: Strongly linked to higher disease likelihood.
5. **Oldpeak**: ST depression during exercise was a significant indicator.

---

## 📊 Data Analysis & Results

<div style="display: flex; justify-content: space-between; align-items: center; gap: 10px; overflow-x: auto; margin: 20px 0;">
   <img src="reports/figures/age_distribution.png" alt="Age Distribution" height="50"/>
   <img src="reports/figures/gender_distribution.png" alt="Gender Distribution" height="50"/>
   <img src="reports/figures/correlation_heatmap.png" alt="Correlation Heatmap" height="50"/>
   <img src="reports/figures/lr_feature_importance_baseline.png" alt="Baseline Feature Importance" height="50"/>
   <img src="reports/figures/lr_feature_importance_all.png" alt="All Features Importance" height="50"/>
   <img src="reports/figures/roc_curve_baseline.png" alt="ROC Curve Baseline" height="50"/>
   <img src="reports/figures/roc_curve_all_features.png" alt="ROC Curve All Features" height="50"/>
   <img src="reports/figures/shap_values_all_features.png" alt="SHAP Values Analysis" height="50"/>
</div>

---

## 🎧 Project Overview Audio

Listen to the project report:

[Heart Failure Project Report (1).webm](https://github.com/user-attachments/assets/01166a0f-4904-4a25-a02c-82e5ada6d6c6)

To learn more about our methodology, results, and insights, view the complete [**project report**](https://github.com/sehroz/heart-failure-prediction/tree/main/reports).

---

[![Forks](https://img.shields.io/github/forks/sehroz/heart-failure-prediction)](https://github.com/sehroz/heart-failure-prediction/network/members)
[![Contributors](https://img.shields.io/github/contributors/sehroz/heart-failure-prediction)](https://github.com/sehroz/heart-failure-prediction/graphs/contributors)
[![Top Language](https://img.shields.io/github/languages/top/sehroz/heart-failure-prediction)](https://github.com/sehroz/heart-failure-prediction)


