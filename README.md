# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn
### NAME: KEERTHANA V
### REG NO: 212223220045
## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import Libraries and Load Dataset.
2. Preprocess the Data.
3. Split the Dataset.
4. Train the Decision Tree Classifier.
5. Make Predictions and Evaluate the Model. 

## Program:
```
import pandas as pd
data=pd.read_csv("Employee.csv")
data
```
## Output:
![Screenshot 2025-04-21 153359](https://github.com/user-attachments/assets/153a81d0-7bc6-472f-9ac2-7cb63bdf6351)

```
data["left"].value_counts()
```
## Output:
![Screenshot 2025-04-21 153623](https://github.com/user-attachments/assets/c5522481-6182-4961-b691-53d850ec5d2e)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data.head()
```
## Output:
![Screenshot 2025-04-21 154537](https://github.com/user-attachments/assets/41970409-4944-4601-bed7-a2a067694f3c)
```
data["salary"]=le.fit_transform(data["salary"])
data
```
## Output:
![image](https://github.com/user-attachments/assets/3e9469bb-58c6-4873-9309-b9921a931511)

![image](https://github.com/user-attachments/assets/2bfbc2e2-8aab-4b66-9dba-bb624467783d)

```
x=data[["satisfaction_level","last_evaluation","number_project","time_spend_company"]]
x.head()
```
## Output:
![Screenshot 2025-04-21 155059](https://github.com/user-attachments/assets/76f0ca50-d6d7-49ad-a89c-1b636d5b9287)

```
y=data["left"]
```
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
```
```
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
```
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
![Screenshot 2025-04-21 205855](https://github.com/user-attachments/assets/83f2d35e-765e-4693-a72a-e55f925510f0)
```
dt.predict([[0.5,0.8,9,2]])
```
## Output:
![Screenshot 2025-04-21 210112](https://github.com/user-attachments/assets/e0e1ef4f-69a1-4f0d-abc7-6854e26eab0c)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
