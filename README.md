# AML Detection with Machine Learning
A project that applies machine learning techniques to detect suspicious transactions in a synthetic Anti-Money Laundering (AML) dataset.

## Overview
**Anti-Money Laundering (AML)** measures are critical for financial institutions to identify, prevent, and report suspicious transactions. This project uses a synthetic dataset (SAML-D) that simulates real-world banking transactions with a small fraction marked as suspicious. The goal is to effectively build and compare different machine learning models (e.g., Logistic Regression, Random Forest, XGBoost) to detect these suspicious transactions.

The dataset comes from [SAML-D on Kaggle](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml) and contains over 9 million transactions, of which ~0.1039% are flagged as suspicious. This extreme imbalance poses an interesting challenge for anomaly detection.

## Project Structure
- **`data/`**  
  You can download the data through the above link and here you can see a small sample of the transaction data.  
- **`notebooks/`**  
  - `1_EDA_Data_Prep.ipynb`: Exploratory Data Analysis (EDA), data cleaning, and preparation steps.  
  - `2_Modeling.ipynb`: Model training with various algorithms, handling class imbalance, and parameter tuning.   
- **`README.md`**  
  You are here! Provides an overview and usage instructions.

  ## Data Description
The synthetic dataset (SAML-D) includes:
- **Date/Time**: When the transaction was made.
- **Sender/Receiver Accounts**: Details of the account numbers (string/categorical).
- **Amount**: The transaction amount in the specified currency.
- **Payment Type**: E.g., credit card, debit card, ACH, wire transfer, etc.
- **Location**: The sender's and receiver's bank location (country).
- **Currency**: The currency used in the transaction (may differ for sender/receiver).
- **Laundering Type**: Is it a normal transaction of is it suspicious.
- **`is_suspicious`**: Binary flag (0 = normal, 1 = suspicious). This is our target for classification.

Due to the large size of the dataset (~9.5 million transactions), only a small sample is included in `data/` for demonstration. The full dataset can be downloaded from [Kaggle](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml).

## How to Use
 **Clone this repository**:
   ```bash
   git clone https://github.com/arezoo17/AML_Detection/edit/main/README.md


## Methods and Approach
- **Data Cleaning & EDA**: Removed duplicates, handled missing values, corrected data types (e.g., date/time), and performed exploratory analysis to understand distribution and correlations.
- **Train/Test Split**: Used an 80/20 split for training and testing. 
- **Cross-Validation**: Applied stratified 5-fold cross-validation to ensure robust performance estimation, given the highly imbalanced dataset.
- **Class Imbalance Handling**: Experimented with:
  - Class weighting in Logistic Regression.
  - SMOTE oversampling for Random Forest and XGBoost.
- **Algorithms**:
  - **Logistic Regression**: Baseline, interpretable model.
  - **Random Forest**: Ensemble method good for tabular data and potential to handle imbalance.
  - **XGBoost**: Gradient boosting framework known for high performance in classification tasks.
- **Evaluation Metrics**: Focused on **Recall** and **Precision-Recall AUC** due to the low prevalence of suspicious transactions. Also reported F1-score and ROC-AUC for completeness.
  
## Results and Key Insights



## References
1. [SAML-D dataset](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml) by Oztas et al. (2023)
2. **Oztas, B. et al. (2023)**. "Enhancing Anti-Money Laundering: Development of a Synthetic Transaction Monitoring Dataset," *2023 IEEE International Conference on e-Business Engineering (ICEBE)*, pp. 47-54, doi: 10.1109/ICEBE59045.2023.00028.
3. Additional AML resources().


## Contact
Feel free to reach out via GitHub issues or email me at [arezooamani842@gmail.com](mailto:arezooamani842@gmail.com) for any questions or suggestions.

