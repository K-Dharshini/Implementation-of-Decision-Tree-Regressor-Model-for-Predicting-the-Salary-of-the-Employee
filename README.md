# EXP7 - Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## Aim:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1. Import the libraries and read the data frame using pandas.

2. Calculate the null values present in the dataset and apply label encoder.
   
3. Determine test and training data set and apply decison tree regression in dataset.
   
4. Calculate Mean squared error, and r2.

## Program:
~~~
/* 
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: DHARSHINI K
RegisterNumber:  212223230047
*/

import pandas as pd
data=pd.read_csv("Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
print(mse)

r2=metrics.r2_score(y_test,y_pred)
print(r2)

dt.predict([[5,6]])
~~~
## Output:
# DATASET
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/fad4ac6e-6233-4642-94d8-fdb9c24716a5)

# data.info()
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/1df11c88-3d24-407c-9bf4-f0997d2b2563)

# CHECKING IF NULL VALUES ARE PRESENT
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/47c64c54-2d21-46b3-903b-bdd7fa2d2652)

# DATASET AFTER ENCODING
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/d10c39ff-3074-4edc-b201-68ca609248b7)

# MSE
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/af30b04f-2ad5-42f4-af2f-96cc8de4828b)

# r2
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/5c85217b-0505-4345-98b0-e87b2f3c5976)

# dt.predict()
![image](https://github.com/K-Dharshini/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/139334830/d993baa4-b83e-4505-a779-c9fdc3f45cd9)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
