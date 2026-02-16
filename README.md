### Introduction
Breast cancer, which mainly affects women, is responsible for a high percentage of cancer-related deaths in developing countries. Early diagnosis and treatment increase the chances of survival, but with conventional diagnostic methods, errors are likely to occur along with other limiting factors, which can reduce survival rates. Incorporating machine learning has provided a platform for improving the early detection and treatment of breast cancer by leveraging insights from clinical and histopathologic datasets to accurately detect benign and malignant tumours in breast cells.

<img width="268" height="188" alt="image" src="https://github.com/user-attachments/assets/89260ef7-77d7-4921-99f5-6d2a85b60639" />

### Statement of the Problem
Most breast cancer cases are detected after they have progressed to an advanced stage, where little can be done in terms of treatment. A large number of cases come from regions where access to experienced personnel and advanced equipment is limited. Also, lack of automated systems has made it difficult to fully utilize the information provided by patient data for the early detection and treatment of breast cancer cases. This has created the need to explore viable and advanced methods, such as the use of machine learning models to accurately predict breast cancer cases

### Significance of the Study
The main significance of this study is to enhance the diagnostic precision of breast cancer cases using machine learning models

### Methodology

•	Data Collection: For this study, the Breast Cancer Wisconsin (Diagnostic) dataset which is available on the UCI Machine Learning Repository was used as case study. The dataset had a total of 569 samples with numeric features obtained from digitised cell-nucleus images, with a target variable having labels 0 as benign or 1 as malignant.

•	Data Preprocessing: Data was cleaned, prepared and, exploratory data analysis of the dataset was done. Feature scaling was performed via standardization (StandardScaler) to equalize the impact across features. The data were then split into training (80 %) and testing (20 %) sets.

•	Model Development and Evaluation: Six machine learning models were trained: Stochastic Gradient Descent (SGD), Logistic Regression (LR), Decision Tree (DT), Support Vector Machine (SVM), Random Forest (RF) and Extreme Gradient Boosting (XGBoost). The performance of the models was enhanced using hyperparameter tuning via GridSearch CV and their performances were evaluated. Their performances were evaluated based on their metrics: accuracy, precision, f1-score and recall.

•	Feature Importance and Explainability: To promote interpretability, feature importance analyses were conducted using model-agnostic techniques (e.g., SHAP values or permutation importance). These analyses identified which features—such as radius, texture, concavity, perimeter, and symmetry—had the greatest influence on model predictions, thereby aligning machine-learning outcomes with biologic insight 


### Project Visualizations

####  i.  Feature Correlation Matrix


<img width="586" height="494" alt="Screenshot 2025-10-27 150821" src="https://github.com/user-attachments/assets/10e3bc3c-ed9a-41a8-93c5-88e4b4efdfa4" />


##### Correlation matrix 

The correlation matrix and heatmap of the breast cancer dataset showed clear patterns of relationships among features, with correlation values ranging from −1.00 to +1.00. Strong positive correlations were found among size-related variables (e.g., radius, perimeter, area, and concavity), including their “worst” measurements, indicating high feature redundancy. Texture features displayed moderate correlations, while symmetry and fractal dimension had generally weak associations. Several size and concavity related features were strongly positively correlated with malignancy, whereas smoothness and symmetry showed negative correlations with the target class. Overall, the analysis revealed substantial multicollinearity, suggesting the need for feature selection or dimensionality reduction in predictive modeling.

####  ii.  Model Evaluation

##### Performance metrics of models

<img width="574" height="282" alt="Screenshot 2025-10-27 150925" src="https://github.com/user-attachments/assets/27a79754-7401-4e9f-9518-1ce8fbc59216" />


<img width="829" height="181" alt="Screenshot 2026-02-02 160558" src="https://github.com/user-attachments/assets/12cb815e-a669-4818-bc8a-a2301a1a3e80" />


The comparison of baseline and optimized versions of six classification models shows that hyperparameter tuning significantly improved performance across all metrics. At baseline, XGBoost performed best overall, followed closely by Random Forest, while Logistic Regression also showed strong recall and F1-score. Decision Tree and SVC had lower balance, and SGD recorded the weakest initial performance. After optimization, all models improved substantially, with SGD and SVC showing the most dramatic gains, exceeding 97% accuracy and 98% F1-scores. The top overall performers were the optimized SVC and Logistic Regression models, which achieved the highest recall and F1-scores, making them particularly effective for minimizing false negatives

