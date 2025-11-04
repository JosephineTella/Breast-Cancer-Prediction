# Breast-Cancer-Prediction

<img width="274" height="211" alt="image" src="https://github.com/user-attachments/assets/f5774bd6-bf96-4619-9869-535ea452e863" />

### Introduction

Breast cancer, which mainly affects women, is responsible for a high percentage of cancer-related deaths in developing countries. Early diagnosis and treatment increase the chances of survival, but with conventional diagnostic methods, errors are likely to occur along with other limiting factors, which can reduce survival rates. Incorporating machine learning has provided a platform for improving the early detection and treatment of breast cancer by leveraging insights from clinical and histopathologic datasets to accurately detect benign and malignant tumours in breast cells.

### Statement of the Problem
Most breast cancer cases are detected after they have progressed to an advanced stage, where little can be done in terms of treatment. A large number of cases come from regions where access to experienced personnel and advanced equipment is limited. Also, lack of automated systems has made it difficult to fully utilize the information provided by patient data for the early detection and treatment of breast cancer cases. This has created the need to explore viable and advanced methods, such as the use of machine learning models to accurately predict breast cancer cases

### Significance of the Study
The main significance of this study is to enhance the diagnostic precision of breast cancer cases using machine learning models

### Methodology
  - **Data Collection:**
For this study, the Breast Cancer Wisconsin (Diagnostic) dataset which is available on the UCI Machine Learning Repository was used as case study. The dataset had a total of 569 samples with numeric features obtained from digitised cell-nucleus images, with a target variable having labels 0 as benign or 1 as malignant.

  - **Data Preprocessing:**
Data was cleaned, prepared and, exploratory data analysis of the dataset was done. Feature scaling was performed via standardization (StandardScaler) to equalize the impact across features. The data were then split into training (80 %) and testing (20 %) sets.

  - **Model Development and Evaluation:**
Six machine learning models were trained: Stochastic Gradient Descent (SGD), Logistic Regression (LR), Decision Tree (DT), Support Vector Machine (SVM), Random Forest (RF) and Extreme Gradient Boosting (XGBoost). The performance of the models was enhanced using hyperparameter tuning via GridSearch CV and their performances were evaluated. Their performances were evaluated based on their metrics: accuracy, precision, f1-score and recall.
        
  - **Feature Importance and Explainability:**
To promote interpretability, feature importance analyses were conducted using model-agnostic techniques (e.g., SHAP values or permutation importance). These analyses identified which features—such as radius, texture, concavity, perimeter, and symmetry—had the greatest influence on model predictions, thereby aligning machine-learning outcomes with biologic insight (Gurmessa, 2024)

### Project Visualization
####  i.  Feature Correlation Matrix

<img width="586" height="494" alt="Screenshot 2025-10-27 150821" src="https://github.com/user-attachments/assets/10e3bc3c-ed9a-41a8-93c5-88e4b4efdfa4" />

Correlation matrix of features and how they are related


####  ii.  Model Evaluation

<img width="574" height="282" alt="Screenshot 2025-10-27 150925" src="https://github.com/user-attachments/assets/27a79754-7401-4e9f-9518-1ce8fbc59216" />

Preformance metrics of models

####  iii.  Feature Importance

<img width="522" height="306" alt="Screenshot 2025-10-27 150953" src="https://github.com/user-attachments/assets/fa00e747-04b4-4280-8d8e-c24a2e2d0fe2" />

Features ranked by their influence on the model's output 

<img width="441" height="310" alt="Screenshot 2025-10-27 151036" src="https://github.com/user-attachments/assets/79df16c0-823e-4992-8670-82b72b5e5991" />

Shap values of top five features

<img width="449" height="275" alt="Screenshot 2025-10-27 151053" src="https://github.com/user-attachments/assets/7e443668-ffce-4ef3-8a13-741bd0b58692" />

Summary plot of top five features

### Results
Key findings include:

  - **Correlation matrix:** The correlation analysis revealed strong interrelationships among several predictive variables, particularly those describing tumor size and shape, such as mean radius, mean perimeter, and mean area, which demonstrated high positive correlations. Concavity-related features, including mean concavity and mean concave points, also exhibited strong associations, emphasizing their shared morphological significance in differentiating malignant from benign tumors. In contrast, features such as symmetry and fractal dimension showed weak or negative correlations with other predictors, suggesting their distinct contribution to tumor irregularity.

  - **Model Evaluation:** Comparative analysis of the model revealed that the Support Vector Classifier (SVC) demonstrated the best overall performance in terms of accuracy, precision, recall, and F1-score, indicating its robustness in handling non-linear relationships within the dataset.

  - **Feature Importance:** Feature importance and SHAP value analyses showed that concavity-related parameters, such as mean concavity, mean concave points, and worst concave points, were among the strongest predictors of malignancy. Additionally, mean radius, mean perimeter, and mean area exhibited high positive correlations and were strongly associated with malignant tumor detection.

### Conclusion
This study shows that the model Support Vector Classifier had the highest performance after optimization and can help in the early detection of breast cancer cases with the aid of feature importance and SHAP analyses. The findings revealed the potential of data-driven approaches in medical diagnostics, presenting a better, more accurate, and cost-effective way for breast cancer screening. For further work, larger datasets can be incorporated with the use of more advanced models.

### References

Bray, F., et al. (2024). Global cancer statistics 2022: GLOBOCAN estimates of incidence and mortality worldwide for 36 cancers in 185 countries. CA: A Cancer Journal for Clinicians. (Discussed in global cancer updates).

Frontiers in Oncology. (2024). Hussain, S., et al. Breast cancer risk prediction using machine learning: A systematic review of imaging and non-imaging features. Frontiers in Oncology. https://doi.org/10.3389/fonc.2024.1343627

Gurmessa, D. K. (2024). Explainable machine learning for breast cancer diagnosis from mammography and ultrasound: A systematic review. PubMed. 

Lundberg, S. M., & Lee, S.-I. (2017). A unified approach to interpreting model predictions. Advances in Neural Information Processing Systems (NeurIPS). 
NeurIPS Proceedings

UCI Machine Learning Repository. (1995). Breast Cancer Wisconsin (Diagnostic) dataset. Retrieved from https://archive.ics.uci.edu/dataset/17/breast%2Bcancer%2Bwisconsin%2Bdiagnostic.archive.ics.uci.edu

Wolberg, W. H., Street, W. N., & Mangasarian, O. L. (1994). Machine learning techniques to diagnose breast cancer from fine-needle aspirates. Cancer Letters, 77(2–3), 163–171. 

World Health Organization. (2025). Breast cancer fact sheet — global statistics and trends. Retrieved from https://www.who.int/news-room/fact-sheets/detail/breast-cancer


