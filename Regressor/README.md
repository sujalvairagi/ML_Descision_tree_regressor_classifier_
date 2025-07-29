1. Project Overview  
This project uses a Decision Tree Regressor to predict median house values in California. The dataset includes housing and location-related features such as income, house age, and geography.

2. Dataset Summary  
- Source: sklearn.datasets.fetch_california_housing  
- Rows: 20,640  
- Features: 8 numeric predictors  
- Target: MedHouseVal (median house value in $100,000s)  

3. Workflow Breakdown  

3.1 Load and Inspect Data  
- Loaded dataset using fetch_california_housing(as_frame=True)  
- Verified no nulls and all numeric columns  

3.2 Correlation and EDA  
- Plotted correlation heatmap  
- Found MedInc most strongly correlated with target (~0.69)  
- Scatterplot showed upward trend: MedInc vs MedHouseVal  

3.3 Preprocessing  
- Split data: 80% train, 20% test  
- No scaling required (tree-based model)  

3.4 Base Model Training  
- Trained DecisionTreeRegressor with default parameters  
- Results:  
  - Train R²: 1.000 (overfitting)  
  - Test R²: 0.622  
  - RMSE: 0.704  
  - MAE: 0.455  

3.5 Hyperparameter Tuning  
- GridSearchCV used on:  
  - max_depth: [3, 5, 7, 10, None]  
  - min_samples_split: [2, 5, 10]  
  - min_samples_leaf: [1, 2, 4]  
- Best parameters:  
  - max_depth = 10  
  - min_samples_leaf = 4  
  - min_samples_split = 2  

3.6 Final Model Evaluation  
- Test R²: 0.688  
- RMSE: 0.639  
- MAE: 0.431  
- Overfitting reduced and generalization improved  

4. Feature Importance  

5. Model Saving  
Used joblib to save the final model:

