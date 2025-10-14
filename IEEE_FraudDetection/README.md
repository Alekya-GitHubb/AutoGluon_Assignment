# IEEE-CIS Fraud Detection using AutoGluon

This notebook demonstrates the use of [AutoGluon](https://auto.gluon.ai) for an end-to-end Kaggle competition pipeline.

## Steps Covered
1. **Authenticate Kaggle** using API token (`kaggle.json`)
2. **Download Dataset** for IEEE Fraud Detection
3. **Preprocess & Merge** identity and transaction data
4. **Train Model** using `TabularPredictor` (binary classification)
5. **Evaluate** best models using ROC-AUC
6. **Predict** fraud probabilities on test set (batched prediction to avoid RAM crash)
7. **Submit** predictions to Kaggle via CLI

## Output Artifacts
- `my_submission.csv` – final Kaggle submission file  
- `ieee_autogluon/` – directory containing saved AutoGluon models  
- Kaggle submission message: “Successfully submitted to IEEE-CIS Fraud Detection”

## Key Learnings
- Handling large-scale tabular datasets with AutoGluon  
- Managing memory limits in Colab via chunked prediction  
- Automating Kaggle submissions directly from Colab
