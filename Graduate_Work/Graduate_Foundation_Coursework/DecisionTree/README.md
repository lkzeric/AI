# Decision Tree

## What is a Decision Tree?
A **Decision Tree** is a supervised machine learning algorithm used for both **classification** and **regression** tasks.  
It works by recursively splitting the dataset into subsets based on feature values, forming a tree-like structure.

---

## Key Concepts
- **Nodes**: Represent questions or decisions based on a feature.  
- **Branches**: Outcomes of the decision (e.g., yes/no).  
- **Leaves**: Final predictions (class labels for classification or numeric values for regression).  
- **Root Node**: The first split that partitions the dataset.

---

## How It Works
1. Select the **best feature** to split the data (using criteria like Gini Index, Entropy, or Variance Reduction).  
2. Partition the dataset into subsets.  
3. Repeat the process recursively for each subset until:
   - A maximum depth is reached,  
   - A stopping condition is met, or  
   - The nodes are pure (all samples belong to one class).  

---

## Strengths
- Easy to interpret and visualize.  
- Handles both numerical and categorical data.  
- Non-linear relationships can be captured.  

---

## Limitations
- Prone to **overfitting** if the tree grows too deep.  
- Small changes in data can lead to very different trees.  
- May require techniques like **pruning** or ensemble methods (Random Forest, Gradient Boosting) to improve performance.  

---

## Applications
- Customer segmentation.  
- Credit risk analysis.  
- Medical diagnosis.  
- Predicting numerical outcomes (e.g., housing prices).  