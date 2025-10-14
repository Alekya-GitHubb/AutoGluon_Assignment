# AutoGluon - California Housing Price Prediction

## Objective
This project demonstrates the use of **AutoGluon’s TabularPredictor** for a **regression task** — predicting median house values using the **California Housing dataset**.  
It replicates the principles of AutoML (Automatic Machine Learning), enabling end-to-end model training, hyperparameter optimization, and prediction without manual model tuning.

---

## Dataset Description
The dataset used is the **California Housing dataset** from `sklearn.datasets`.  
Each record represents aggregated census block data in California, with the target variable being:
- `MedHouseValue`: Median house value for households within a block.

### Key Features:
| Feature | Description |
|----------|--------------|
| MedInc | Median income in block group |
| HouseAge | Median house age in block group |
| AveRooms | Average number of rooms per household |
| AveBedrms | Average number of bedrooms per household |
| Population | Population per block group |
| AveOccup | Average household size |
| Latitude | Block latitude |
| Longitude | Block longitude |

---

## Workflow

1. Data Loading
   - Loaded the California housing dataset using `fetch_california_housing()`.
   - Converted to a Pandas DataFrame for analysis and model training.

2. Data Preparation
   - Split the dataset into 80% training and 20% testing using `train_test_split()`.
   - Defined the target label as `MedHouseValue`.

3. Model Training
   - Utilized `AutoGluon.tabular.TabularPredictor` with:
     ```python
     predictor = TabularPredictor(label='MedHouseValue', problem_type='regression')
     predictor.fit(train, presets='best_quality', time_limit=600)
     ```
   - Automatically performed feature engineering, model ensembling, and hyperparameter tuning.

4. Evaluation
   - Evaluated model performance using the test set.
   - Displayed AutoGluon’s leaderboard to compare model accuracy and RMSE.

5. Prediction
   - Generated predicted values for the test data.
   - Saved results to `/content/california_predictions.csv`.

6. Result Export
   - Downloaded prediction CSV for submission and GitHub artifact inclusion.

---

## Results Summary
AutoGluon automatically trained multiple regression models (LightGBM, XGBoost, CatBoost, RandomForest, NeuralNet, etc.)  
and selected the best-performing ensemble model.  
The leaderboard ranked models by **Root Mean Squared Error (RMSE)** and **R² Score**, indicating effective model performance with minimal manual tuning.

---

## Project Artifacts
| File | Description |
|------|--------------|
| `AutoGluon_California_Housing_Alekya.ipynb` | Colab notebook with full pipeline and outputs |
| `california_predictions.csv` | Model output: predicted vs actual house values |
| `README.md` | Project documentation and workflow summary |

---

## Key Learnings
- Understood how **AutoGluon automates model selection and tuning**.
- Learned to handle **tabular regression tasks** using AutoML.
- Observed how model ensembling and feature preprocessing are performed without explicit code.
- Gained experience creating **production-ready ML workflows** suitable for enterprise applications.

---

## Tools & Technologies
- **AutoGluon Tabular**
- **Python (Pandas, NumPy, Scikit-learn)**
- **Google Colab**
- **GitHub for version control**

---

## Author
Alekya Gudise
Master’s in Software Engineering — San José State University  
Data Mining Assignment — Fall 2025
