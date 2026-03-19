
📄 CNN-LSTM for Human Activity Recognition (HAR)
________________________________________
📚 Project Overview :

This project presents a deep learning solution for Human Activity Recognition (HAR) using a CNN-LSTM hybrid architecture applied to smartphone sensor data.
The model is designed to simulate sequential learning on a dataset that originally contains engineered features, by restructuring the input into segments and applying both:

•	Convolutional Neural Networks (CNN) for feature extraction
•	Long Short-Term Memory (LSTM) for sequence modeling

The implementation reflects concepts from Sequential Data Modeling and extends them with practical improvements.

________________________________________
🎯 Objectives :

•	Build a hybrid CNN-LSTM model for activity classification
•	Transform static feature data into a pseudo-sequential format

•	Learn both:
o	Local signal patterns (CNN)
o	Sequential dependencies (LSTM)

•	Achieve high classification accuracy .
•	Analyze model performance using evaluation metrics .
________________________________________
📊 Dataset :

Property	       value
Datasets	       UCI HAR Dataset
Samples        	10,299
Train	          7,352
Test          	2,947
Features      	561
Classes         	6

________________________________________
🏗️ Model Architecture :

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

________________________________________
Data Preprocessing

1. Feature / Label Separation :
•	Features used as input
•	Labels represent activities

2. Label Encoding :
•	Convert activity names → numeric labels

3. One-Hot Encoding :
•	Convert labels into binary vectors
•	Required for multi-class classification

4. Normalization:
•	StandardScaler applied
•	Ensures stable and faster training

5. Segmentation (Key Step) :
Features are reshaped into segments 
561 → (7 segments × 80 values)

Purpose
•	Simulate time dependency
•	Enable LSTM learning


________________________________________

 Model Behavior
The model learns in two stages:

Stage 1: CNN
•	Detects patterns inside segments
•	Reduces noise

Stage 2: LSTM
•	Understands sequence of patterns
•	Captures temporal relationships
________________________________________
Model Training

Configuration:
•	Optimizer: Adam
•	Loss: Categorical Crossentropy
•	Batch Size: 64
•	Epochs: up to 50

EarlyStopping :
•	Monitor validation loss
•	Stop training when performance stops improving
________________________________________
Results
Metric	              Value
Training Accuracy   	90%+
Test Accuracy	       92.74 %


