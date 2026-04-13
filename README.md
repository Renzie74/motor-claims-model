# Motor Claims Model

This repository contains models and analysis for motor insurance claims.<br>
For reproducibility, when setting up your Notebook environment, run: pip install -r requirements.txt

**Abstract**
The vast datasets present in the insurance sector make big data solutions highly suitable for predictive analytics. However, machine learning applications such as claim prediction are often affected by class imbalance, where claim events (minority class) are significantly fewer than non-claims, leading to poor minority class detection. This study aimed to improve motor insurance claim prediction by mitigating minority class misclassification using imbalance handling techniques. The CRISP-DM framework was used to guide the end to end modeling process. A structured pipeline involving data preprocessing, feature engineering, and exploratory data analysis was implemented on a motor insurance dataset. Imbalance handling techniques, in
cluding Synthetic Minority Oversampling Technique (SMOTE), Adaptive Synthetic Sampling (ADASYN), and Random Oversampling, were applied in combination with ensemble learning algorithms such as Random Forest, Gradient Boosting, XGBoost, and AdaBoost. Model performance was evaluated using metrics suitable for imbalanced datasets, including Precision,
Recall, F1-score, and ROC-AUC. Experimental results showed that initial models achieved low minority class performance, with the highest F1-score of 0.38. After hyperparameter tuning, performance improved significantly, with Random Forest achieving an F1-score of 0.529. Further optimization identified AdaBoost with ADASYN and XGBoost with SMOTE as the
best-performing models on unseen data, both achieving an F1-score of 0.53. However, AdaBoost with ADASYN provided a better balance between precision and recall, achieving a recall of 0.972 with fewer false positives compared to XGBoost. The study concluded that combining ensemble learning with adaptive resampling techniques significantly improves minority class detection. It recommended the adoption of balanced evaluation metrics and robust preprocessing pipelines for real-world insurance applications.
**Keywords**: Minority Class, Imbalanced data, Machine Learning, Claim Prediction, Ran
dom Forest, XGBoost, Adaboost

**Problem Statement**
The critical challenge faced in claim prediction is the disproportionate data distribution where the number of claims instances are generally fewer compared to the majority non-claims instances. This is a real-world data challenge seen in most sectors such as health insurance, life and liability insurance. The imbalanced data problem affects the forecasting abilities
of machine learning models since conventional algorithms tend to focus on increasing the overall accuracy of the model by favoring the majority class. This causes the prediction of the minority class, claims, to be worse off. Models trained on uneven data frequently demonstrate higher false negative rates (Brandt and Lanz´en, 2021). This results in substantial
financial losses due to incorrect capital reserves, undetected fraud and lost opportunity for risk mitigation. To ensure better performance of models, the class imbalance in motor insurance should be addressed using imbalanced data handling techniques such as cost-sensitive learning, SMOTE or ADASYN to reduce bias towards the minority claims class (Brandt and Lanz´en, 2021). These techniques combined with robust machine learning techniques will provide models with improved
predictive performances.
Some of the stakeholders who can benefit from this solution are:
1. Risk Manager: For effective capital management and solvency strategy.
2. Underwriters and Insurance Actuaries: For premium determination, policy evaluation and
risk evalauation.
3. Claims Department: For fraud detection and effective claims processing.

**ResearcH Questions**
To achieve the specified goal, the following objectives were addressed:
1. To conduct literature review on existing studies on claim prediction on imbalanced data.
2. To analyze characteristics, data attributes and pre-processing techniques for accurate claim
prediction in an imbalanced motor insurance dataset.
3. Todevelop a machine learning model for claim prediction using imbalance handling techniques.
4. To evaluate models based on suitable metrics for handling unbalanced data.

**Conceptual Framework**
<img width="246" height="386" alt="image" src="https://github.com/user-attachments/assets/74a6e4f9-bc08-4f4a-9493-eeeb6c3b3c89" />