####  iii.  Feature Importance

<img width="522" height="306" alt="Screenshot 2025-10-27 150953" src="https://github.com/user-attachments/assets/fa00e747-04b4-4280-8d8e-c24a2e2d0fe2" />


##### Features ranked by their influence on the model's output 

The permutation importance analysis for the Support Vector Classifier (SVC) showed that the most influential features were measures of cellular irregularity and variability. Radius error and mean concave points ranked highest in importance. Overall, the key features reflected geometric and boundary characteristics of cell nuclei such as radius, perimeter, area, concavity, and smoothness, highlighting their strong role in classification performance.

<img width="441" height="310" alt="Screenshot 2025-10-27 151036" src="https://github.com/user-attachments/assets/79df16c0-823e-4992-8670-82b72b5e5991" />

##### Shap values of top ten features

The Support Vector Classifier (SVC) demonstrated strong performance in distinguishing malignant from benign cases, with its predictions clarified through SHAP analysis. The most influential features were mean concave points, worst radius, and radius error, suggesting that greater tumour concavity and larger radii increase the likelihood of malignancy classification. Other key predictors, such as mean and worst concavity and worst texture, emphasize the importance of geometric and textural irregularities. Overall, the SHAP findings show that the SVC model relies on clinically relevant features, enhancing its interpretability and consistency with established diagnostic markers.

<img width="449" height="275" alt="Screenshot 2025-10-27 151053" src="https://github.com/user-attachments/assets/7e443668-ffce-4ef3-8a13-741bd0b58692" />

##### Summary plot of top ten features

The SHAP summary plot for the Support Vector Classifier (SVC) illustrated both the importance and directional impact of key features in breast cancer classification. The most influential predictors were mean concave points, worst radius, and radius error, followed by mean and worst concavity, emphasizing the importance of tumour size and shape irregularities in identifying malignancy. Higher values of concavity and radius related features were associated with malignant predictions, while lower values indicated benign outcomes. Texture features contributed moderately, serving as secondary indicators. Overall, the SHAP analysis confirmed that the SVC model bases its decisions on clinically meaningful characteristics, supporting both strong predictive performance and interpretability for clinical use.


#### iv. PCA analysis

#####  (a) PCA Analysis on logistic regression, SVM and KNN models

(i) PCA analysis summary on logistic regression, SVM and KNN models

<img width="555" height="206" alt="Screenshot 2026-01-04 002451" src="https://github.com/user-attachments/assets/17d9b924-3a28-4fd7-a554-1e0b4b1fee3c" />

The table compared Logistic Regression, SVM, and KNN models trained with and without PCA using multiple performance metrics. Overall, models without PCA performed best, achieving very high accuracy (about 97.4%) and excellent ROC-AUC (around 0.99). Applying PCA slightly reduced performance for Logistic Regression and SVM. In contrast, KNN maintained nearly identical accuracy, recall, and F1-scores with and without PCA, though with a small drop in ROC-AUC. Overall, the findings suggest that PCA was not necessary in this case, as the full feature set provided superior predictive performance, especially for linear and margin-based models.


(ii) ROC Curves of PCA and No-PCA analysis on logistic regression, SVM and KNN models

<img width="686" height="441" alt="Screenshot 2026-01-04 003034" src="https://github.com/user-attachments/assets/dac4a4e1-48c9-4be5-a780-025e9d53f0fc" />

All six models achieved AUC scores above 0.99, demonstrating outstanding ability to distinguish between classes. The ROC curves cluster near the top-left corner, indicating very high true positive rates with minimal false positives. Applying PCA resulted in only a slight AUC reduction (about 0.001–0.002), suggesting that the principal components retained most of the essential variance for classification. The nearly identical performance across linear, kernel-based, and distance-based models indicates that the dataset contains strong and consistent patterns that can be effectively captured by different modeling approaches.

##### Cluster visualization (2D PCA)


<img width="557" height="468" alt="image" src="https://github.com/user-attachments/assets/ee8168d4-510d-43e9-8c90-9a5991689e34" />

The 2D PCA visualization compared class separation across six classification pipelines using the first two principal components. In all plots, Class 0 and Class 1 formed clearly distinct clusters primarily separated along the first principal component, confirming the strong discriminative performance reflected by high AUC scores (0.992–0.996). For each algorithm, the No-PCA and PCA projections appeared very similar in cluster structure and separation, showing that PCA effectively preserved the key discriminative information and explaining the minimal AUC drop (0.001–0.002). A few misclassified points appeared near class boundaries, which is expected and consistent with AUC values slightly below perfect classification.

##### PCA Loadings

<img width="667" height="157" alt="Screenshot 2026-02-02 202634" src="https://github.com/user-attachments/assets/0220f918-599f-4793-88e4-6ff3ed419737" />

The PCA loading matrix showed how the original features contributed to the first ten principal components. PC1 was mainly driven by size-related features: mean radius, mean perimeter, and mean area, indicating it captures overall tumour size variation. PC2 also reflected size information but contrasts it with other characteristics, such as smoothness. PC4 was strongly influenced by mean texture, highlighting texture as a distinct source of variation. Mean smoothness contributed more prominently to PC5, PC6, and PC8, representing surface regularity and boundary-related characteristics rather than size. Overall, the results show that PCA combines all the related size features into one main size factor, while texture and smoothness are grouped into other separate and meaningful components.

#####  PCA feature loadings heatmap

<img width="770" height="475" alt="Screenshot 2026-02-02 210116" src="https://github.com/user-attachments/assets/671769a0-802d-4d58-8417-86abbe10a816" />

The PCA heatmap showed how the 30 original cell features contributed to the first five components (PC1–PC5). The colors show how strongly each feature affects a component and whether the effect is positive or negative.

##### PCA Variance Structure and Predictive Importance


<img width="658" height="506" alt="Screenshot 2026-01-03 235626" src="https://github.com/user-attachments/assets/130ff739-697f-482c-8386-d26bb886f124" />

The scatter plot compared each principal component’s importance for capturing data variance (x-axis) with how much it helped the model make predictions (y-axis). This showed which components were most useful for both describing the data and predicting outcomes.

##### Comparison of PCA Loadings and SHAP Importance by Principal Component


<img width="970" height="469" alt="Screenshot 2026-01-04 001841" src="https://github.com/user-attachments/assets/f5ff5dac-4f83-4d30-ae08-91569b021c95" />

The bar chart compared how much each principal component explains the data (blue bars) versus how much it helps the model make predictions (orange bars), showing which components were useful for prediction and which mainly just captured variance.

##### Explained Variance against Predictive Contribution (SHAP)


<img width="970" height="476" alt="Screenshot 2026-01-04 001900" src="https://github.com/user-attachments/assets/2f87e060-a0b0-43a7-b0c1-5286a57bd045" />

The bar chart compared explained variance (blue bars - how much data variation each component captured) versus SHAP importance (orange bars - how much each component contributed to predictions) across the first 17 principal components.


#####  (b) PCA Analysis on KMeans, Hierarchical and DBSCAN algorithms

Cluster visualizations (2D PCA) of KMeans, Hierarchical and DBSCAN algorithms

<img width="1133" height="306" alt="Screenshot 2026-01-05 113229" src="https://github.com/user-attachments/assets/1652e570-7b96-43c7-b7d3-c022df511900" />

PCA variance and Cluster Importance

<img width="376" height="498" alt="Screenshot 2026-01-05 113512" src="https://github.com/user-attachments/assets/5810a319-303a-4543-89e3-64f80f627946" />


The scatter plots show how each PCA component relates to cluster importance for K-Means (top) and Hierarchical (bottom) clustering. Both plots look very similar, confirming that the three-cluster solution is reliable.


#####  (c) PCA analysis of linear models

<img width="362" height="365" alt="Screenshot 2026-01-05 114430" src="https://github.com/user-attachments/assets/c91abec0-c47b-465d-84c2-4eaa2217b545" />

### Conclusion

The breast cancer dataset is well structured, driven mainly by tumour size and shape irregularities. Classification models distinguish malignant from benign cases with very high accuracy, and after optimization, SVC and Logistic Regression perform nearly perfectly, making them suitable for clinical application. Feature and SHAP analyses showed that concavity, radius, and variability are the most important factors for predicting malignancy. PCA captured data patterns well but did not improve predictions and slightly reduced accuracy. Regularization handled correlated features effectively without losing important information. Overall, the results showed that careful model tuning and feature handling created accurate, interpretable, and clinically meaningful predictions, while dimensionality reduction was not necessary for this dataset

