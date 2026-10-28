# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1) Imports
2) Load dataset
3) Prepare input X and target Y
4) Train/test split
5) Create and train the linear model
6) Predict on test set
7) Plots
8) Evaluation metrics
9) Predict new samples

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: V.Lakshita Rai
RegisterNumber:  212225220054
*/
```
```
import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error, mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
df = pd.read_csv('/content/exp_2_dataset_student_scores.csv')   # CSV should have two columns, e.g. "Hours","Scores"
print("First 5 rows:\n", df.head(), "\n")
print("Last 5 rows:\n", df.tail(), "\n")

X = df.iloc[:, :-1].values   # all rows, all columns except last -> shape (n_samples, 1)
Y = df.iloc[:, -1].values    # all rows, last column -> shape (n_samples,)
print("X (features):", X.flatten())
print("Y (targets):", Y)

X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=1/3, random_state=0)
print("\nTraining samples:", len(X_train), " Testing samples:", len(X_test))

Y_pred = regressor.predict(X_test)
print("\nPredicted values:", np.round(Y_pred, 2))
print("Actual values   :", Y_test)

plt.figure(figsize=(6,4))
plt.scatter(X_train, Y_train, color="orange", label="Training data")
plt.plot(X_train, regressor.predict(X_train), color="red", label="Fitted line")
plt.title("Hours vs Scores (Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()

order = np.argsort(X_test.flatten())
X_test_sorted = X_test.flatten()[order]
Y_test_sorted = Y_test[order]
Y_pred_sorted = Y_pred[order]
plt.figure(figsize=(6,4))
plt.scatter(X_test, Y_test, color="blue", label="Test data")
plt.plot(X_test_sorted, Y_pred_sorted, color="green", label="Predictions")
plt.title("Hours vs Scores (Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()
```


## Output:
<img width="308" height="288" alt="684408527-496875ea-c95f-4ae2-ad11-0eef8f718780" src="https://github.com/user-attachments/assets/e39bf10b-059a-4f4a-a55c-50939e8e0036" />

<img width="752" height="83" alt="684408597-6396d139-8812-4be0-82e7-f0ebb4d959b9" src="https://github.com/user-attachments/assets/3ab3be6b-95ad-480a-b134-f01ef3069db4" />

<img width="311" height="72" alt="684408755-3c3b4c99-f874-4335-893f-f17dd375c820" src="https://github.com/user-attachments/assets/389c14fe-87f8-4f5f-9635-aae1bd813f80" />

<img width="665" height="62" alt="684408895-71b1a3f2-2e5f-4ccf-9d60-6b3b13691447" src="https://github.com/user-attachments/assets/15b4f292-5800-49dc-aeec-c51ee16da309" />

<img width="530" height="400" alt="684408977-debd3490-cb2f-49fe-847e-aeeaf39c7e8e" src="https://github.com/user-attachments/assets/f1e78305-a58a-4f82-8176-1e6194580ccc" />


<img width="536" height="397" alt="684409061-6e0d705b-107e-4a50-a9dc-37a026f9154d" src="https://github.com/user-attachments/assets/49078840-73e6-4c59-9106-4d2480cba75e" />








## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
