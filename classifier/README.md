# ML_Descision_tree_classifier_
Objective
Build a Decision Tree Classifier to predict heart disease using patient medical data, focusing on reducing overfitting and improving test accuracy.

Dataset
Includes features such as:

Age, RestingBP, Cholesterol, MaxHR, Oldpeak (numerical)
ChestPainType, FastingBS, ST_Slope, Sex, ExerciseAngina (categorical)
Target: HeartDisease (0 = No, 1 = Yes)

Steps
1. Data Loading
1.1 Load the dataset into a pandas DataFrame.

2. Data Cleaning
2.1 Check for null or missing values
2.2 Convert categorical columns using Label Encoding or One-Hot Encoding

3. Exploratory Data Analysis (EDA)
3.1 Plot correlation heatmap to identify relationships between numerical features
3.2 Plot category distributions (e.g., ChestPainType vs HeartDisease) to identify patterns
3.3 Identify potential key features visually

4. Initial Model Training
4.1 Train a DecisionTreeClassifier on the processed dataset
4.2 Observe performance: 100% training accuracy, ~74% test accuracy → overfitting detected

5. Model Tuning (Pre-Pruning)
5.1 Use GridSearchCV to tune:

max_depth
min_samples_split
min_samples_leaf

5.2 Retrain Decision Tree using the best parameters
5.3 Evaluate test performance after tuning

6. Evaluation
6.1 Compare training and test accuracy
6.2 Identify important features based on the final tree:

MaxHR
ChestPainType
ST_Slope


