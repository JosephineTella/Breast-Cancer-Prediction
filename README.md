
### Project Visualizations

####  i.  Feature Correlation Matrix


<img width="586" height="494" alt="Screenshot 2025-10-27 150821" src="https://github.com/user-attachments/assets/10e3bc3c-ed9a-41a8-93c5-88e4b4efdfa4" />


##### Correlation matrix of features and how they are related

The correlation matrix and heatmap analysis of the breast cancer dataset revealed clear patterns of association among quantitative features, with coefficients ranging from −1.00 to +1.00 and distinct clusters of strong, moderate, and weak relationships. Strong positive correlations were observed among size-related variables such as mean radius, mean perimeter, mean area, and concavity, as well as among worst radius, worst perimeter, and worst area, indicating substantial feature redundancy. Moderate correlations appear among texture-related features, while symmetry and fractal dimension exhibit weak associations. Several size- and concavity-related features showed strong positive correlations with malignancy, whereas smoothness and symmetry were negatively correlated with the target class. Overall, the heatmap underscores considerable multicollinearity, highlighting the importance of feature selection or dimensionality reduction in downstream modeling.


####  ii.  Model Evaluation

##### Performance metrics of models



<img width="574" height="282" alt="Screenshot 2025-10-27 150925" src="https://github.com/user-attachments/assets/27a79754-7401-4e9f-9518-1ce8fbc59216" />



<img width="829" height="181" alt="Screenshot 2026-02-02 160558" src="https://github.com/user-attachments/assets/12cb815e-a669-4818-bc8a-a2301a1a3e80" />




The plot and table compared baseline and optimized (“best”) versions of six classification models and showed that performance improved substantially after model tuning across all metrics. Among the baseline models, XGBoost achieved the strongest overall performance (Accuracy = 96.48%, F1 = 97.24%), closely followed by Random Forest, indicating superior balance between precision and recall. Logistic Regression also performed well, with high recall (96.50%) and strong F1-score (95.33%), while Decision Tree and SVC showed comparatively lower balance, and the SGD model lagged behind with the lowest accuracy. After optimization, all models exhibited marked gains, particularly SGD and SVC, which improved dramatically to above 97% accuracy and F1-scores exceeding 98%, highlighting the impact of hyperparameter tuning. The best-performing models overall were best_svc_model and best_lr_model, which achieved the highest recall (99.66% and 98.95%, respectively) and F1-scores (98.46% and 98.27%), making them especially suitable for applications where minimizing false negatives is critical. Overall, the results demonstrate that while ensemble and boosting methods are strong performers by default, careful optimization allows even simpler or margin-based models to achieve state-of-the-art classification performance.



####  iii.  Feature Importance

<img width="522" height="306" alt="Screenshot 2025-10-27 150953" src="https://github.com/user-attachments/assets/fa00e747-04b4-4280-8d8e-c24a2e2d0fe2" />


##### Features ranked by their influence on the model's output 


The permutation importance chart for the Support Vector Classifier (SVC) model revealed that the top predictive features for classification are primarily measurements of cellular irregularity and variability, with radius_error and mean_concave_points being the most important (importance scores ≈0.055 and 0.054 respectively). Notably, six of the top ten features are either "error" metrics (measuring variability/standard error) or "worst" metrics (capturing extreme values). The features span geometric characteristics including radius, perimeter, area, concavity, and smoothness, all of which relate to the shape and boundary properties of cell nuclei.


<img width="441" height="310" alt="Screenshot 2025-10-27 151036" src="https://github.com/user-attachments/assets/79df16c0-823e-4992-8670-82b72b5e5991" />

##### Shap values of top ten features

The Support Vector Classifier (SVC) showed strong performance in distinguishing malignant from benign breast cancer cases, and its decision process was further clarified using SHAP analysis. The SHAP feature importance plot, based on mean absolute SHAP values, identified mean concave points, worst radius, and radius error as the most influential predictors, indicating that tumours with greater concavity and larger radii are more likely to be classified as malignant. Additional important features, including mean concavity, worst concavity, and worst texture, highlighted the role of both geometric and textural irregularities in malignancy detection. Overall, the SHAP results demonstrate that the SVC model relies on clinically meaningful features, supporting its interpretability and alignment with established breast cancer diagnostic markers


