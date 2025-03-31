
# 🏥 Patient No-Show Prediction

This project focuses on predicting whether a patient will miss a scheduled medical appointment, a common and costly problem in healthcare systems. By identifying high-risk patients, clinics can optimize appointment scheduling and improve resource management.

---

## 📊 Dataset

- Source: [Kaggle - No-show appointments](https://www.kaggle.com/datasets/joniarroba/noshowappointments)
- 110,000+ patient appointment records
- Includes demographics, health conditions, appointment timing, SMS reminders, and outcomes

---

## 🧼 Preprocessing

- Converted dates to calculate `lead-time` between scheduling and appointment
- Encoded categorical variables (e.g., Gender, Neighbourhood)
- Removed irrelevant identifiers (e.g., PatientId, AppointmentID)
- Handled class imbalance with **SMOTE** to boost model fairness

---

## 📈 Exploratory Data Analysis

- **Younger patients** and those with **longer lead times** are more likely to miss appointments
- **SMS reminders** are strongly associated with lower no-show rates
- Some **neighborhoods** have higher no-show patterns

---

## 🤖 Models Trained

- **Logistic Regression** – baseline model for interpretability
- **XGBoost Classifier** – high-performing tree-based model
- Evaluated using ROC AUC, classification reports, and SHAP

| Model                | AUC Score |
|----------------------|-----------|
| Logistic Regression  | 0.667     |
| XGBoost              | 0.732 ✅  |

---

## 🔍 Interpretability with SHAP

- Top features:
  - `lead-time` – longer wait increases no-show risk
  - `Age` – younger patients more likely to miss
  - `SMS_received` – receiving a reminder reduces risk
- SHAP visualizations explain feature impact at both global and individual levels

---

## ✅ Conclusions

- XGBoost offers strong predictive power for no-show detection
- Lead time and SMS are actionable levers for clinics to reduce no-shows
- Future work: Deploy a Streamlit app or integrate into a scheduling system

---

## 📁 Files

- `appointment_predict.ipynb` – full notebook with EDA, modeling, and SHAP analysis
- `README.md` – this project summary
