# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## EQUIPMENTS REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## ALGORITHM:
1. Load and Inspect Data: Detect file encoding using chardet, load the spam dataset (spam.csv), and inspect its structure using .head(), .tail(), and .info() methods.
2. Check for Missing Values: Use .isnull().sum() to identify any missing data in the dataset and ensure data completeness.
3. Define Features and Target: Extract feature (x, email messages) and target (y, labels like "spam" or "ham") columns from the dataset.
4. Split Dataset: Divide x and y into training and testing sets using train_test_split (80-20 split).
5. Transform Text Data: Use CountVectorizer to convert textual email data into numerical feature vectors for model compatibility.
6. Train SVM Classifier: Initialize and train an SVC model on the vectorized training data (x_train and y_train).
7. Evaluate Model Accuracy: Predict labels on the test set, then compute the accuracy score using metrics.accuracy_score to evaluate model performance.

## PROGRAM:
```
Program to implement the SVM For Spam Mail Detection..
Developed by: SRINIDHI SENTHIL
RegisterNumber: 212222230148

import chardet
file='/content/spam.csv'
with open(file,'rb') as rawdata:
  result = chardet.detect(rawdata.read(100000))
result
```
```
import pandas as pd
data=pd.read_csv('/content/spam.csv',encoding='Windows-1252')
```
### DATA.HEAD():

```
data.head()
```
### DATA.TAIL():
```
data.tail()
```
### DATA.INFO():
```
data.info()
```
### DATA.ISNULL().SUM():
```
data.isnull().sum()
```
### X_TEST.SHAPE:
```
x_test.shape
```
### X,Y DATA VALUES

```
x=data["v1"].values
y=data["v2"].values
```
### SKLEARN
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
```
### TRANSFORM 
```
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
```
### IMPORT 
```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```
### ACCURACY 
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/87d05b26-9111-4544-a830-b700bd9a5e3e)

### DATA.HEAD():

![image](https://github.com/user-attachments/assets/e2ba6705-663f-4947-8ff4-487543c5a8ff)

### DATA.TAIL():

![image](https://github.com/user-attachments/assets/010716b4-5d15-48cb-8a6c-b35b241dd530)


### DATA.INFO():

![image](https://github.com/user-attachments/assets/e54f0bc0-47f2-4b22-9deb-32098d8a93ad)

### DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/f35333ed-d112-472d-88bc-93145233f97b)
### X_TEST.SHAPE:
![image](https://github.com/user-attachments/assets/6f0518f6-170b-4d85-8b0a-96603de797fa)

### Y_PREDICTION VALUE:
![image](https://github.com/user-attachments/assets/0eb284b3-06a6-4db3-b2f2-36d4b327955d)

### ACCURACY: 
![image](https://github.com/user-attachments/assets/b2afb625-ee80-48c4-b672-a4c31d1bfbf4)



## RESULT:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