<img width="449" height="275" alt="Screenshot 2025-10-27 151053" src="https://github.com/user-attachments/assets/7e443668-ffce-4ef3-8a13-741bd0b58692" />

##### Summary plot of top ten features

The SHAP summary plot for the Support Vector Classifier (SVC) highlighted the relative importance and directional effects of the top predictive features used in breast cancer classification, with features ranked by mean absolute SHAP values to reflect their overall contribution. The analysis showed that mean concave points, worst radius, and radius error have the strongest influence on model predictions, followed by mean concavity and worst concavity, underscoring the critical role of tumour shape irregularities and size-related characteristics in distinguishing malignant from benign cases. Positive SHAP values indicated a shift toward malignancy, while negative values suggested benign classification, with high feature values (red) for concavity- and radius-related measures predominantly associated with malignant outcomes and low values (blue) linked to benign tumours. Texture-related features, such as worst and mean texture, contributed more modestly, providing secondary diagnostic information. Overall, the SHAP analysis confirmed that the SVC model relied on clinically meaningful features, offering both strong predictive performance and transparent, interpretable decision-making suitable for clinical decision support.


#### iv. PCA analysis

#####  (a) PCA Analysis on logistic regression, SVM and KNN models

(i) PCA analysis summary on logistic regression, SVM and KNN models

<img width="555" height="206" alt="Screenshot 2026-01-04 002451" src="https://github.com/user-attachments/assets/17d9b924-3a28-4fd7-a554-1e0b4b1fee3c" />



This table compared the classification performance of Logistic Regression, Support Vector Machine (SVM), and K-Nearest Neighbors (KNN) models trained with and without Principal Component Analysis (PCA), using accuracy, precision, recall, F1-score, and ROC-AUC as evaluation metrics. Overall, models trained without PCA achieved the strongest performance, with LogReg_NoPCA, SVM_NoPCA, and KNN_NoPCA all reaching very high accuracy (≈97.4%) and excellent discrimination (ROC-AUC ≈0.99), indicating that the original feature space already contains highly informative and well-structured signals. Applying PCA led to a modest reduction in performance for Logistic Regression and SVM, as seen in lower accuracy, recall, and F1-scores, suggesting some loss of class-discriminative information during dimensionality reduction. In contrast, KNN showed identical accuracy, recall, and F1-score with and without PCA, indicating that KNN was relatively robust to feature compression, although a slight decrease in ROC-AUC was observed. The results implied that while PCA can reduce dimensionality and model complexity, it is not strictly beneficial in this case, particularly for linear and margin-based models, as the full feature set provides superior predictive power.


(ii) ROC Curves of PCA and No-PCA analysis on logistic regression, SVM and KNN models

<img width="686" height="441" alt="Screenshot 2026-01-04 003034" src="https://github.com/user-attachments/assets/dac4a4e1-48c9-4be5-a780-025e9d53f0fc" />



All six models achieved AUC scores above 0.99, indicating exceptional discriminative ability. The curves cluster tightly in the top-left corner, showing that all models can achieve very high true positive rates with minimal false positives. Across all three algorithms, applying PCA dimensionality reduction results in only marginal performance degradation (0.001-0.002 AUC drop). This suggests that the principal components successfully capture most of the variance needed for accurate classification. Across all three algorithms, applying PCA dimensionality reduction resulted in only marginal performance degradation (0.001-0.002 AUC drop). This suggests that the principal components successfully captured most of the variance needed for accurate classification. The fact that all three very different algorithms (linear, kernel-based, and distance-based) achieved nearly identical performance suggests the dataset has strong, consistent patterns that multiple approaches can capture effectively.


##### Cluster visualization (2D PCA)


<img width="557" height="468" alt="image" src="https://github.com/user-attachments/assets/ee8168d4-510d-43e9-8c90-9a5991689e34" />


