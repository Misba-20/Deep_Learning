# Topic: MNIST Handwritten Digit Recognition using Feedforward Neural Network (FNN)

 MNIST Digit Classifier with Feedforward Neural Network

## Overview
This project implements a Feedforward Neural Network (FNN) using TensorFlow/Keras to classify handwritten digits from the MNIST dataset. The model achieves high accuracy by learning to recognize patterns in 28x28 pixel grayscale images of digits (0-9).

## Project Structure
```
FNN-MNIST.ipynb
├── Data Loading
│   └── MNIST dataset (Keras built-in)
├── Data Exploration
│   ├── Dataset shape visualization
│   ├── Sample image display
│   └── Label distribution
├── Data Preprocessing
│   ├── Normalization (pixel values / 255.0)
│   ├── Reshaping for FNN input
│   └── One-Hot Encoding (categorical labels)
├── Model Architecture
│   ├── Flatten Layer (784 neurons)
│   ├── Dense Layer 1 (128 neurons, ReLU)
│   ├── Dense Layer 2 (64 neurons, ReLU)
│   └── Output Layer (10 neurons, Softmax)
├── Model Training
│   ├── Optimizer: Adam
│   ├── Loss: Categorical Crossentropy
│   ├── Epochs: 5
│   └── Batch Size: 32
├── Model Evaluation
│   ├── Test Accuracy
│   ├── Sample Predictions
│   ├── Correct Predictions Visualization
│   └── Incorrect Predictions Visualization
└── Individual Prediction Demo
    └── Single image prediction with visualization
```

## Features
- **High Accuracy**: Achieves ~97-98% accuracy on test data
- **Fast Training**: Only 5 epochs with 60,000 training samples
- **Simple Architecture**: Straightforward FNN design
- **Comprehensive Visualization**: 
  - Sample digit grid
  - Correct predictions
  - Misclassified examples
  - Individual predictions with true/predicted labels

## Dataset
The MNIST (Modified National Institute of Standards and Technology) dataset contains:
- **Training Set**: 60,000 images
- **Test Set**: 10,000 images
- **Image Size**: 28x28 pixels (784 features)
- **Classes**: 10 digits (0-9)
- **Format**: Grayscale images

## Requirements
```
tensorflow
numpy
matplotlib
scikit-learn
pandas
```

## Installation
```bash
pip install tensorflow numpy matplotlib scikit-learn pandas
```

## Usage

### Running the Notebook
1. Execute all cells in the Jupyter notebook sequentially
2. The model will automatically download the MNIST dataset
3. Training will complete in approximately 30-60 seconds
4. Results and visualizations will be displayed

### Model Architecture
```
Model: "sequential_5"
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━┓
┃ Layer (type)                         ┃ Output Shape                ┃         Param # ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━┩
│ flatten_5 (Flatten)                   │ (None, 784)                 │               0 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ dense_10 (Dense)                     │ (None, 128)                 │         100,480 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ dense_11 (Dense)                     │ (None, 64)                  │           8,256 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ dense_12 (Dense)                     │ (None, 10)                  │             650 │
└──────────────────────────────────────┴─────────────────────────────┴─────────────────┘
Total params: 109,386 (427.29 KB)
Trainable params: 109,386 (427.29 KB)
Non-trainable params: 0 (0.00 B)
```

## Training Results

### Training Progress
```
Epoch 1/5: accuracy: 0.9285 - loss: 0.2408 - val_accuracy: 0.9607 - val_loss: 0.1282
Epoch 2/5: accuracy: 0.9694 - loss: 0.1013 - val_accuracy: 0.9727 - val_loss: 0.0897
Epoch 3/5: accuracy: 0.9776 - loss: 0.0718 - val_accuracy: 0.9744 - val_loss: 0.0819
Epoch 4/5: accuracy: 0.9823 - loss: 0.0543 - val_accuracy: 0.9770 - val_loss: 0.0785
Epoch 5/5: accuracy: 0.9871 - loss: 0.0404 - val_accuracy: 0.9726 - val_loss: 0.0939
```

### Test Accuracy
```
Test Accuracy: 98.70%
```

## Visualization Examples

### Sample Digits Grid
Displays 10 random training examples with their correct labels.

### Correct Predictions
Shows 5 test samples with both true and predicted labels (all matching).

### Misclassified Examples
Displays up to 5 misclassified predictions with true vs predicted labels.

## Making Single Predictions
```python
# Predict a single image
prediction = model.predict(X_test)
index = 0  # Choose any index

true = np.argmax(y_test[index])
pred = np.argmax(prediction[index])

print(f"True: {true}")
print(f"Predicted: {pred}")
```

## Key Concepts Covered
1. **Feedforward Neural Networks**: Basic architecture and training
2. **Data Preprocessing**: Normalization and one-hot encoding
3. **Activation Functions**: ReLU for hidden layers, Softmax for output
4. **Optimization**: Adam optimizer for efficient training
5. **Regularization**: Implicit through architecture design
6. **Model Evaluation**: Accuracy metrics and confusion analysis

## Applications
- Handwritten digit recognition
- Document digitization
- OCR (Optical Character Recognition)
- Educational tool for neural network learning

## Performance Optimization Tips
- Add dropout layers to prevent overfitting
- Increase epochs for better accuracy
- Experiment with different architectures
- Add batch normalization
- Use learning rate scheduling
