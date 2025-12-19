# Dental X-Ray Object Counting & Representation Learning
#### Course: CSE475 (Machine Learning)
#### Semester: Fall 2025 
#### Section: 1
#### East West University
This repository contains our semester project focused on the automated counting and detection of dental structures using high-resolution X-ray imagery. We compare the effectiveness of the latest object detection models against self-supervised and semi-supervised learning techniques.

```css
                  Team Members (Group H)
```

```css
        |-------------------------|------------------|
        |          Name           |     Student ID   |
        |-------------------------|------------------|
        |   Nafisa Saiyara Aranti |   2022-1-60-060  |
        |    Rebeka Sultana Dina  |   2022-3-60-027  |
        |       Lamiya Akter      |   2022-2-60-055  |
        |-------------------------|------------------|
```

## Project Objective: Object Counting

The primary goal of this project is to accurately count specific objects within dental X-rays (such as teeth or dental work). Our research explores:

## Quantification

Moving beyond simple detection to provide accurate numerical counts of features in a scan.

## Methodological Comparison

Analyzing how different training strategies—Supervised, Self-Supervised, and Semi-Supervised—impact counting accuracy.

## Model Architectures

1. **Baseline Detection Models (Object Counting):**
   We implemented the most recent versions of the YOLO family to establish a performance benchmark for counting:

- YOLOv10
- YOLOv11
- YOLOv12

2. **Self-Supervised Learning (SSL):**
   These methods allow the model to learn the "structure" of dental X-rays from unlabeled images, improving the model's internal feature recognition:

- **SimCLR:** A framework that teaches the model to recognize similar images through different augmentations.
- **MoCo (Momentum Contrast):** A method that helps the model build a memory of features to better distinguish between complex dental structures.

3. **Semi-Supervised Learning**
   To get the best results from a mix of a small amount of labeled data and a large amount of unlabeled data:

- **STAC (Self-Training and Augmentation Consistency):** This method uses YOLOv11 as the backbone to create "pseudo-labels" for unlabeled data, significantly boosting the model's counting performance.

##  Repository Structure

├── models/ # Code for YOLO variants, SSL frameworks, and STAC

├── training/ # Training scripts and configuration files

├── evaluation/ # Performance analysis and counting error reports

└── README.md # Project documentation

## Evaluation Metrics
For our counting task, we evaluate performance using:

- **Mean Absolute Error (MAE):** Tells us the average difference between the actual count and the model's predicted count.

- **Root Mean Squared Error (RMSE):** Helps us identify if the model is making any large counting mistakes.
- **mAP:** Ensures the model is counting the correct objects by checking the accuracy of its detections.
