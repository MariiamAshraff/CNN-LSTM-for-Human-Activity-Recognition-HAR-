# 📄 CNN-LSTM for Human Activity Recognition (HAR)

---

## 📚 Project Overview

This project presents a **deep learning solution** for Human Activity Recognition (HAR) using a **CNN-LSTM hybrid architecture** applied to smartphone sensor data.  

The model is designed to simulate sequential learning on a dataset that originally contains engineered features by restructuring the input into segments and applying both:  

- **Convolutional Neural Networks (CNN)** for feature extraction  
- **Long Short-Term Memory (LSTM)** for sequence modeling  

The implementation reflects concepts from **Sequential Data Modeling** and extends them with practical improvements.

---

## 🎯 Objectives

- Build a hybrid CNN-LSTM model for activity classification  
- Transform static feature data into a pseudo-sequential format  
- Learn both:  
  - Local signal patterns (CNN)  
  - Sequential dependencies (LSTM)  
- Achieve high classification accuracy  
- Analyze model performance using evaluation metrics  

---

## 📊 Dataset

| Property        | Value |
|-----------------|-------|
| Dataset         | [UCI HAR Dataset](https://www.kaggle.com/datasets/uciml/human-activity-recognition-with-smartphones) |
| Total Samples   | 10,299 |
| Training Samples| 7,352 |
| Test Samples    | 2,947 |
| Features        | 561 |
| Classes         | 6 |

---

## 🏗️ Model Architecture

Input Data (Segmented Structure)
↓
TimeDistributed CNN Layers
↓
Feature Flattening (per segment)
↓
Bidirectional LSTM
↓
Dense Layers
↓
Softmax Output (6 Classes)


---

## ⚙️ Data Preprocessing

1. **Feature / Label Separation**  
   - Features used as input  
   - Labels represent activities  

2. **Label Encoding**  
   - Convert activity names → numeric labels  

3. **One-Hot Encoding**  
   - Convert labels into binary vectors  
   - Required for multi-class classification  

4. **Normalization**  
   - StandardScaler applied  
   - Ensures stable and faster training  

5. **Segmentation (Key Step)**  
   - Features reshaped into segments: 561 → 7 segments × 80 values  
   - **Purpose:**  
     - Simulate time dependency  
     - Enable LSTM learning  

---

## 🔍 Model Behavior

The model learns in two stages:  

**Stage 1: CNN**  
- Detects patterns inside segments  
- Reduces noise  

**Stage 2: LSTM**  
- Understands sequence of patterns  
- Captures temporal relationships  

---

## 🏋️ Model Training

| Configuration | Value |
|---------------|-------|
| Optimizer     | Adam |
| Loss Function | Categorical Crossentropy |
| Batch Size    | 64 |
| Epochs        | Up to 50 |
| EarlyStopping | Monitors validation loss and stops training when performance stops improving |

---

## 📈 Results

| Metric            | Value |
|------------------|-------|
| Training Accuracy | 90%+ |
| Test Accuracy     | 92.74% |