The 2D PCA (Principal Component Analysis) visualization compared predicted classes across six different classification pipelines, showing how well each model separated the two classes (Class 0 in orange, Class 1 in blue) when projected onto the first two principal components. All six scatter plots showed clear separation between Class 0 (orange cluster, primarily in negative PC1 region) and Class 1 (blue cluster, primarily in positive PC1 region). This visual separation confirmed the high AUC scores (0.992-0.996) from the ROC curve analysis. For each algorithm pair, the left (No-PCA) and right (PCA) plots looked remarkably similar in terms of class separation and cluster structure. This validates that PCA preserves the discriminative information needed for classification, explaining why performance drops were negligible (0.001-0.002 AUC).  In all the plots, there are a few orange dots within the blue cluster and vice versa, representing misclassified instances. These appear at the boundary regions where the classes overlap, which is expected and consistent with AUC scores slightly below 1.0.


##### PCA Loadings

<img width="667" height="157" alt="Screenshot 2026-02-02 202634" src="https://github.com/user-attachments/assets/0220f918-599f-4793-88e4-6ff3ed419737" />


The table presents the PCA loading matrix for the first ten principal components (PC1–PC10), showing how each original feature contributed to the transformed components. PC1 is primarily driven by size-related features—mean radius, mean perimeter, and mean area—with similar positive loadings, indicating that it captures overall tumour size variation. PC2 also reflected size information but with opposite signs, suggesting it contrasts size-related measures with other characteristics, such as smoothness. PC4 is dominated by mean texture (loading ≈ 0.60), identifying texture variation as the main source of information in this component, largely independent of size. Mean smoothness contributed more strongly to PC5, PC6, and PC8 with relatively large negative loadings, indicating that these components captured surface regularity and boundary-related variations rather than tumour size. Overall, the table showed that PCA effectively separated correlated size features into a dominant size component (PC1), while texture and smoothness are distributed across subsequent components, confirming that the original variables contribute to distinct and interpretable latent dimensions in the data.

#####  PCA feature loadings heatmap

<img width="770" height="475" alt="Screenshot 2026-02-02 210116" src="https://github.com/user-attachments/assets/671769a0-802d-4d58-8417-86abbe10a816" />


The PCA feature loadings heatmap showed how the original 30 features (cell nucleus measurements) contributed to the first five principal components (PC1-PC5). The color intensity and direction indicated the strength and sign of each feature's contribution to each component.

##### PCA Variance Structure and Predictive Importance


<img width="658" height="506" alt="Screenshot 2026-01-03 235626" src="https://github.com/user-attachments/assets/130ff739-697f-482c-8386-d26bb886f124" />


The scatter plot evaluated the relationship between PCA variance structure and predictive importance by comparing each principal component's mean absolute loading (x-axis) against its mean SHAP value (y-axis), which measured its contribution to model predictions.



##### Comparison of PCA Loadings and SHAP Importance by Principal Component


<img width="970" height="469" alt="Screenshot 2026-01-04 001841" src="https://github.com/user-attachments/assets/f5ff5dac-4f83-4d30-ae08-91569b021c95" />

The bar chart directly compared PCA loading strength (blue bars) versus SHAP importance (orange bars) for each principal component, making it easy to see which components contributed to model predictions versus which just captured variance.


##### Explained Variance against Predictive Contribution (SHAP)


<img width="970" height="476" alt="Screenshot 2026-01-04 001900" src="https://github.com/user-attachments/assets/2f87e060-a0b0-43a7-b0c1-5286a57bd045" />

The bar chart compares explained variance (blue bars - how much data variation each component captures) versus SHAP importance (orange bars - how much each component contributes to predictions) across the first 17 principal components.

#####  (b) PCA Analysis on KMeans, Hierarchical and DBSCAN algorithms

Cluster visualizations (2D PCA) of KMeans, Hierarchical and DBSCAN algorithms

<img width="1133" height="306" alt="Screenshot 2026-01-05 113229" src="https://github.com/user-attachments/assets/1652e570-7b96-43c7-b7d3-c022df511900" />

PCA variance and Cluster Importance

<img width="376" height="498" alt="Screenshot 2026-01-05 113512" src="https://github.com/user-attachments/assets/5810a319-303a-4543-89e3-64f80f627946" />


#####  (c) PCA analysis of linear models

<img width="362" height="365" alt="Screenshot 2026-01-05 114430" src="https://github.com/user-attachments/assets/c91abec0-c47b-465d-84c2-4eaa2217b545" />

