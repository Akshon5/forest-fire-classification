# Forest Fire Classification using MobileNetV2

## Overview

Wildfires are among the most destructive natural disasters, causing severe environmental, economic, and human losses worldwide. Early and accurate fire detection is critical for minimizing damage and improving emergency response.

This project presents a lightweight deep learning solution for wildfire image classification using Transfer Learning with MobileNetV2. The system is designed to distinguish between wildfire and non-wildfire images while maintaining computational efficiency suitable for deployment on edge devices such as drones, embedded AI systems, and remote monitoring stations.

The project was developed as part of an undergraduate research study investigating efficient deep learning approaches for real-time wildfire detection.

---

## Problem Statement

Traditional wildfire monitoring systems often rely on satellite imagery, manual surveillance, or sensor networks. While effective in certain situations, these approaches may suffer from:

* Detection delays
* High operational costs
* Limited real-time coverage
* Environmental constraints

Recent advances in Computer Vision and Deep Learning have enabled automated image-based wildfire detection systems capable of providing rapid and scalable monitoring solutions.

The objective of this project is to develop a lightweight and accurate image classification model that can identify wildfire events from visual imagery while remaining practical for real-world deployment.

---

## Dataset

A custom curated dataset containing wildfire and non-wildfire images was used for training and evaluation.

### Dataset Statistics

| Category | Number of Images |
| -------- | ---------------- |
| Fire     | 477              |
| Non-Fire | 631              |
| Total    | 1,108            |

### Data Preparation

* Images resized to 224 × 224 pixels
* Dataset organized into Fire and Non-Fire classes
* 80:20 training-validation split
* Automated loading using TensorFlow data generators

The dataset was carefully curated and cleaned to improve image quality and remove duplicate or irrelevant samples.

---

## Data Augmentation

To improve model generalization and robustness under varying environmental conditions, multiple augmentation techniques were applied during training:

* Horizontal Flipping
* Random Rotation
* Random Zoom
* Width Shifting
* Height Shifting
* Brightness Adjustment

These augmentations help simulate diverse wildfire scenarios and reduce overfitting.

---

## Model Architecture

### MobileNetV2

The project utilizes MobileNetV2, a lightweight convolutional neural network architecture originally developed for mobile and edge computing applications.

#### Reasons for Selection

* Low computational complexity
* Fast inference speed
* Reduced memory requirements
* Strong image classification performance
* Suitable for real-time deployment

The model was initialized with pretrained ImageNet weights and adapted using Transfer Learning.

### Transfer Learning Strategy

Instead of training from scratch:

1. Pretrained ImageNet weights were loaded.
2. The base feature extractor was retained.
3. The final classification layers were customized.
4. The last 30 layers were fine-tuned on the wildfire dataset.

This approach significantly reduced training time while improving classification accuracy.

---

## Handling Class Imbalance

The dataset contained an unequal distribution between Fire and Non-Fire samples.

To address this issue:

* Dynamic class weights were calculated.
* Weighted loss functions were applied during training.

This helped improve minority-class recognition and reduced prediction bias.

---

## Training Strategy

Several optimization techniques were incorporated to improve model performance.

### Early Stopping

Training automatically stopped when validation performance ceased improving.

Benefits:

* Reduced overfitting
* Faster training
* Improved generalization

### Learning Rate Scheduling

ReduceLROnPlateau was used to dynamically lower the learning rate during training when validation metrics plateaued.

### Model Checkpointing

The best-performing model weights were preserved throughout training.

---

## Evaluation Metrics

Performance was evaluated using multiple metrics to provide a comprehensive assessment.

### Metrics Used

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC Score
* Confusion Matrix
* Classification Report
* Cohen's Kappa Score

---

## Results

### Overall Performance

| Metric              | Score  |
| ------------------- | ------ |
| Validation Accuracy | 91.33% |
| ROC-AUC Score       | > 0.91 |
| Cohen's Kappa Score | 0.799  |

### Class-wise Performance

| Class    | Precision | Recall | F1 Score |
| -------- | --------- | ------ | -------- |
| Non-Fire | 91%       | 96%    | 94%      |
| Fire     | 91%       | 81%    | 86%      |

### Key Findings

* Achieved strong classification performance despite a relatively small dataset.
* Successfully identified wildfire imagery under diverse environmental conditions.
* Maintained high accuracy while using a lightweight architecture.
* Demonstrated suitability for resource-constrained deployment scenarios.

---

## Technology Stack

### Programming Language

* Python

### Libraries and Frameworks

* TensorFlow
* Keras
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn

### Development Environment

* Jupyter Notebook
* Google Colab

---

## Repository Structure

```text
forest-fire-classification/
│
├── forest_fire_classification.ipynb
├── README.md
├── requirements.txt
├── .gitignore
│
└── images/
    ├── confusion_matrix.png
    ├── roc_curve.png
    ├── training_accuracy.png
    └── sample_predictions.png
```

---

## Potential Applications

The proposed system can be extended to support:

* Forest Fire Monitoring Systems
* Drone-Based Fire Surveillance
* Smart Environmental Monitoring
* Edge AI Applications
* Emergency Response Systems
* Remote Fire Detection Networks

---

## Limitations

Despite strong performance, several challenges remain:

* Smoke-heavy scenes may be difficult to classify accurately.
* Industrial emissions can sometimes resemble wildfire patterns.
* Performance may vary under extreme lighting conditions.
* The model currently operates on static images rather than video streams.

---

## Future Work

Potential improvements include:

### Multimodal Learning

Combining RGB imagery with:

* Thermal Cameras
* Infrared Sensors
* Satellite Imagery

### Video-Based Detection

Extending the system to analyze temporal information from video streams using:

* ConvLSTM Networks
* Temporal CNNs
* Video Transformers

### Explainable AI

Integrating interpretability methods such as:

* Grad-CAM
* Saliency Maps
* Attention Visualization

### Edge Deployment

Optimizing the model for deployment using:

* TensorFlow Lite
* ONNX
* NVIDIA Jetson Devices
* Raspberry Pi Systems

---

## Research Contribution

This project originated from an undergraduate research study focused on lightweight deep learning architectures for wildfire classification.

The work investigates how transfer learning, class balancing, and data augmentation can be combined to create accurate yet computationally efficient wildfire detection systems suitable for real-world deployment.

---

## Author

**Akshon Choudhary**

B.Tech – Robotics & Artificial Intelligence
Thapar Institute of Engineering and Technology

Areas of Interest:

* Machine Learning
* Computer Vision
* Deep Learning
* Reinforcement Learning
* Robotics
* Artificial Intelligence Systems
