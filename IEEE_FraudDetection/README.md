AutoGluon – IEEE-CIS Fraud Detection (Kaggle)
----------------------------------------------

Objective:
This project applies AutoGluon’s TabularPredictor for a binary classification problem – detecting fraudulent transactions using the IEEE-CIS Fraud Detection dataset from Kaggle. The aim is to automate data preprocessing, model training, and evaluation using AutoML techniques.

Dataset Description:
- train_transaction.csv: Transaction-level features (amount, product, card info, etc.)
- train_identity.csv: Identity-based features (browser, device, IP details)
- test_transaction.csv / test_identity.csv: Test data
- sample_submission.csv: Kaggle submission format

Workflow Steps:
1. Kaggle Authentication:
   - Uploaded kaggle.json API key
   - Verified using: !kaggle --version

2. Dataset Download:
   - !kaggle competitions download -c ieee-fraud-detection
   - !unzip ieee-fraud-detection.zip -d /content/ieee

3. Data Preparation:
   - Merged transaction and identity datasets on TransactionID
   - Defined label = 'isFraud' and eval_metric = 'roc_auc'

4. Model Training:
   - predictor = TabularPredictor(label=label, eval_metric='roc_auc')
   - predictor.fit(train, presets='best_quality', time_limit=3600)

   AutoGluon handled missing data, encoding, ensembling (LightGBM, CatBoost, XGBoost, etc.), and tuning automatically.

5. Evaluation:
   - Used predictor.leaderboard() to compare AUC scores

6. Prediction and Submission:
   - Generated fraud probabilities on test data
   - Created submission file my_submission.csv
   - Submitted via Kaggle CLI

Results:
- Validation metric: ROC-AUC ≈ 0.94
- Best model: WeightedEnsemble_L2
- Submission successful on Kaggle leaderboard

Artifacts:
- AutoGluon_IEEE_FraudDetection_Alekya.ipynb (Notebook with full outputs)
- AutoGluon_IEEE_Submission_Alekya.csv         (Kaggle submission file)
- README.md                                   (This file)

Key Learnings:
- Hands-on with AutoML for classification
- Managed large dataset with memory optimization
- Understood ensemble modeling and ROC-AUC metric
- Integrated AutoGluon pipeline with Kaggle CLI

Tools & Technologies:
AutoGluon Tabular
Python (Pandas, NumPy)
Kaggle CLI
Google Colab
GitHub

