# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments

## Program:

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: SURUTHI S

RegisterNumber: 212224220114
```

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```
## Output:
### 1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/1a2317c2-8065-43ae-911a-ab2ec8572ee6)
### 2.DATA.INF0():
![image](https://github.com/user-attachments/assets/0632af69-4376-4916-97fc-672e4aa7fd97)
### 3.DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/5b1ad30c-6426-410b-9883-25b16c2aad87)
### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/6aac2268-2e22-4dce-b3a0-6698e754299b)
### 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/bdfa153d-721d-46c9-aadd-3b429c8219a1)
### 6.Y_PRED ARRAY:
![image](https://github.com/user-attachments/assets/6e4eb72e-bf64-4915-92c8-08532d2f60f2)
### 7.CUSTOMER SEGMENT:
![image](https://github.com/user-attachments/assets/a4cf8f54-7f8b-4b74-a73f-f0a41099537d)
## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
