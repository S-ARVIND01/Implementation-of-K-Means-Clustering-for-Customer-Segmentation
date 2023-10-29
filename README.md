# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
Program to implement the K Means Clustering for Customer Segmentation.

Developed by: ARVIND S

RegisterNumber:  212222240012
```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### data.head():
![Screenshot 2023-10-29 180321](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/ae357444-6286-4afc-9732-02925d9b0d3d)

### data.info():
![Screenshot 2023-10-29 181053](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/7d5a838e-7c72-416e-b511-95d87da4401e)

### Null Values:
![Screenshot 2023-10-29 180342](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/c850ad20-dcb2-4a90-9573-96b18ae5abc5)

### Elbow Graph:
![Screenshot 2023-10-29 180449](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/90434d86-50fc-4c83-b618-e1be1025062c)

### Cluster Formation:
![Screenshot 2023-10-29 180640](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/d284c7ce-bca7-402b-ac71-39256e5eeb2b)

### Predicted Value:
![Screenshot 2023-10-29 180708](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/8ed2fe10-fd02-4978-9270-56af68373502)

### Customer Segment:
![Screenshot 2023-10-29 180731](https://github.com/S-ARVIND01/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707337/16400ae1-b2dc-41f8-982d-55660c87a5a1)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
