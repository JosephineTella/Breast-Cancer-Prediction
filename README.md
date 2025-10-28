# Breast-Cancer-Prediction

<img width="274" height="211" alt="image" src="https://github.com/user-attachments/assets/f5774bd6-bf96-4619-9869-535ea452e863" />

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

  - **Feature Importance and Explainability:**
To promote interpretability, feature importance analyses were conducted using model-agnostic techniques (e.g., SHAP values or permutation importance). These analyses identified which features—such as radius, texture, concavity, perimeter, and symmetry—had the greatest influence on model predictions, thereby aligning machine-learning outcomes with biologic insight (Rabiei et al., 2022; Ghasemi et al., 2024).

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
This study demonstrates that machine learning techniques, particularly the Support Vector Classifier, can play a vital role in early breast cancer detection by analyzing complex diagnostic features. The SVC model achieved high predictive accuracy and interpretability through feature importance and SHAP analyses, underscoring the significance of concavity and geometrical metrics in tumor classification.

The findings highlight the transformative potential of data-driven approaches in medical diagnostics, offering a pathway toward faster, more accurate, and cost-effective breast cancer screening. Continued research integrating larger datasets, advanced modeling, and clinical validation will be crucial to transitioning these systems from experimental frameworks into reliable, real-world diagnostic tools.

### References

Bray, F., et al. (2024). Global cancer statistics 2022: GLOBOCAN estimates of incidence and mortality worldwide for 36 cancers in 185 countries. CA: A Cancer Journal for Clinicians. (Discussed in global cancer updates).

Frontiers in Oncology. (2024). Hussain, S., et al. Breast cancer risk prediction using machine learning: A systematic review of imaging and non-imaging features. Frontiers in Oncology. https://doi.org/10.3389/fonc.2024.1343627

Gurmessa, D. K. (2024). Explainable machine learning for breast cancer diagnosis from mammography and ultrasound: A systematic review. PubMed. 

Lundberg, S. M., & Lee, S.-I. (2017). A unified approach to interpreting model predictions. Advances in Neural Information Processing Systems (NeurIPS). 
NeurIPS Proceedings

UCI Machine Learning Repository. (1995). Breast Cancer Wisconsin (Diagnostic) dataset. Retrieved from https://archive.ics.uci.edu/dataset/17/breast%2Bcancer%2Bwisconsin%2Bdiagnostic.archive.ics.uci.edu

Wolberg, W. H., Street, W. N., & Mangasarian, O. L. (1994). Machine learning techniques to diagnose breast cancer from fine-needle aspirates. Cancer Letters, 77(2–3), 163–171. 

World Health Organization. (2025). Breast cancer fact sheet — global statistics and trends. Retrieved from https://www.who.int/news-room/fact-sheets/detail/breast-cancer


