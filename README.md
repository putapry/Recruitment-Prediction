# Recruitment-Prediction

Proyek machine learning untuk efisiensi rekrutmen dengan tujuan **menurunkan biaya rekrutmen, mempercepat waktu perekrutan, dan meningkatkan kualitas kandidat** yang diterima.

## Dataset
Dataset berisi informasi kandidat dan strategi rekrutmen dengan beberapa fitur:

- **Data kandidat**:  
  `Age`, `Gender`, `EducationLevel`, `ExperienceYears`, `PreviousCompanies`, `DistanceFromCompany`, `InterviewScore`, `SkillScore`, `PersonalityScore`.

- **Data rekrutmen**:  
  `RecruitmentStrategy`, `StrategyName`, `Cost`, `Time to Hire`, `Quality of Hire`.

- **Label**:  
  `HiringDecision` (diterima / tidak).

## Tujuan
1. Memprediksi keputusan penerimaan kandidat.  
2. Mengevaluasi strategi rekrutmen berdasarkan biaya, waktu, dan kualitas hire.  

## Business Metrics
- Mengurangi biaya rekrutmen hingga **45%**.  
- Mengurangi waktu rekrutmen hingga **60%**.  
- Meningkatkan kualitas kandidat hingga **40%**.
- Mencapai F1 Score **70%**. 

## Teknologi
- **Python** (Google Colab / Jupyter Notebook)  
- **scikit-learn**: Logistic Regression, Decision Tree, Random Forest, GridSearchCV, RandomizedSearchCV, preprocessing  
- **XGBoost**: XGBClassifier  
- **CatBoost**: CatBoostClassifier  
- **Optuna**: Hyperparameter Tuning  
- **Imbalanced-learn**: SMOTE untuk menangani imbalance class  
- **statsmodels**: VIF untuk mendeteksi multikolinearitas  
- **SHAP**: interpretabilitas model  
- **joblib**: penyimpanan model  
- **Pandas, Numpy, Matplotlib, Seaborn**: data processing & visualization 

## Cara Menjalankan
1. Download file `Recruitment_Prediction.ipynb` dari repository ini.
2. Buka file tersebut di Jupyter Notebook atau Google Colab.
3. Jalankan setiap cell secara berurutan.

## Data Exploration & Preprocessing
Langkah-langkah yang dilakukan pada tahap ini antara lain:
- Mengecek distribusi data (usia, pengalaman, skor interview, dll).
- Menangani data anomali.
- Encoding variabel kategorikal (misalnya Gender, EducationLevel, RecruitmentStrategy).
- Normalisasi fitur numerik dengan **StandardScaler**.
- Feature engineering: membuat kolom yang lebih representatif.
- Handling imbalance class menggunakan **SMOTE**.
- Split data menjadi **train** dan **test set**.

### Hasil Evaluasi Model

Ringkasan hasil evaluasi menunjukkan bahwa:
- **Logistic Regression** konsisten memberikan baseline yang stabil, namun performanya lebih rendah dibanding model lain.
- **Decision Tree** cukup sederhana, tetapi cenderung overfitting dengan performa yang fluktuatif.
- **Random Forest** memberikan hasil lebih baik dengan F1-Score stabil di atas 0.88.
- **XGBoost** menunjukkan peningkatan signifikan, terutama setelah tuning, dengan F1-Score hingga 0.89.
- **CatBoost** menghasilkan performa terbaik secara konsisten. Dengan GridSearch dan Randomized Search mencapai **F1-Score ~0.92**, sedangkan dengan Optuna performanya tetap tinggi (**F1-Score ~0.91**).

**Kesimpulan:**  
Hasil evaluasi menunjukkan bahwa model dengan performa terbaik diperoleh dari algoritma **CatBoost** yang dioptimasi menggunakan **Randomized Search**, dengan nilai **Precision** sebesar **0.93**, **Recall** sebesar **0.92**, dan **F1-score** sebesar **0.93**. Pencapaian ini menegaskan bahwa Randomized Search mampu menemukan kombinasi hyperparameter yang lebih optimal dibandingkan GridSearch dan Optuna, sehingga menghasilkan kinerja model yang unggul dalam memprediksi keputusan rekrutmen.


