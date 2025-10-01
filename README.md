## Recruitment Prediction - Pancarona Group
Final Project - Data Science by Rakamin Batch 57 Kelompok 1

## Authors
- Putri Apryanti as Project Manager
- Qurrata A'yun as Data Scientist
- M Faisol Akbar as Data Engineer
- Evan Fikri Mahendra as Data Analyst

## Project Overview

An efficient and effective recruitment process is crucial for organizational success, as top talent drives productivity, innovation, and competitiveness. Although the quality of hired candidates is relatively strong (58%), the average recruitment cost ($804.20) and time-to-fill (29.7 days) indicate significant inefficiencies. The high costs and lengthy process hinder growth and strain the budget, highlighting the need for a data-driven approach to optimize recruitment, improve efficiency, and secure top talent.
The final goal is to recommend the most effective model to improve recruitment efficiency and accuracy.

## Business Metrics
- Reduce recruitment costs by up to **45%**.  
- Reduce hiring time by up to **60%**.  
- Improve candidate quality by up to **40%**.  
- Achieve an F1 Score of **70%** or higher. 
  
## Dataset
The dataset (sourced from Kaggle) contains information about candidates’ demographic background, education, experience, and recruitment outcomes.  
Key attributes include:
  `Age`, `Gender`, `EducationLevel`, `ExperienceYears`, `PreviousCompanies`, `DistanceFromCompany`, `InterviewScore`, `SkillScore`, `PersonalityScore`,  `RecruitmentStrategy`, `HiringDecision`.

## Methodology
1. **Exploratory Data Analysis (EDA)**  
   - Analyzed distributions, correlations, and candidate characteristics.  
   - Identified key factors influencing recruitment outcomes.  

2. **Preprocessing & Feature Engineering**  
   - Handling anomalies 
   - Encoding categorical variables  
   - Normalizing numerical features with **StandardScaler**.
   - Create new features to enhance model performance (e.g., **TotalScore**, **AvgJobTenure**, **Skill_Experience_Interaction**).
   - Select the most relevant features for modeling using **Feature Importance**
   - Handling imbalanced classes using **SMOTE**.  
   - Splitting the dataset into **train** and **test sets**. 

3. **Modeling**  
   - Models tested: **Logistic Regression, Random Forest, Decision Tree, XGBoost, CatBoost**  
   - Hyperparameter tuning with **RandomizedSearchCV**, **Optuna** and **GridSearchCV**  

4. **Evaluation**  
   - Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC
  
## Model Evaluation Results

Summary of evaluation results shows that:  
- **Logistic Regression & Decision Tree**: Stable performance (F1 ≈ 0.86 and 0.84). Hyperparameter tuning had no meaningful impact.
- **Random Forest**: Strong baseline (F1 ≈ 0.88). Slight improvement with GridSearch (0.886), and consistent gains with Randomized Search & Optuna (≈ 0.882 and 0.899).
- **XGBoost**: Highly responsive to tuning. Improved from baseline 0.874 → GridSearch 0.899 → best with Randomized Search & Optuna (0.907).
- **CatBoost**: Strongest performer. High baseline (0.908) further optimized with Optuna to 0.913.

**Conclusion**: Based on a comprehensive analysis of the **F1 Score** metric, the best model to apply is **CatBoost** with hyperparameter tuning using **Optuna**.

## Business Impact
- Cost Efficiency – Machine Learning implementation is projected to reduce recruitment costs by up to 36%, lowering the average cost per hire from around $804.20 to $511.0.
- Time-to-Hire Reduction – The recruitment process can be shortened by 36%, cutting the average hiring time from 29.7 days to about 18.9 days.
- Improved Candidate Quality – Candidate quality is expected to increase by 57%, raising the success rate of qualified hires from 58% to approximately 91.3%.

## Business Recommendation

- Utilize the Dashboard for Data-Driven Selection: Use the Dashboard for Real-Time Scoring by Inputting interview and test data directly. Prioritize candidates using the “Recruitment Score” and “Prediction Status”.
- Creating a 'Considered' candidate category: Establish a score threshold that separates candidates into 'Hired', 'Considered', and 'Not Hired'.
- Implement Model Monitoring and Regular Retraining: Conduct model evaluation every 6–12 months using the latest recruitment data.
- Optimize Recruitment Strategies: Prioritize budget and resources for Strategy 1, while maintaining Strategy 2 and 3 as complementary channels to ensure diversified candidate sources.
- Implement Fast-Track Pathway for High-Potential Candidates: Create a special recruitment track for candidates with high experience and education level 4.
- Adopt Automated Scoring with Cut-Off Thresholds: Set a minimum cut-off score across the three assessment aspects to streamline candidate screening. 
 
## How to Run
1. Download the file `Recruitment_Prediction.ipynb` from this repository.  
2. Open the file in Jupyter Notebook or Google Colab.  
3. Run each cell sequentially.  


