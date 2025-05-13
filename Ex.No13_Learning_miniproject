# Predicting Student Performance with Machine Learning

### DATE:   13-05-2025                                                                         
### REGISTER NUMBER : 212222060280
### AIM: The project aims to predict student performance (whether a student is performing above or below average) based on various factors like gender, race/ethnicity, parental level of education, lunch type, and test preparation course completion.

###  Algorithm:
Random Forest is an ensemble learning method that combines multiple decision trees to make predictions. It's particularly effective for classification tasks like predicting student performance.
Here's a breakdown of how it works:
Building the Forest:
The algorithm creates multiple decision trees, each trained on a different random subset of the data (bootstrapping) and a random subset of features.
This randomness introduces diversity and reduces overfitting, leading to better generalization.
Making Predictions:
When a new data point (e.g., a student's information) needs to be classified, it's passed through each decision tree in the forest.
Each tree makes its own prediction (e.g., above-average or below-average performance).
The final prediction is determined by aggregating the predictions of all the trees, typically by majority voting for classification tasks.
Why Random Forest is Suitable for this Project:
Handles Complex Datasets: It can handle datasets with many features, like the student performance dataset with demographics, parental background, and test scores.
Robustness: It's less prone to overfitting compared to individual decision trees, leading to more reliable predictions on unseen data.
High Accuracy: It often achieves high accuracy due to the ensemble approach and randomness.
Feature Importance: It can provide insights into which features are most important for prediction, helping to understand the factors influencing student performance.


### Program:

```
!pip install pandas numpy scikit-learn matplotlib seaborn

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

df = pd.read_csv('StudentsPerformance.csv')  # Upload this file from Kaggle
df.head()

df['average'] = (df['math score'] + df['reading score'] + df['writing score']) / 3
df['performance'] = df['average'].apply(lambda x: 1 if x > 70 else 0)
df_encoded = pd.get_dummies(df.drop(['average', 'math score', 'reading score', 'writing score'], axis=1), drop_first=True)

X = df_encoded.drop('performance', axis=1)
y = df_encoded['performance']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
model = RandomForestClassifier()
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
print("Classification Report:\n", classification_report(y_test, y_pred))

sns.heatmap(confusion_matrix(y_test, y_pred), annot=True, fmt='d', cmap='Greens')
plt.xlabel("Predicted")
plt.ylabel("Actual")
plt.title("Student Performance Confusion Matrix")
plt.show()
```
### Output:
 Accuracy: 0.585
Classification Report:
               precision    recall  f1-score   support

           0       0.62      0.65      0.64       112
           1       0.53      0.50      0.51        88

    accuracy                           0.58       200
   macro avg       0.58      0.58      0.58       200
weighted avg       0.58      0.58      0.58       200


### Result:
Thus the system was trained successfully and the prediction was carried out.
