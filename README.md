# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries from python.
2. Upload the dataset and check for any null values using .isnull() function.
3. Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply to the model from the dataset.
5. Predict the values of the arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model from the dataset.
7. Predict the values of array
8. Apply it to the new unknown values.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Ragul D
RegisterNumber:  212225230221
*/

import pandas as pd
data=pd.read_csv(r"C:\Users\acer\Downloads\Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
  ```
<img width="682" height="420" alt="Screenshot 2026-05-20 084429" src="https://github.com/user-attachments/assets/1158d567-d798-4623-99f3-b3206059c3cb" />

<img width="448" height="371" alt="Screenshot 2026-05-20 084437" src="https://github.com/user-attachments/assets/72542dd2-01bc-4ae4-bd5e-51fc6069b9fc" />

```
x=data[["Position","Level"]]
x.head()
```

<img width="291" height="366" alt="Screenshot 2026-05-20 084655" src="https://github.com/user-attachments/assets/c1fb1b13-6d43-47f3-a430-759a7c6c23f1" />

```
y=data[["Salary"]]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse
```
<img width="242" height="78" alt="Screenshot 2026-05-20 084751" src="https://github.com/user-attachments/assets/76f07d61-cc3c-4d1f-b660-62dc87a7bc78" />

```
r2=metrics.r2_score(y_test,y_pred)
r2
```

<img width="497" height="87" alt="Screenshot 2026-05-20 084757" src="https://github.com/user-attachments/assets/83f02130-339f-4b16-b45a-69d7f831e90c" />




## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
