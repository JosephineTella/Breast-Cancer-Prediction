# Breast-Cancer-Prediction
### Introduction
Breast cancer remains one of the most prevalent malignancies affecting women globally and is a leading cause of cancer-related mortality (World Health Organization, 2023). Early detection significantly improves prognosis and survival outcomes. Conventional diagnostic modalities such as mammography, ultrasound, and biopsy while effective, often depend on expert interpretation, are time-intensive, and may be subject to human variability and error (Ghasemi et al., 2024). The advent of machine learning (ML) presents a transformative opportunity: algorithms can process large volumes of clinical, imaging, and histopathologic data, identify latent patterns, and classify tumours as benign or malignant with high accuracy (Islam et al., 2022). Harnessing ML for breast cancer prediction promises to enhance accuracy, expedite diagnosis, and serve as a decision-support tool for clinicians.

### Statement of the Problem
Despite advances in screening and diagnostic technologies, a significant proportion of breast cancers are still detected at advanced stages, particularly in low-resource settings where access to experienced radiologists and advanced imaging is limited. Furthermore, vast quantities of patient and imaging data remain underutilized, as there is often no automated system to convert this data into actionable predictive diagnostics (Rabiei et al., 2022). 

### Significance of the Study
This investigation addresses a key healthcare concern by demonstrating how machine learning can be effectively employed to predict breast cancer cases. The significance of this study includes:

  •	Improving diagnostic precision by leveraging feature-rich datasets and ML algorithms (Rahebi et al., 2023).

  •	Assisting clinicians with decision-support tools that offer measurable predictions, thereby reducing reliance on subjective interpretations.

  •	Promoting early detection and intervention, which is vital for successful treatment and improved survival rates.

  •	Reducing healthcare costs through fewer unnecessary biopsies and better risk stratification.

  •	Advancing the knowledge base of AI-driven oncologic diagnostics by identifying the most predictive features and algorithmic approaches.

### Aim and Objectives
- **Aim**: To develop and evaluate machine learning models capable of accurately predicting breast cancer occurrence based on clinical and histopathological data using interpretable predictive frameworks.

- **Objectives:**
  
  - To procure and preprocess a publicly available breast cancer dataset suitable for machine learning analysis (e.g., the Breast Cancer Wisconsin (Diagnostic) dataset).
  
  - To implement multiple machine learning algorithms—including logistic regression, decision tree, support vector machine, random forest, and extreme gradient boosting—and   train them on the preprocessed data.
  
  - To evaluate each model’s performance using accuracy, precision, recall (sensitivity), F1-score, and confusion matrix, including cross-validation to assess robustness.
  
  - To perform feature importance and explainability assessments (e.g., SHAP values and permutation importance) to identify which tumour- and cell-feature variables most significantly influence predictions.
  
  - To recommend the best-performing and most interpretable model for potential integration into clinical decision-support workflows.

### Methodology
  - **Data Collection:**
This study utilized the Breast Cancer Wisconsin (Diagnostic) dataset from the UCI Machine Learning Repository, which comprises 569 samples with 30 numeric features derived from digitised cell-nucleus images and a target variable labelled as 0 (benign) or 1 (malignant).

  - **Data Preprocessing:**
Data were cleaned, prepared and, exploratory data analysis was performed. Feature scaling was performed via standardization (StandardScaler) to equalize the impact across features. The data were then split into training (80 %) and testing (20 %) sets.

  - **Model Development:**
Five machine learning algorithms were implemented:

      - Stochastic Gradient Descent (SGD): linear classifier that separates data through linear decision boundary
        
      - Logistic Regression (LR): a baseline binary classification model.
        
      - Decision Tree (DT): a tree-based model that partitions feature space by decision rules.
        
      - Support Vector Machine (SVM): an algorithm that finds optimal hyperplanes to separate classes.
        
      - Random Forest (RF): an ensemble method aggregating multiple decision trees to enhance robustness.
        
      - Extreme Gradient Boosting (XGBoost): a gradient-boosted ensemble algorithm optimized for classification accuracy.

Each model was trained on the training set and tuned (where applicable) for hyperparameters, then evaluated on the test set.

  - **Model Evaluation:** 
Performance metrics computed included accuracy (correct predictions divided by total predictions), precision (true positives divided by predicted positives), recall (true positives divided by actual positives), F1-score (harmonic mean of precision and recall), and confusion matrix (true positives, false positives, true negatives, false negatives). A 5-fold cross-validation procedure was also applied to assess model generalization.

### Feature Importance and Explainability
To promote interpretability, feature importance analyses were conducted using model-agnostic techniques (e.g., SHAP values or permutation importance). These analyses identified which features—such as radius, texture, concavity, perimeter, and symmetry—had the greatest influence on model predictions, thereby aligning machine-learning outcomes with biologic insight (Rabiei et al., 2022; Ghasemi et al., 2024).

### Conclusion
This study illustrates the feasibility and promise of machine learning in predicting breast cancer cases. Robust preprocessing, algorithmic training, and comprehensive evaluation demonstrated that certain models achieved high accuracy, precision, and sensitivity, while explainability analyses revealed key predictive features consistent with clinical understanding of malignancy. The findings indicate that ML models—particularly those offering interpretability—may serve as valuable adjuncts to clinical diagnostics, enhancing early detection, guiding interventions, and reducing diagnostic burden. Future work should focus on integrating larger, multicenter datasets, incorporating imaging modalities and genomics, and deploying predictive models within clinical workflows for real-time decision support across diverse patient populations.

### References
Ghasemi, A., Hashtarkhani, S., Schwartz, D. L., & Shaban-Nejad, A. (2024). Explainable artificial intelligence in breast cancer detection and risk prediction: A systematic scoping review. arXiv. https://arxiv.org/abs/2407.12058.

Islam, T., Kundu, A., Khan, N. I., Bonik, C. C., Akter, F., & Jihadul I. (2022). Machine learning approaches to predict breast cancer: Bangladesh perspective. arXiv. https://arxiv.org/abs/2206.14972

Rabiei, R., Ayyoubzadeh, S. M., Sohrabei, S., Esmaeili, M., & Atashi, A. (2022). Prediction of breast cancer using machine learning approaches. PMC. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9175124/

Rahebi, A. (2023). Machine learning-based models for the prediction of breast cancer recurrence. BMC Medical Informatics and Decision Making, 23(1). https://bmcmedinformdecismak.biomedcentral.com/articles/10.1186/s12911-023-02377-z

World Health Organization. (2023). Global cancer statistics. https://www.who.int/news-room/fact-sheets/detail/breast-cancer

Kumar, V., Abbas, A. K., & Aster, J. C. (2020). Robbins and Cotran pathologic basis of disease (10th ed.). Elsevier.

Spanhol, F. A., Oliveira, L. S., Petitjean, C., & Heutte, L. (2016). A dataset for breast cancer histopathological image classification. IEEE Transactions on Biomedical Engineering, 63(7), 1455–1462. https://doi.org/10.1109/TBME.2015.2496264



