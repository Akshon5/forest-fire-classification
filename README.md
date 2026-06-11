# Forest Fire Classification using MobileNetV2

## Overview

This project presents a lightweight deep learning system for wildfire image classification using transfer learning with MobileNetV2. The goal is to accurately distinguish between fire and non-fire scenes while maintaining computational efficiency suitable for deployment on edge devices such as drones, embedded AI systems, and real-time monitoring platforms.

The project originated from an undergraduate research study investigating efficient deep learning architectures for wildfire detection and classification.

---

## Key Features

* Transfer Learning using MobileNetV2
* Fine-tuning of pretrained ImageNet weights
* Data Augmentation for improved generalization
* Class Imbalance Handling using weighted loss functions
* Early Stopping and Learning Rate Scheduling
* Edge-Deployment-Oriented Architecture
* Comprehensive Model Evaluation

---

## Dataset

The model was trained on a curated dataset containing:

* 477 Fire Images
* 631 Non-Fire Images
* Total Images: 1,108

Images were resized to 224×224 pixels and divided using an 80:20 training-validation split.

---

## Data Augmentation

To improve robustness across diverse wildfire scenarios, the following augmentation techniques were applied:

* Horizontal Flipping
* Random Zoom
* Brightness Adjustment
* Rotation
* Width and Height Shifts

These transformations help the model generalize to varying environmental and lighting conditions.

---

## Model Architecture

### MobileNetV2

MobileNetV2 was selected due to its:

* Low computational complexity
* Efficient inference speed
* Strong classification performance
* Suitability for edge deployment

The network was initialized with pretrained ImageNet weights and the final 30 layers were fine-tuned on the wildfire dataset.

---

## Training Strategy

The training pipeline incorporated:

* Transfer Learning
* Fine-Tuning
* Class Weighting
* EarlyStopping
* ReduceLROnPlateau
* Model Checkpointing

These techniques improved convergence, reduced overfitting, and enhanced minority-class performance.

---

## Results

| Metric              | Score  |
| ------------------- | ------ |
| Validation Accuracy | 91.33% |
| ROC-AUC             | > 0.91 |
| Cohen's Kappa       | 0.80   |
| Fire Precision      | 91%    |
| Fire Recall         | 81%    |
| Fire F1 Score       | 0.86   |

The model achieved strong classification performance while remaining lightweight enough for deployment in resource-constrained environments.

---

## Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn

---

## Potential Applications

* Forest Fire Monitoring
* Drone-Based Surveillance
* Smart Environmental Monitoring Systems
* Edge AI Deployment
* Emergency Response Systems

---

## Future Improvements

* Thermal Image Integration
* Video-Based Fire Detection
* Grad-CAM Explainability
* TensorFlow Lite Optimization
* Multimodal RGB + Thermal Fusion
* Real-Time Deployment on Embedded Devices

---

## Repository Structure

```text
forest-fire-classification/
│
├── forest_fire_classification.ipynb
├── README.md
├── requirements.txt
└── images/
```

---

## Author

Akshon Choudhary

B.Tech Robotics & Artificial Intelligence
Thapar Institute of Engineering and Technology
