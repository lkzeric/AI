# Support Vector Machine (SVM)

## What is SVM?
Support Vector Machine (SVM) is a supervised machine learning algorithm used for **classification** and **regression** tasks.  
It works by finding the **best separating boundary (hyperplane)** that divides data points into classes.

---

## Key Ideas
- **Hyperplane**: A line (in 2D), a plane (in 3D), or higher-dimensional surface that separates data classes.
- **Support Vectors**: The data points that are closest to the hyperplane. These points define the boundary.
- **Margin**: The distance between the hyperplane and the nearest support vectors.  
  SVM tries to maximize this margin → better generalization.

---

## How It Works (Classification)
1. Input data points from two classes.  
2. SVM finds the hyperplane that separates the classes with the **largest margin**.  
3. For data that is not linearly separable, SVM uses **kernel functions** (e.g., polynomial, RBF) to map data into higher dimensions.

---
## How SVM Works for Regression (SVR)
Unlike classification, **Support Vector Regression (SVR)** tries to fit a function that approximates the data **within a certain error tolerance**.

- We define an **epsilon-insensitive tube** around the regression function.
- Data points inside this tube are considered “well-predicted” and do not contribute to the loss.
- Only points outside the tube (violating the tolerance) contribute to the optimization.


## Advantages
- Works well for high-dimensional data.  
- Effective when the number of features is greater than the number of samples.  
- Uses only a subset of data (support vectors), making it efficient in memory.

---

## Limitations
- Can be slower on very large datasets.  
- Choosing the right kernel and parameters (C, gamma) is critical.  

---

## Applications
- Image recognition  
- Text classification  
- Bioinformatics (e.g., gene classification)  
- Handwriting digit recognition  
- Stock price prediction (SVR)  
- Demand forecasting (SVR)