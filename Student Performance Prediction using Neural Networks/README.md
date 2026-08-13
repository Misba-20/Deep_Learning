# Topic: Student Performance Prediction using Neural Networks

# Student Performance Prediction with MLP Classifier

## Overview
This project implements a Multi-Layer Perceptron (MLP) neural network to predict student performance based on various academic and behavioral factors. The model analyzes student data including study habits, attendance, previous grades, and extracurricular participation to predict whether a student will pass or fail.

## Project Structure
```
week1-dl.ipynb
├── Data Loading
│   └── student_performance.csv
├── Data Preprocessing
│   ├── Label Encoding for categorical variables
│   ├── Feature scaling with StandardScaler
│   └── Train-test split (80/20)
├── Model Architecture
│   └── MLPClassifier with 1 hidden layer (10 neurons)
├── Model Training
│   ├── Activation: ReLU
│   ├── Learning Rate: 0.01
│   ├── Max Iterations: 500
│   └── Random State: 42
├── Model Evaluation
│   ├── Accuracy Score
│   ├── F1 Score
│   ├── Confusion Matrix
│   └── Classification Report
└── Activation Functions Demo
    ├── Sigmoid Function
    ├── ReLU Function
    ├── Linear Transformation (Z = WX + b)
    └── Learning Rate Demonstration
```

## Features
- **Binary Classification**: Predicts whether a student will pass (1) or fail (0)
- **Comprehensive Student Data**: Analyzes 6 features including:
  - Study Hours per Week
  - Attendance Rate
  - Previous Grades
  - Extracurricular Participation
  - Parent Education Level
- **Data Preprocessing**: Handles categorical variables and feature scaling
- **Performance Metrics**: Provides multiple evaluation metrics for model assessment
- **Educational Components**: Includes implementation of key deep learning concepts

## Dataset Description
The dataset contains 100 student records with the following features:
- **Student ID**: Unique identifier
- **Study Hours per Week**: Hours spent studying
- **Attendance Rate**: Percentage of classes attended
- **Previous Grades**: Previous academic performance score
- **Participation in Extracurricular Activities**: Yes/No
- **Parent Education Level**: Undergraduate/Post Graduate
- **Passed**: Target variable (Yes/No)

## Requirements
```
numpy
pandas
scikit-learn
```

## Installation
```bash
pip install numpy pandas scikit-learn
```

## Usage

### Running the Notebook
1. Ensure `student_performance.csv` is in the same directory
2. Run all cells in the Jupyter notebook sequentially
3. The model will:
   - Load and preprocess the data
   - Train the neural network
   - Display evaluation metrics

### Making Predictions
```python
# The model is already trained and can be used for predictions
predictions = model.predict(X_test)
```

## Model Architecture
```
MLPClassifier Configuration:
- Hidden Layer: 1 layer with 10 neurons
- Activation Function: ReLU
- Solver: Adam optimizer (default)
- Learning Rate: 0.01
- Maximum Iterations: 500
- Random State: 42
```

## Performance Metrics
The model achieves perfect classification on the test set:
- **Accuracy**: 1.0 (100%)
- **F1 Score**: 1.0 (Weighted)
- **Confusion Matrix**:
  ```
  [[ 3  0]
   [ 0 17]]
  ```

### Classification Report
```
              precision    recall  f1-score   support
           0       1.00      1.00      1.00         3
           1       1.00      1.00      1.00        17
    accuracy                           1.00        20
   macro avg       1.00      1.00      1.00        20
weighted avg       1.00      1.00      1.00        20
```

## Implementation Details

### Data Preprocessing
1. **Label Encoding**: Converts categorical variables to numerical values
2. **Feature Scaling**: Uses StandardScaler for normalization
3. **Train-Test Split**: 80% training, 20% testing with random_state=42

### Activation Functions Implemented
1. **Sigmoid Function**:
   ```python
   def sigmoid(z):
       return 1/(1+np.exp(-z))
   ```

2. **ReLU Function**:
   ```python
   def relu(z):
       return np.maximum(0, z)
   ```

### Linear Transformation
Demonstrates the fundamental neural network operation:
```python
Z = WX + b
# Example: W = [0.5, 0.2], X = [10, 20], b = 1
# Z = 0.5*10 + 0.2*20 + 1 = 10.0
```

## Key Concepts Covered
1. **Neural Network Fundamentals**: MLP architecture and training
2. **Activation Functions**: Sigmoid and ReLU implementations
3. **Gradient Descent**: Understanding learning rates
4. **Feature Engineering**: Label encoding and scaling
5. **Model Evaluation**: Multiple performance metrics

## Applications
- Educational data mining
- Student performance prediction
- Early warning systems for at-risk students
- Academic intervention planning

## Future Improvements
- Add more hidden layers
- Implement cross-validation
- Explore different activation functions
- Add feature importance analysis
- Create visualization of neural network architecture
- Deploy as a web application

