# Project Overview

An efficient and effective recruitment process is crucial for organizational success, as top talent drives productivity, innovation, and competitiveness. Although the quality of hired candidates is relatively strong (58%), the average recruitment cost ($804.20) and time-to-fill (29.7 days) indicate significant inefficiencies. The high costs and lengthy process hinder growth and strain the budget, highlighting the need for a data-driven approach to optimize recruitment, improve efficiency, and secure top talent.
The final goal is to recommend the most effective model to improve recruitment efficiency and accuracy.

## Business Metrics
- Reduce recruitment costs by up to **45%**.  
- Reduce hiring time by up to **60%**.  
- Improve candidate quality by up to **40%**.  
- Achieve an F1 Score of **70%** or higher. 

## Authors
- Putri Apryanti as Project Manager
- Qurrata A'yun as Data Scientist
- M Faisol Akbar as Data Engineer
- Evan Fikri Mahendra as Data Analyst
  
## Dataset
The dataset (sourced from Kaggle) contains information about candidates’ demographic background, education, experience, and recruitment outcomes.  
Key attributes include:
  `Age`, `Gender`, `EducationLevel`, `ExperienceYears`, `PreviousCompanies`, `DistanceFromCompany`, `InterviewScore`, `SkillScore`, `PersonalityScore`,  `RecruitmentStrategy`, `HiringDecision`.

 ## Methodology
1. **Exploratory Data Analysis (EDA)**  
   - Analyzed distributions, correlations, and candidate characteristics.  
   - Identified key factors influencing recruitment outcomes.  

2. **Preprocessing & Feature Engineering**  
   - Handling anomaly 
   - Encoding categorical variables  
   - Feature normalization  
   - Handling imbalance class  

3. **Modeling**  
   - Models tested: Logistic Regression, Random Forest, Decision Tree, XGBoost, CatBoost  
   - Hyperparameter tuning with **RandomizedSearchCV**, **Optuna** and **GridSearchCV**  

4. **Evaluation**  
   - Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC
  
## Data Exploration & Preprocessing
The steps performed in this phase include:  
- Checking data distributions (age, experience, interview scores, etc.).  
- Handling anomalies/outliers.  
- Encoding categorical variables (e.g., Gender, EducationLevel, RecruitmentStrategy).  
- Normalizing numerical features with **StandardScaler**.  
- Feature engineering: creating more representative features.  
- Handling imbalanced classes using **SMOTE**.  
- Splitting the dataset into **train** and **test sets**.  

### Model Evaluation Results

Summary of evaluation results shows that:  
- **Logistic Regression** consistently provides a stable baseline, but with lower performance compared to other models.  
- **Decision Tree** is simple but tends to overfit with fluctuating performance.  
- **Random Forest** performs better with F1-Score consistently above 0.88.  
- **XGBoost** demonstrates significant improvement, especially after tuning, achieving F1-Score up to 0.89.  
- **CatBoost** delivers the best and most consistent performance. With GridSearch and Randomized Search it reaches an **F1-Score of ~0.92**, while Optuna also achieves a strong result (**F1-Score ~0.91**).  

**Conclusion:**  
The evaluation results show that the best performing model is **CatBoost**, optimized using **Randomized Search**, achieving **Precision = 0.93**, **Recall = 0.92**, and **F1-Score = 0.93**. This result highlights that Randomized Search was able to find a more optimal set of hyperparameters compared to GridSearch and Optuna, resulting in a superior model performance for predicting recruitment decisions.
 
## How to Run
1. Download the file `Recruitment_Prediction.ipynb` from this repository.  
2. Open the file in Jupyter Notebook or Google Colab.  
3. Run each cell sequentially.  


