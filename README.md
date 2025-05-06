# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model

4.Plot the Cluster graph

## Program:

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SURUTHI S

RegisterNumber: 212224220114
```
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")
```

## Output:
![image](https://github.com/user-attachments/assets/1c6b3568-1aff-468a-9033-69817402e076)
![image](https://github.com/user-attachments/assets/5ba254f7-bc13-4a8b-80bf-a24f3f12037e)
![image](https://github.com/user-attachments/assets/336800df-3eb7-4306-919c-d99d0b41d249)
![image](https://github.com/user-attachments/assets/48134f2f-6c3a-48a1-a728-d4368b5e32ce)
![image](https://github.com/user-attachments/assets/8b75d7b6-ead0-43f2-815d-63f1913f6deb)
![image](https://github.com/user-attachments/assets/746e385c-7ffc-4d87-b275-d4b529431273)
![image](https://github.com/user-attachments/assets/0f163aaa-eb70-4f0f-b35b-8a1089408e59)


## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
