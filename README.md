# Hybrid Probabilistic–Ensemble Framework for Early Detection 
# of Perinatal Depression

### 📚 Course: Math 5366 - Data Science Capstone | Spring 2025
### 🏫 Tarleton State University
### 👨‍🎓 Author: Emmanuel Keku (001143396)
### 👨‍🏫 Supervisor: Dr. Scott Cook

---

## 📌 Abstract
Perinatal depression affects **30–37%** of women in Pakistan,
representing a substantial but under-recognized public health 
crisis. This study developed and interpreted a predictive model 
for perinatal depression severity using the PERI_DEP dataset 
(n=14,006) from Pakistan.

Three gradient boosting models were compared:
- XGBoost
- LightGBM  
- NGBoost

The top-performing model **(XGBoost)** was interpreted using 
**SHAP** and **Partial Dependence Plots (PDPs)** to identify 
key predictors and quantify their non-linear effects.

---

## 🎯 Research Questions
1. How do XGBoost, LightGBM, and NGBoost compare in 
   predictive accuracy?
2. Do psychosocial variables significantly improve model 
   performance over baseline?
3. Which predictors show the highest global importance?
4. What non-linear dynamics do PDPs reveal about high-impact 
   predictors?

---

## 📊 Dataset
- **Name:** PERI_DEP Dataset
- **Source:** Zenodo Repository (Zafar et al., 2025)
- **Location:** Lahore & Gujranwala, Punjab, Pakistan
- **Records:** 14,006 perinatal women (aged 18–45)
- **Target Variable:** EPDS-PHQ-Total-Score (Range: 1–24)
  (Continuous measure of depression severity)

### Data Split Strategy
| Split | Records | Purpose |
|-------|---------|---------|
| Training Set | 11,204 (80%) | Model fitting & cross-validation |
| Holdout Set | 2,802 (20%) | Final unbiased evaluation |

### Key Variables
| Category | Variables |
|----------|-----------|
| **Sociodemographic** | Age, Education, Residence, Working Status |
| **Psychosocial** | Appearance Acceptance, Male Gender Preference |
| **Family** | Family System, Relationship with Mother-in-law |
| **Obstetric** | Gravida, Gestational Age, Miscarriages |
| **Children** | Number of Sons, Number of Daughters |

---

## 🛠️ Tools & Technologies
- **Language:** Python
- **Environment:** Google Colab / Jupyter Notebook
- **Modeling:** `XGBoost`, `LightGBM`, `NGBoost`
- **Explainability:** `SHAP`, Partial Dependence Plots
- **Data:** `Pandas`, `NumPy`
- **Visualization:** `Matplotlib`, `Seaborn`
- **Validation:** Stratified K-Fold Cross Validation

---

## 🏆 Results

### Model Comparison
**Table 3: Comparative Performance Metrics of Gradient Boosting Frameworks**

| Model | Split | MAE | RMSE | R² | Pearson r | IoA | CCC |
|-------|-------|-----|------|----|-----------|-----|-----|
| **XGBoost** | Train | 0.218 | 0.715 | 0.963 | 0.981 | 0.990 | 0.981 |
| **XGBoost** | **Test** | **0.881** | **1.996** | **0.713** | **0.848** | **0.920** | **0.846** |
| NGBoost | Train | 0.920 | 1.390 | 0.860 | 0.936 | 0.956 | 0.915 |
| NGBoost | Test | 1.445 | 2.215 | 0.639 | 0.799 | 0.868 | 0.755 |
| LightGBM | Train | 1.309 | 1.833 | 0.757 | 0.887 | 0.913 | 0.839 |
| LightGBM | Test | 2.000 | 2.687 | 0.479 | 0.697 | 0.783 | 0.622 |

> 🥇 **XGBoost is the best performing model** across all 
> metrics on the test set.

### Metric Definitions
| Metric | Meaning |
|--------|---------|
| **MAE** | Mean Absolute Error (lower is better) |
| **RMSE** | Root Mean Square Error (lower is better) |
| **R²** | Variance explained (higher is better) |
| **Pearson r** | Linear correlation (higher is better) |
| **IoA** | Index of Agreement (higher is better) |
| **CCC** | Concordance Correlation Coefficient (higher is better) |


### Key SHAP Findings
- 📚 **Maternal/Spousal Education** → Most important predictor
- 👩 **Maternal Age** → U-shaped risk curve
  (highest risk at extremes of reproductive age)
- 💄 **Appearance Acceptance** → Strong protective effect
  (key modifiable psychosocial factor)
- 👨‍👩‍👧‍👦 **Sons + Daughters** → Non-additive compounding 
  risk effect (cumulative caregiver strain)

---

## 💡 Key Contributions
1. 🌍 **Culturally Rich Data:** Large locally curated 
   Pakistani dataset with socio-cultural determinants
2. 📈 **Continuous Outcome Modeling:** Models depression 
   as a continuous score for granular risk stratification
3. 🎲 **Probabilistic Uncertainty Quantification:** 
   Evaluated NGBoost for robust clinical uncertainty estimates
4. 🤖 **Explainable AI Bridge:** SHAP + PDPs bridge 
   predictive modeling and clinical epidemiology

---

## 📋 Methodology

### 1. Data Preprocessing
- Stratified split by target tertiles
- Feature selection via literature review and 
  preliminary importance analysis
- Handling of missing values and categorical encoding

### 2. Model Building
- Trained XGBoost, LightGBM, and NGBoost
- Hyperparameter tuning via cross-validation
- Evaluated on holdout set

### 3. Model Interpretation
- **SHAP Values:** Global and local feature importance
- **Partial Dependence Plots:** Non-linear effect visualization
- **Subgroup Analysis:** Risk patterns across demographics

---

## 📁 Project Files
| File | Description |
|------|-------------|
| `Capstone_Emmanuel-Keku.ipynb` | Full Jupyter Notebook |

---

## 🔗 Related Projects
- [DS1: Postnatal Depression Prediction](https://github.com/Emmanuel-Keku/Postnatal-Depression-Prediction)

---

## 📚 Key References
1. Zafar et al. (2025). PERI_DEP Dataset. *Zenodo*
2. Atif et al. (2021). Perinatal depression in Pakistan.
3. Kasani et al. (2023). Gradient boosting for depression 
   prediction. 
4. Padhani et al. (2024). Perinatal mental health in 
   South Asia.

---

## 📫 Contact
- 📧 **Email:** ekekuinchrist247@gmail.com
- 🔬 **ORCID:** https://orcid.org/0000-0001-5864-4843
- 🐙 **GitHub:** https://github.com/Emmanuel-Keku
