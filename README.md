# TweetEmotionAI-Simple clear and-highlights AI aspect.
A deep learning project for detecting emotions in tweets. It uses tokenization, padding, and a **Bidirectional LSTM** model to classify tweets into emotions like **joy, sadness, anger, fear, surprise, and love**. The project includes training, evaluation, visualizations, and model export for deployment.

---

## Table of Contents

1. [Overview](#overview)  
2. [Features](#features)  
3. [Dataset](#dataset)  
4. [Model Architecture](#model-architecture)  
5. [Visualizations](#visualizations)  
6. [Results](#results)  
7. [Usage](#usage)  
8. [Author](#author)  

---

## Overview

TweetEmotionAI provides a complete workflow for **emotion detection in tweets**. Tweets are preprocessed, tokenized, and padded before being fed into a **Bidirectional LSTM network**. Class imbalance is handled via weighted training, and performance is evaluated using **F1 score, classification reports, and confusion matrices**. The trained model is saved for future deployment.

---

## Features

- Tokenization and padding for tweet preprocessing  
- Class imbalance handling with weighted training  
- Bidirectional LSTM neural network for contextual understanding  
- Performance tracking with F1 score and loss plots  
- Evaluation using classification report and confusion matrix  
- Save models in **Keras (.keras)** and **TensorFlow SavedModel** formats  

---

## Dataset

- **MTEB Emotion dataset** from Hugging Face  
- Train: 15,956 tweets | Validation: 1,988 tweets | Test: 1,986 tweets  
- Each sample contains:  
  - `text`: the tweet content  
  - `label`: numeric class  
  - `label_text`: human-readable emotion  

---

## Model Architecture

The model is a **Sequential Keras model** with:

| Layer Type                 | Parameters/Units | Description |
|-----------------------------|-----------------|-------------|
| Input Layer                 | (50,)           | Accepts padded tweet sequences |
| Embedding Layer             | 10,000 → 24     | Converts words into dense vectors |
| Bidirectional LSTM Layer 1  | 20 units        | Returns sequences for next LSTM layer |
| Bidirectional LSTM Layer 2  | 20 units        | Outputs final feature representation |
| Dense Output Layer           | 6 units, softmax| Predicts probabilities for 6 emotion classes |

Compiled with **categorical crossentropy loss**, **Adam optimizer**, and **macro F1 score** as the metric.

---

## Visualizations

- **Tweet Length Distribution** – before and after tokenization  
- **Training Curves** – F1 score and loss over epochs  
- **Confusion Matrix** – predicted vs true emotions  

These visualizations help monitor training, detect overfitting, and evaluate model performance.

---

## Results

The model achieves strong performance across multiple emotion classes. Evaluation includes:  

- **Classification report** with precision, recall, and F1 score  
- **Confusion matrix** showing correct and misclassified predictions  
- Models are saved for deployment in both **Keras** and **TensorFlow** formats

---

## Usage

1. Load the dataset and split into train/validation/test  
2. Tokenize and pad tweets to fixed length  
3. One-hot encode labels and handle class imbalance  
4. Build and train the Bidirectional LSTM model  
5. Evaluate using classification report and confusion matrix  
6. Save the trained model for deployment

---

## Author

**Om Patil** – [GitHub Profile]([https://github.com/yourusername](https://github.com/OmPatil2806))
