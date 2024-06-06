**Diabetes Dataset**

**Explanatory Data Analysis:**

The diabetes dataset is composed on 100k samples (rows) with 9 total columns. The target variable, diabetes, is binary: patient has diabetes (1), patient does not have diabetes (0). The explanatory variables are as follows:
columns_to_encode = ['gender', 'smoking_history'] -> used one hot vector
columns_to_scale = ['age', 'bmi', 'HbA1c_level', 'blood_glucose_level'] -> used standardization

columns_no_scale = ['hypertension', 'heart_disease'] -> already encoded to 0 and 1

It is important to note that the target variable, diabetes, is highly skewed. There are a total of 91500 patients that do not have diabetes and 8500 that are diabetic. This raised concerns as we trained algorithms and tested results. It is much easier to predict 0's because of how many patients do not have diabetes.

Throughout this analysis we are focusing on recall as the most important evaluation score. This is because it is more dangerous to classify a diabetic individual as healty than it is to diagnose a healthy person as having diabetes. We must focus on the error rate of individuals who have diabetes (class 1)

**Data Preparation:**

Check for outliers -> there were no outliers
Check for missing values -> there were no missing values
One Hot Vector -> applied one hot encoding to ['gender', 'smoking_history']
Standardization -> standardized the following quantitative variables ['age', 'bmi', 'HbA1c_level', 'blood_glucose_level']
Split Train, Dev, and Test Set -> used 80,000 for train, 10,000 for dev, and 10,000 for test

**Training Models:**

We fit our data to five algorithms and the recall values for class 1 (Diabetes) are as follows:

SGD Classifier: 0.716
Logistic Regression: 0.6
SVC Classifier: 0.825
KNeighbors: 0.63
Decision Tree: 0.728
We will continue with the two models with the highest recall scores -> SVC and Decision Tree

**Hypertuning Parameters:**

**Decision Tree**

The best score: 0.736664303438497
The best hyperparameters: {'criterion': 'entropy', 'max_depth': 40, 'min_samples_split': 2, 'random_state': 42}
Accuracy: 0.9551
Precision: 0.856671848722498
Recall: 0.8644210977011957
F1 Score: 0.8604930436829215
