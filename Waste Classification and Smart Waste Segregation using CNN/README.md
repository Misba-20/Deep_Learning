# Waste Classification using CNN

## Topic
**AI-Powered Waste Segregation System using Convolutional Neural Networks (CNN)**

## Overview
This project implements a Convolutional Neural Network (CNN) for automated waste classification and segregation. The model classifies waste items into six categories and provides environmentally-conscious disposal suggestions, making it a practical tool for smart waste management and recycling initiatives.

## Project Structure
```
Trashnet-cnn.ipynb
├── Data Loading & Preprocessing
│   ├── Dataset loading from directory
│   ├── Image augmentation (rotation, zoom, shear, flip)
│   └── Train/Validation split (80/20)
├── Model Architecture
│   ├── 3 Convolutional Layers with MaxPooling
│   ├── Flatten Layer
│   ├── Dense Layer with Dropout (0.5)
│   └── Output Layer (6 classes - Softmax)
├── Training
│   └── 15 epochs with Adam optimizer
├── Model Evaluation
│   └── Accuracy plot (Training vs Validation)
├── Inference
│   └── Single image prediction
└── Waste Segregation Logic
    ├── Category prediction
    ├── Bin assignment
    └── Environmental AI suggestions
```

## Features
- **Multi-class Classification**: Identifies 6 types of waste materials
- **Data Augmentation**: Improves model generalization with rotation, zoom, shear, and flip
- **Real-time Prediction**: Classifies single images with confidence scores
- **Smart Segregation**: Provides appropriate bin assignments for each waste type
- **Environmental Insights**: Offers eco-friendly disposal recommendations

## Dataset
The model is trained on a resized dataset (150x150 pixels) containing 6 classes:
- **Cardboard** (0)
- **Glass** (1)
- **Metal** (2)
- **Paper** (3)
- **Plastic** (4)
- **Trash** (5)

## Requirements
```
tensorflow
numpy
matplotlib
PIL (Pillow)
```

## Installation
```bash
pip install tensorflow numpy matplotlib pillow
```

## Usage

### Training the Model
1. Organize dataset in the following structure:
```
dataset-resized/
├── cardboard/
├── glass/
├── metal/
├── paper/
├── plastic/
└── trash/
```

2. Run the notebook cells sequentially
3. Model will train for 15 epochs with data augmentation
4. Training/validation accuracy will be displayed

### Making Predictions
```python
from tensorflow.keras.preprocessing import image
import numpy as np

# Load and preprocess image
img = image.load_img(img_path, target_size=(150,150))
img_array = image.img_to_array(img) / 255.0
img_array = np.expand_dims(img_array, axis=0)

# Predict
prediction = model.predict(img_array)
classes = ['cardboard', 'glass', 'metal', 'paper', 'plastic', 'trash']
predicted_class = classes[np.argmax(prediction)]
```

## Model Architecture
```
Layer (type)                 Output Shape      Param #
================================================================
Conv2D (32 filters, 3x3)    (None, 148, 148, 32)   896
MaxPooling2D (2x2)          (None, 74, 74, 32)     0
Conv2D (64 filters, 3x3)    (None, 72, 72, 64)     18,496
MaxPooling2D (2x2)          (None, 36, 36, 64)     0
Conv2D (128 filters, 3x3)   (None, 34, 34, 128)    73,856
MaxPooling2D (2x2)          (None, 17, 17, 128)    0
Flatten                     (None, 36992)           0
Dense (128 neurons)         (None, 128)            4,735,104
Dropout (0.5)               (None, 128)            0
Dense (6 neurons, Softmax)  (None, 6)              774
================================================================
Total params: 4,829,126 (18.42 MB)
Trainable params: 4,829,126 (18.42 MB)
```

## Results
- **Training Accuracy**: ~62.5%
- **Validation Accuracy**: ~50.7%

## Waste Segregation Logic
The system provides bin assignments based on the predicted category:

| Predicted Category | Segregation Bin |
|---|---|
| Plastic | Plastic Recycling Bin |
| Paper | Paper Recycling Bin |
| Glass | Glass Recycling Bin |
| Metal | Metal Recycling Bin |
| Cardboard | Cardboard Recycling Bin |
| Trash | General Waste Bin |

## Environmental AI Features
- Recommends recycling for all categories except "trash"
- Provides eco-friendly disposal suggestions
- Promotes sustainable waste management practices

## Applications
- Smart waste management systems
- Recycling facility automation
- Educational tools for waste segregation
- Environmental awareness applications
- IoT-enabled smart bins

