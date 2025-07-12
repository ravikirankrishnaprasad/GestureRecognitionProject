# Gesture Recognition Project

This project involves the development of a gesture recognition system using various deep learning models. The objective is to classify different gestures from video sequences. The project explores multiple model architectures, including Conv3D, ConvLSTM, and a CNN + RNN hybrid model, with the goal of achieving the highest possible accuracy on the validation set.

## 🧠 Problem Statement

Imagine you're working as a data scientist at a home electronics company that manufactures cutting-edge smart televisions. The goal is to develop a feature that allows users to control the TV through **hand gestures**, eliminating the need for a remote control. These gestures are captured in real time by a **webcam mounted on the TV**, enabling seamless interaction.

The system is designed to recognize **five distinct gestures**, each mapped to a specific control action:

- 👍 Thumbs Up: Increase volume  
- 👎 Thumbs Down: Decrease volume  
- 👈 Left Swipe: Rewind 10 seconds  
- 👉 Right Swipe: Forward 10 seconds  
- ✋ Stop: Pause the video  

---

## 🎥 Understanding the Dataset

Each gesture is captured as a **video** comprising **30 sequential image frames**. The dataset includes recordings from multiple users performing gestures under varied conditions. Each video folder contains:

- 30 frames (images) with dimensions of either `360x360` or `120x160`
- A CSV file entry describing:
  - Folder name
  - Gesture label (0 to 4)
  - Gesture class

The dataset is organized into:
- `train/`: Training videos and labels  
- `val/`: Validation set for evaluating model generalization

---

## 🧪 Objective

Your task is to build a deep learning model that can accurately classify gesture videos from the `train` set and perform well on the `val` set. The final model will be evaluated on a separate `test` set (not provided).

To solve this problem, two neural network architectures are recommended:
1. **3D Convolutional Networks** – to directly extract spatiotemporal features from video frames
2. **CNN + RNN Stack** – where CNN processes individual frames and RNN captures the temporal dynamics

---

## 📦 Dataset Access Instructions

To set up the data locally:
```bash
# Step 1: Download the dataset
gdown https://drive.google.com/uc?id=1ehyrYBQ5rbQQe6yL4XbLWe3FMvuVUGiL

# Step 2: Unzip the data
unzip Project_data.zip

## Table of Contents
- [Project Overview](#project-overview)
- [Experimentation](#experimentation)
- [Results](#results)
- [Final Model Selection](#final-model-selection)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The gesture recognition project involves training deep learning models on video sequences to classify different gestures. The project initially started with a baseline Conv3D model and progressively explored different architectures and hyperparameters, including increasing epochs, adjusting batch sizes, and implementing a CNN + RNN hybrid model.

## Experimentation

The following experiments were conducted during the project:

1. **Baseline Conv3D Model**: 
   - **Training Accuracy**: 80.80%
   - **Validation Accuracy**: 27.34%
   - **Validation Loss**: 10.7707

2. **Increasing Number of Epochs (Conv3D)**:
   - **Training Accuracy**: 93.90%
   - **Validation Accuracy**: 71.09%
   - **Validation Loss**: 1.6455

3. **Decreasing Batch Size (Conv3D)**:
   - **Training Accuracy**: 97.92%
   - **Validation Accuracy**: 80.36%
   - **Validation Loss**: 1.3362

4. **Building a ConvLSTM Model**:
   - **Training Accuracy**: 49.78%
   - **Validation Accuracy**: 60.27%
   - **Validation Loss**: 3.5580

5. **Increasing Number of Epochs for ConvLSTM Model**:
   - **Result**: Experiment could not be completed due to disk errors.

6. **CNN + RNN Model**:
   - **Training Accuracy**: 100.0%
   - **Validation Accuracy**: 81.70%
   - **Validation Loss**: 0.7183

## Results

- The CNN + RNN model demonstrated the best performance with a validation accuracy of 81.70% and a validation loss of 0.7183. This model effectively captures both spatial and temporal features, making it the most suitable architecture for this gesture recognition task.

## Final Model Selection

The CNN + RNN model from Experiment 6 is selected as the final model for this project due to its superior performance in both training and validation accuracy. The model is well-balanced and generalizes effectively to unseen data.

## Installation

To run this project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/gesture-recognition-project.git
