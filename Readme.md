# 🧠 Customer Churn Prediction — Lloyds Banking Group (Forage Job Simulation)

This project focuses on predicting customer churn using machine learning, based on structured banking data. Built as part of the **Forage x Lloyds Banking Group Job Simulation**, the goal is to derive business insights from predictive modeling while maintaining model interpretability.

---

## 📌 Objective

To develop a robust and interpretable machine learning model that predicts the likelihood of customer churn, allowing stakeholders to take proactive retention measures.

---

## ⚙️ Technologies & Libraries

- **Languages:** Python  
- **Tools:** Jupyter Notebook, VSCode  
- **Libraries:** Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib  
- **Model Used:** Random Forest Classifier  
- **XAI Methods:** SHAP (global/local feature importances), LIME (individual prediction explanations)

---

## 📊 Workflow

### 1. **Data Preprocessing**
- Null value handling
- Feature engineering (e.g., churn ratios, interaction features)
- Label encoding and scaling
- Train-Test Split

### 2. **Model Training**
- Used `RandomForestClassifier` with cross-validation
- Hyperparameter tuning using GridSearchCV (optional)

### 3. **Model Evaluation**
- Accuracy, F1-score, Confusion Matrix, ROC-AUC
- Business analysis based on churned customer segments

### 4. **Explainable AI**
- **SHAP:** Visualized global and individual prediction impacts
- **LIME:** Explained why a specific customer was predicted to churn

---

## ✅ Results

- Achieved **strong accuracy and interpretability** with Random Forest
- SHAP and LIME enabled clear understanding of key churn drivers (e.g., active product count, credit score, tenure)
- Actionable business suggestions were proposed for high-churn segments

---

## 📁 Repository Structure

```bash
.
├── Lloyd Customer Churning.ipynb     # Main notebook
├── Customer_Churn_Data_Large.xlsx   # Dataset (if included)
├── README.md                         # Project overview

## 🔍 How to Run Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/lloyds-customer-churn.git
   cd lloyds-customer-churn

2. **Install required libraries**
    ```bash
    pip install -r requirements.txt

3. **Launch the notebook**
    ```bash
    jupyter notebook "Lloyd Customer Churning.ipynb"

## 🧑‍💻 Author

**Tanishk Jain**  
- [GitHub](https://github.com/tanishhhk)  
- [LinkedIn](https://www.linkedin.com/in/tanishhhk)  

---

## 🙏 Acknowledgements

- **Lloyds Banking Group** – For providing a realistic customer churn analysis challenge through the Forage platform.  
- **Forage** – For hosting the job simulation and helping students gain hands-on experience in real-world data science tasks.  
