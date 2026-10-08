# Deep Learning Image Classification

## Overview

This project develops a multi-class image classification system to classify four monkey species:

- Bald Uakari
- Mandrill
- Proboscis Monkey
- Emperor Tamarin

The project compares four pre-trained deep learning architectures using transfer learning.

## Dataset

The dataset contains 4,000 RGB images, with 1,000 images per class.

The original dataset contained 10 monkey species, but four classes were selected for this project.

## Models Compared

- VGG16
- ResNet50
- InceptionV3
- MobileNetV2

All models used ImageNet pre-trained weights and were adapted for four-class classification.

## Data Preparation

- Image resizing
- Normalization
- Data cleaning
- Data augmentation
- Label encoding
- Stratified train-validation-test split

Dataset split:

- Training: 70%
- Validation: 15%
- Testing: 15%

## Training

Transfer learning was used to reduce training requirements and take advantage of features already learned from ImageNet.

The models were trained using:

- Cross-Entropy Loss
- Adam optimizer
- Hyperparameter tuning
- Best-model checkpointing

Learning rate and number of epochs were tested for each architecture.

## Results

| Model | Test Accuracy |
|---|---:|
| VGG16 | 98.83% |
| ResNet50 | 98.50% |
| InceptionV3 | 98.83% |
| MobileNetV2 | 98.33% |

VGG16 and InceptionV3 achieved the highest test accuracy at approximately 98.8%.

## Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

The results showed strong generalization across all four architectures.

## Key Findings

- VGG16 and InceptionV3 achieved the highest test accuracy.
- confusion matrix for the VGG16:
- ## VGG16 Confusion Matrix

| Actual \ Predicted | Bald Uakari | Emperor Tamarin | Mandrill | Proboscis Monkey |
|---|---:|---:|---:|---:|
| **Bald Uakari** | 148 | 1 | 0 | 1 |
| **Emperor Tamarin** | 0 | 150 | 0 | 0 |
| **Mandrill** | 0 | 0 | 150 | 0 |
| **Proboscis Monkey** | 2 | 1 | 2 | 145 |

-The model classified Emperor Tamarin and Mandrill perfectly, while most errors occurred between Proboscis Monkey and the other classes.
- ResNet50 showed the smallest gap between training and validation accuracy.
- MobileNetV2 achieved slightly lower accuracy but remained highly competitive despite being a lightweight model.
- Most classification errors occurred between Bald Uakari and Proboscis Monkey.

## Technologies Used

- Python
- PyTorch
- Torchvision
- Scikit-learn
- NumPy
- Matplotlib
- Google Colab

## Future Improvements

- Train on all 10 monkey species
- Use a larger dataset
- Test more hyperparameter combinations
- Explore fine-tuning more layers
- Add Grad-CAM for model explainability

