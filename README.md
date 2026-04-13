
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

**Research Questions**

To achieve the specified goal, the following objectives were addressed:
1. To conduct literature review on existing studies on claim prediction on imbalanced data.
2. To analyze characteristics, data attributes and pre-processing techniques for accurate claim
prediction in an imbalanced motor insurance dataset.
3. To develop a machine learning model for claim prediction using imbalance handling techniques.
4. To evaluate models based on suitable metrics for handling unbalanced data.

**Conceptual Framework**
The process flown of the conceptual framework is grounded in two key theoretical frameworks: risk theory, which models insurance risk through claim frequency and severity, and cost-sensitive learning, which addresses class imbalance by assigning higher misclassification costs to the minority class. From these foundations, two independent variables are defined—risk-factor features derived from frequency and severity, and cost-sensitive learning approaches using cost matrices and threshold adjustments—each contributing differently to prediction performance. Data balancing techniques such as SMOTE, ADASYN, and oversampling act as a mediating factor, ensuring that imbalanced data is corrected before model training. Operationally, the system involves data balancing, model training using algorithms like Random Forest and Gradient Boosting, and prediction of outputs including claim probability and expected loss (calculated as frequency × severity). A feedback loop enables continuous improvement through threshold tuning and cost adjustments. Finally, performance is evaluated using metrics suited for imbalanced data, particularly Recall, F1-score, and AUC-ROC, with emphasis on accurately predicting the minority “claim” class.
<img width="246" height="386" alt="image" src="https://github.com/user-attachments/assets/74a6e4f9-bc08-4f4a-9493-eeeb6c3b3c89" />

**System Architecture**
There are five main modules in the system architecture illustrated in Figure below. The Data Input
and Preprocessing Module handled ingestion and preparation of the motor insurance dataset. The
cleaned data was then converted into model-ready features via the Feature Engineering Module.
The Model Training Module was used to train several machine learning models using data balancing
approaches. The Model Evaluation Module used threshold optimization and classification metrics to
evaluate the model’s performance. In order to predict insurance claims in real time, the Deployment
Interface Module serialized the chosen model, exposed it via a FastAPI service, and linked it to the
Streamlit analytics dashboard.
<img width="761" height="277" alt="image" src="https://github.com/user-attachments/assets/58a1e1b2-b117-4678-891f-92fff96585f9" />

**Repository Contents**

This repository contains models and analysis for motor insurance claims.<br>
For reproducibility, when setting up your Notebook environment, run: pip install -r requirements.txt

**Streamlit App**

https://claim-prediction-streamlit.onrender.com/

**Setup Instructions**

The project can be set up locally by first cloning the repository from GitHub to the user’s machine. This is done by copying the repository link and running the command git clone <repository-url> in the terminal, then navigating into the project folder using cd <project-folder>. After cloning, a Python virtual environment should be created to isolate project dependencies. On Windows, this can be done using python -m venv venv, followed by activating it with venv\Scripts\activate, while on macOS or Linux the activation command is source venv/bin/activate. Once the environment is active, all required packages should be installed using pip install -r requirements.txt. These dependencies typically include Streamlit, FastAPI, Uvicorn, pandas, scikit-learn, imbalanced-learn, joblib, and any other libraries used in model training and deployment.
After installation, the saved trained model file, such as claim_model.pkl, should be placed in the project directory together with the application files, for example main.py for the FastAPI backend and app.py for the Streamlit frontend. The FastAPI service is then started using the command uvicorn main:app --reload, which launches the prediction API locally, usually at http://127.0.0.1:8000. Once the API is running successfully, the Streamlit dashboard can be launched in a separate terminal using streamlit run app.py. This opens the dashboard in a browser, providing an interface where users can input customer, vehicle, and policy details for claim risk prediction. To validate the model using the Streamlit dashboard, the user navigates to the Prediction section and enters values such as customer age, annual premium, driver experience, vehicle value, vehicle age, engine capacity, third-party cover status, use purpose, region, policy term, and gender. When the prediction action is triggered, the dashboard sends the entered data to the FastAPI endpoint, which applies the trained machine learning pipeline and returns the prediction result. The returned output indicates the predicted claim risk class and the associated probability score. Validation is performed by testing the dashboard with multiple sample records and confirming that predictions are generated correctly, consistently, and in line with expected model behavior. 


