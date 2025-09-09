# Neural Networks for Regression and Classification

## What is a Neural Network?
A **Neural Network (NN)** is a machine learning model inspired by the human brain.  
It consists of layers of interconnected nodes (**neurons**) that process inputs, apply weights, and pass information forward through activation functions.

---

## Neural Network for Regression
- **Goal**: Predict continuous values (e.g., house prices, stock values, temperature).  
- **How it works**:
  - Inputs are passed through hidden layers with activation functions.  
  - The final layer usually has **one neuron** with a **linear activation** (no non-linearity).  
  - The network minimizes a **loss function** like Mean Squared Error (MSE).  
- **Example**: Predicting the future price of a product.

---

## Neural Network for Classification
- **Goal**: Assign input data into categories (e.g., spam vs. not spam, dog vs. cat).  
- **How it works**:
  - Inputs are transformed through hidden layers.  
  - The final layer has **one or more neurons** with a **non-linear activation** (e.g., Sigmoid for binary, Softmax for multi-class).  
  - The network minimizes a **loss function** like Cross-Entropy.  
- **Example**: Recognizing digits (0–9) from images.

---

## Key Differences
| Aspect              | Regression                          | Classification                       |
|---------------------|-------------------------------------|--------------------------------------|
| Output              | Continuous value (real numbers)     | Discrete class (labels)              |
| Final Activation    | Linear (identity)                  | Sigmoid (binary), Softmax (multi-class) |
| Loss Function       | Mean Squared Error (MSE)           | Cross-Entropy Loss                   |
| Example Use Case    | Predict house prices               | Classify images of animals            |

---

## Applications
- **Regression**: Weather forecasting, financial predictions, energy demand estimation.  
- **Classification**: Image recognition, spam detection, medical diagnosis.  