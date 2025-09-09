# Recurrent Neural Network (RNN)

## What is RNN?
A **Recurrent Neural Network (RNN)** is a type of neural network designed for **sequential data** such as text, speech, or time series.  
Unlike traditional feedforward networks, RNNs have loops that allow information to persist, giving them a form of "memory."

---

## Key Concepts
- **Sequential Processing**: Inputs are processed one step at a time.  
- **Hidden State**: Stores past information and is updated at each step.  
- **Weight Sharing**: The same weights are applied across all time steps, enabling generalization for sequences of any length.  

---

## How It Works
At each time step \(t\):  
- Input: \(x_t\)  
- Hidden state: \(h_t\)  
- Output: \(y_t\)  

The hidden state update combines the **current input** and the **previous hidden state**, making RNNs suitable for tasks with temporal dependencies.

---

## Strengths
- Handles sequential/temporal data effectively.  
- Captures dependencies between elements in a sequence.  
- Useful for variable-length inputs.  

---

## Limitations
- Struggles with **long-term dependencies** due to vanishing or exploding gradients.  
- Training can be slow for very long sequences.  

---

## Variants
- **LSTM (Long Short-Term Memory)**: Adds gates to control information flow and capture long-term patterns.  
- **GRU (Gated Recurrent Unit)**: A simplified version of LSTM, more efficient while retaining performance.  

---

## Applications
- Natural Language Processing (e.g., text generation, translation, sentiment analysis).  
- Speech recognition.  
- Time series prediction (finance, weather, sensor data).  