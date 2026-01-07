# Financial Fraud Detection ML
## **Description:**
 This project implements a machine learning pipeline to detect fraudulent transactions.
 
## **Detailed workflow consists of the following steps:**

**Data Preparation:**

1. Loaded the dataset and removed irrelevant columns (nameOrig, nameDest, isFlaggedFraud).

2. Created a balanced dataset by sampling fraud and non-fraud transactions to address class imbalance, ensuring the model can learn patterns from both classes.

**Feature Processing:**

1. Identified numeric features (amount, oldbalanceOrg, newbalanceOrig, oldbalanceDest, newbalanceDest) and categorical features (type).

2. Applied StandardScaler to numeric features to normalize their range and OneHotEncoder(drop='first') to categorical features to handle categorical variables while avoiding multicollinearity.

3. Used a ColumnTransformer to apply these transformations consistently in a single step.

**Model Training:**

1. Built a Pipeline combining the preprocessing step and a LogisticRegression classifier with class_weight='balanced' to further compensate for class imbalance.

2. Trained the pipeline on the training data (X_train, y_train) so the model learns the relationship between features and fraud labels.

**Evaluation:**

1. The model was first validated on a hold-out portion of the training data, achieving 97.74% accuracy, demonstrating strong internal performance.

2. On the completely unseen final test dataset, the model achieved 97.91% accuracy, confirming that it generalizes well and effectively detects fraudulent transactions.

3. Precision, recall, and F1-score were also calculated, ensuring the model maintains good performance on the minority (fraud) class while minimizing false positives and false negatives.

## **Presetup:**

1. Download the following dataset from Hugging Face: [Click Here](https://huggingface.co/datasets/rohan-chandrashekar/Financial_Fraud_Detection) (Credits: rohan-chandrashekar)
2. Upload it and save it to your Google drive
3. Connect the notebook to your drive (First Code Cell)
4. Locate your uploaded dataset in the Files section
5. Use the three dots and "Copy Path" option to copy the relative location of your dataset
6. Replace "YOUR_PATH_HERE" with the copied path
7. Run rest of the cells normally order wise
