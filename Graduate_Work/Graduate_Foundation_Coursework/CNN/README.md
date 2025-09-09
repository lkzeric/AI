# Convolutional Neural Network (CNN)

## What is CNN?
A **Convolutional Neural Network (CNN)** is a deep learning model especially effective for **image and pattern recognition**.  
It mimics how the human visual cortex processes visual information, making it the backbone of modern computer vision.

---

## Key Components
1. **Convolution Layer**  
   - Applies filters (kernels) that slide over the input (e.g., image).  
   - Detects local features like edges, corners, and textures.  
   - Each filter produces a **feature map**.

2. **Activation Function (ReLU)**  
   - Introduces non-linearity.  
   - Keeps only positive values.  

3. **Pooling Layer (Downsampling)**  
   - Reduces the size of feature maps while keeping important information.  
   - Example: **Max Pooling** selects the largest value in each region.

4. **Fully Connected Layer**  
   - Flattens feature maps into a vector.  
   - Combines extracted features to make final predictions (e.g., class probabilities).

---

## Strengths
- Captures spatial patterns in images.  
- Reduces parameters compared to fully connected networks.  
- Highly effective in computer vision tasks.

---

## Limitations
- Requires large amounts of labeled data.  
- Computationally intensive (training can be slow).  
- Not naturally suited for sequential data like text (RNN/Transformers work better there).

---

## Applications
- Image classification (e.g., recognizing cats vs. dogs).  
- Object detection (e.g., self-driving cars).  
- Face recognition.  
- Medical imaging (e.g., tumor detection).  
- Video analysis and action recognition.  

---