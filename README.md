# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Kaviya D
RegisterNumber:  212223040089
*/
```
```

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

## data.head():

![Image-1](https://github.com/user-attachments/assets/4b362bcf-7668-4473-8941-e0bfdb7dcef3)


## data.info():

![Image-2](https://github.com/user-attachments/assets/3d532e87-6781-409c-92a1-5535f2fbda83)


## data.isnull().sum():
![Image-3](https://github.com/user-attachments/assets/f67cc320-a8aa-401e-84e9-a55cc469eb86)

## Elbow method:
![Image-4](https://github.com/user-attachments/assets/e5289115-e76c-42e0-86a9-78d2dfe3b011)


## km = KMeans(n_clusters = 5):
![Image-5](https://github.com/user-attachments/assets/b62b4cb8-6ddb-4333-a9e6-34207ee71429)

## KMeans(n_clusters = 5):
![Image-6](https://github.com/user-attachments/assets/d6ec9059-ba64-4dbb-8865-a3bf23b299cf)

## Prediction:
![Image-7](https://github.com/user-attachments/assets/be2b7fc4-a3e6-4a52-978d-622770ec4ff0)

## Customer Segment:
![Image-8](https://github.com/user-attachments/assets/941148e1-450d-463b-8cca-737c9fea7cff)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
