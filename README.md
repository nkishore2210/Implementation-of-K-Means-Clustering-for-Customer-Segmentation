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
Developed by: N.Kishore
RegisterNumber: 212222240049
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
![Screenshot 2023-06-04 153504](https://github.com/nkishore2210/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707090/568c23cd-61bf-43fc-a000-3eb7677bfc01)

![Screenshot 2023-06-04 153517](https://github.com/nkishore2210/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707090/ed89110a-6826-4a14-a2c1-e3f59b1d65cc)

![Screenshot 2023-06-04 153524](https://github.com/nkishore2210/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707090/2e47ad59-72a6-4d04-b558-908fa071404b)

![Screenshot 2023-06-04 153533](https://github.com/nkishore2210/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707090/f3ce7578-64b8-442b-a08a-c53688ce5196)

![Screenshot 2023-06-04 153546](https://github.com/nkishore2210/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707090/ab55eec2-9fd4-4afe-9d01-5119a496f56f)

![Screenshot 2023-06-04 153557](https://github.com/nkishore2210/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707090/80228b84-cae1-448c-9acf-d9c4c99b46c6)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
