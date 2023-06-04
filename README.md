# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: M.Sanjay
RegisterNumber: 212222240090
*/

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
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="blue",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="gold",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend
plt.title("Customers Segments")
```

## Output:
![image](https://github.com/Sanjay22006832/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119830477/452c32f9-1b22-4367-9732-1721687a1cd1)

![image](https://github.com/Sanjay22006832/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119830477/d03e9713-3875-4b43-838b-e83c3aa5eac2)

![image](https://github.com/Sanjay22006832/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119830477/907df496-deea-4353-8122-8a1f602b1265)

![image](https://github.com/Sanjay22006832/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119830477/26fa2312-d602-49a3-b13d-9ac592462206)

![image](https://github.com/Sanjay22006832/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119830477/b5669250-b564-45e1-a4f1-17837127e86e)

![image](https://github.com/Sanjay22006832/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119830477/99507801-e2dc-4a2f-adb7-7a5751586ca3)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
