# README.md

# LSTM-Based Emotion Detection Using DAIR Dataset

## Project Overview

This project implements an **Emotion Detection System** using a **Long Short-Term Memory (LSTM)** deep learning model. The model analyzes textual input and predicts the underlying human emotion from the **DAIR Emotion Dataset**. It is designed to demonstrate Natural Language Processing (NLP) techniques for text classification using TensorFlow and Keras.

---

## Features

* Text preprocessing and tokenization
* Emotion classification using LSTM
* Predicts one of six emotions:

  * Sadness
  * Joy
  * Love
  * Anger
  * Fear
  * Surprise
* Displays prediction confidence score
* Classifies overall sentiment as Positive, Negative, or Neutral
* Supports prediction on custom user input

---

## Technologies Used

* Python 3.x
* TensorFlow / Keras
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* NLTK
* Google Colab / Jupyter Notebook

---

## Dataset

**Dataset Name:** DAIR Emotion Dataset

The dataset contains text samples labeled with six emotions.

| Label | Emotion  |
| ----- | -------- |
| 0     | Sadness  |
| 1     | Joy      |
| 2     | Love     |
| 3     | Anger    |
| 4     | Fear     |
| 5     | Surprise |

---

## Project Structure

```
LSTM-Emotion-Detection/
│
├── LSTM-DAIR DATASET.ipynb
├── train.csv
├── validation.csv
├── test.csv
├── README.md
└── requirements.txt
```

---

## Workflow

1. Load the DAIR Emotion Dataset
2. Preprocess text data
3. Tokenize and pad sequences
4. Build the LSTM model
5. Train the model
6. Evaluate model performance
7. Predict emotions for custom text
8. Display emotion, sentiment, and confidence score

---

## LSTM Model Architecture

* Embedding Layer
* LSTM Layer
* Dropout Layer
* Dense Layer (ReLU)
* Output Layer (Softmax)

---

## Installation

Install the required libraries:

```bash
pip install tensorflow pandas numpy matplotlib scikit-learn nltk
```

---

## Running the Project

Open the notebook:

```bash
jupyter notebook
```

or

```bash
google colab
```

Run all cells sequentially to:

* Load the dataset
* Train the model
* Evaluate accuracy
* Test with custom text input

---

## Example Prediction

**Input**

```
I am very happy today.
```

**Output**

```
Input Text        : I am very happy today.
Predicted Emotion : Joy
Sentiment         : Positive
Confidence Score  : 98.76%
```

---

## Performance

The trained LSTM model provides accurate emotion classification for the six emotion categories in the DAIR dataset. Performance depends on the training configuration, preprocessing steps, and dataset quality.

Evaluation metrics include:

* Training Accuracy
* Validation Accuracy
* Loss
* Prediction Confidence

---

## Applications

* Sentiment Analysis
* Social Media Monitoring
* Mental Health Support
* Customer Feedback Analysis
* Chatbots and Virtual Assistants
* Human–Computer Interaction

---

## Future Enhancements

* Deploy using Flask or Streamlit
* Add multilingual emotion detection
* Integrate attention mechanisms or Transformer models
* Support real-time emotion prediction
* Improve performance with larger datasets

---.
