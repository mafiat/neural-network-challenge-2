# neural-network-challenge-2

# Multi-Output Neural Network for Employee Attrition and Department Prediction

This project demonstrates the use of a multi-output neural network to predict employee attrition and department based on various features. The model is built using TensorFlow/Keras and includes preprocessing steps such as scaling and one-hot encoding.

## Table of Contents

- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Training](#training)
- [Evaluation](#evaluation)
- [Results](#results)
- [Improvements](#improvements)

## Dataset

The dataset used in this project contains employee information, including features such as age, education, job satisfaction, and more. The target variables are:
- `Attrition`: Whether the employee has left the company (binary classification).
- `Department`: The department of the employee (multi-class classification).

## Preprocessing

The preprocessing steps include:
1. Splitting the dataset into training and testing sets.
2. Scaling numerical features using `StandardScaler`.
3. One-hot encoding categorical features (`Attrition` and `Department`).

## Model Architecture

The model consists of:
- **Input Layer**: Accepts 10 numerical features.
- **Shared Layers**: Two dense layers shared between both outputs.
- **Branch for Department**:
    - A hidden layer with 32 neurons and `softmax` activation.
    - An output layer with 3 neurons and `softmax` activation for multi-class classification.
- **Branch for Attrition**:
    - A hidden layer with 32 neurons and `sigmoid` activation.
    - An output layer with 2 neurons and `sigmoid` activation for binary classification.

## Training

The model is compiled with:
- Optimizer: `adam`
- Loss functions:
    - `categorical_crossentropy` for the department output.
    - `binary_crossentropy` for the attrition output.
- Metrics: Accuracy for both outputs.

The model is trained for 100 epochs with a batch size of 32.

## Evaluation

The model is evaluated on the test set, and the following metrics are reported:
- Loss and accuracy for both `Attrition` and `Department`.

## Results

- **Department Accuracy**: ~49.3%
- **Attrition Accuracy**: ~81.6%

## Improvements

To improve the model, consider:
1. Hyperparameter tuning (e.g., learning rate, batch size, number of layers).
2. Addressing class imbalance using techniques like oversampling or class weighting.
3. Adding regularization techniques like dropout or batch normalization.
4. Incorporating additional features or engineering new features.

## Summary

This project demonstrates the use of a multi-output neural network for predicting employee attrition and department. While the model achieves reasonable accuracy, further improvements can be made to enhance its performance.

## Requirements

- Python 3.x
- TensorFlow
- scikit-learn
- pandas
- numpy