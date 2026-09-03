# 🌸 K-Means Cluster Analysis on Iris Dataset

A Machine Learning project demonstrating **K-Means Clustering** using the Iris dataset.

## 📌 Project Overview

This project performs **unsupervised machine learning** using the K-Means clustering algorithm.

The main goal is to group Iris flowers into different clusters based on their features without using predefined class labels.

### 🎯 Objectives

* Load the Iris dataset
* Explore the dataset
* Standardize the features
* Determine the appropriate number of clusters using the Elbow Method
* Apply K-Means clustering
* Calculate the Silhouette Score
* Visualize the clusters
* Display cluster centroids

---

## 🛠️ Technologies Used

* Python 🐍
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* K-Means Clustering

---

## 📊 Dataset

### Iris Dataset

The project uses the built-in **Iris dataset** provided by Scikit-learn.

The dataset contains four features:

* Sepal Length
* Sepal Width
* Petal Length
* Petal Width

The Iris dataset is loaded using:

```python
from sklearn.datasets import load_iris

iris = load_iris()
X = iris.data
```

The project then converts the data into a Pandas DataFrame.

---

## 🔄 Machine Learning Workflow

```text
Iris Dataset
     ↓
Data Loading
     ↓
Feature Extraction
     ↓
Standardization
     ↓
Elbow Method
     ↓
Select Number of Clusters
     ↓
K-Means Clustering
     ↓
Silhouette Score
     ↓
Cluster Visualization
     ↓
Cluster Centers
```

---

## ⚙️ Data Standardization

Before applying K-Means, the features are standardized using `StandardScaler`.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

This ensures that the features are placed on a comparable scale before clustering.

---

## 📐 Elbow Method

The **Elbow Method** is used to analyze different numbers of clusters.

The project tests cluster values from **1 to 10** and calculates WCSS (Within-Cluster Sum of Squares).

```python
for i in range(1, 11):
    kmeans = KMeans(
        n_clusters=i,
        random_state=42,
        n_init=10
    )
    kmeans.fit(X_scaled)
    wcss.append(kmeans.inertia_)
```

The WCSS values are plotted to create the Elbow Method graph.

---

## 🤖 K-Means Clustering

For the Iris dataset, the project applies K-Means using **3 clusters**.

```python
kmeans = KMeans(
    n_clusters=3,
    random_state=42,
    n_init=10
)

clusters = kmeans.fit_predict(X_scaled)
```

The resulting cluster labels are added to the DataFrame.

---

## 📈 Silhouette Score

The project calculates the **Silhouette Score** to evaluate the quality of the clustering.

```python
from sklearn.metrics import silhouette_score

score = silhouette_score(X_scaled, clusters)

print("Silhouette Score:", score)
```

---

## 📊 Cluster Visualization

The project visualizes the clusters using two standardized features.

It also displays the **cluster centroids** on the graph.

```text
Cluster Visualization

       ✕  Centroid
      ● ● ●
    ● ● ●

             ✕
          ● ● ●
        ● ● ●

                    ✕
                 ● ● ●
```

---

## 🎯 Cluster Centers

The project calculates and prints the K-Means cluster centers from the scaled data.

```python
centroids = kmeans.cluster_centers_

print("Cluster Centers (Scaled Data):")
print(centroids)
```

---

## 📂 Project Structure

```text
KMeans-Cluster-Analysis/
│
├── kmeans_cluster_analysis.py
├── README.md
└── requirements.txt
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/KMeans-Cluster-Analysis.git
```

### 2. Open the project folder

```bash
cd KMeans-Cluster-Analysis
```

### 3. Install the required libraries

```bash
pip install -r requirements.txt
```

### 4. Run the Python program

```bash
python kmeans_cluster_analysis.py
```

---

## 📦 Requirements

Create a `requirements.txt` file containing:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
```

Then install:

```bash
pip install -r requirements.txt
```

---

## 🎓 Learning Outcomes

After completing this project, you will understand:

* Unsupervised Machine Learning
* K-Means Clustering
* Data Standardization
* Elbow Method
* WCSS
* Silhouette Score
* Cluster Visualization
* Cluster Centroids
* Scikit-learn clustering techniques

---

## 👨‍💻 Author

**Mahadev Prasad L**

🎓 Artificial Intelligence & Data Science
🏫 Maharaja Institute of Technology Thandavapura
📚 3rd Year – 5th Semester
🎓 VTU Student

---

## ⭐ Project

This project is created for **academic and learning purposes** to demonstrate K-Means clustering using Python and Scikit-learn.

If you find this project useful, please ⭐ **star the repository**.
