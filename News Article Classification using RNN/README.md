# Topic: News Article Classification using Recurrent Neural Networks (RNN)

# News Category Classifier with RNN

## Overview
This project implements a Recurrent Neural Network (RNN) for classifying news articles into four categories: World, Sports, Business, and Science/Technology. The model processes news headlines and descriptions to predict the appropriate category.

## Project Structure
```
rnn.ipynb
├── Data Loading
│   └── test.csv
├── Text Preprocessing
│   ├── Clean text (lowercase, remove special characters)
│   └── Tokenization & Padding
├── Model Prediction
│   └── RNN inference
└── Output Display
    └── Show predictions vs actual labels
```

## Features
- **Text Preprocessing**: Cleans input text by converting to lowercase and removing non-alphabetic characters
- **Sequence Processing**: Uses tokenization and padding to prepare text for RNN input
- **Multi-class Classification**: Predicts one of four news categories
- **User-friendly Output**: Displays both actual and predicted categories for comparison

## Requirements
```
numpy
pandas
tensorflow
re (built-in)
```

## Installation
```bash
pip install numpy pandas tensorflow
```

## Usage
1. Ensure `test.csv` is in the same directory as the notebook
2. Run all cells in the Jupyter notebook
3. The notebook will:
   - Load the test data
   - Preprocess a sample news article
   - Use the trained RNN model for prediction
   - Display results comparing actual vs predicted categories

## How It Works
1. **Data Loading**: Reads test data from CSV file containing article headlines and descriptions
2. **Text Preprocessing**: 
   - Combines title and description
   - Cleans text using regex
   - Converts to sequences using tokenizer
   - Pads sequences to uniform length
3. **Prediction**: Uses pre-trained RNN model to classify articles
4. **Results**: Displays category predictions alongside actual labels

## Categories
The model classifies articles into:
- **1**: World News
- **2**: Sports
- **3**: Business
- **4**: Science/Technology

## Example Output
```
============================================================
INPUT TEXT:

Fears for T N pension after talks Unions representing workers at Turner Newall say they are 'disappointed' after talks with stricken parent firm Federal Mogul.

Actual Class Index : 3
Actual Category    : Business

Predicted Class Index : 4
Predicted Category    : Science/Technology
============================================================
```

## Notes
- The notebook demonstrates inference on a single sample (row index 0)
- Modify the `row` variable to test different articles from the dataset
- The model expects `tokenizer`, `max_length`, and `model` objects to be predefined

