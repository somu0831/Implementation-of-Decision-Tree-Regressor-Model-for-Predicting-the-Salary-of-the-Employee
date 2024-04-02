# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import pandas as pd and from sklearn.preprocessing import LabelEncoder
2.from sklearn.model_selection import train_test_split
3. from sklearn.tree import DecisionTreeRegressor
4. from sklearn import metrics 
5. at last by using metrics_mean_squared_error and metrics_r2_score we can get the results

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Panduru somu
RegisterNumber:  212223240111
*/
import pandas as pd
from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeRegressor
from sklearn import metrics 
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
le = LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
y=data["Salary"]
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
mse=metrics.mean_squared_error(y_test,y_pred)
print(float(mse))
r2=metrics.r2_score(y_test,y_pred)
print(r2)
dt.predict([[5,6]])
```

## Output:
![Screenshot 2024-04-02 093623](https://github.com/somu0831/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/162110820/b5c27c2c-81cd-46ad-a85c-c19166d55537)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
