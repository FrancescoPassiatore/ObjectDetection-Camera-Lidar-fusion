# Object Detection with Camera-LiDAR Fusion on MAN TruckScenes Dataset

This project performs object detection on the **MAN TruckScenes** dataset using a combination of camera and LiDAR data. It consists of four main stages:

1. **Initial Inference using YOLOv8**
2. **LiDAR Point Cloud Projection on YOLOv8 Predictions**
3. **YOLOv8 Training with TruckScenes labels and with merged labels**
4. **Inference with Trained Models**

---

## Project Overview

### Setup Instructions

Before running any of the core steps, make sure to:

#### 1. Dataset and Environment Setup
- Download the **MAN TruckScenes** dataset.
- Install required packages:
  - `ultralytics` for YOLOv8
  - `truckscenes-devkit` for dataset handling
- Initialize the TruckScenes dataset.

#### 2. Imports
- Import all necessary libraries for YOLO, data manipulation, and visualization.

---

## Pipeline Description

### 1. YOLOv8 vs Ground Truth
- Perform inference with a pre-trained **YOLOv8** model.
- Compare predicted results with **2D annotations** from the MAN TruckScenes dataset.

### 2. LiDAR Fusion
- Project **LiDAR point clouds** onto camera images.
- Count LiDAR points inside each YOLOv8 bounding box and gather statistics.

### 3. Enhance YOLOv8 - Training with MAN TruckScenes Labels
- Convert MAN TruckScenes annotations to **YOLO format**.
- Split the dataset into **training** and **validation** sets.
- Generate a `data.yaml` configuration file with the new labels.
- Train YOLOv8n for **50 epochs**.

### 4. Enhance YOLOv8 - Training with Merged Labels
- Same as above, but merges TruckScenes labels.
- Train YOLOv8n for **100 epochs**, freezing the first 5 layers.

---

## Inference with Trained Models

### Second Inference - Trained on MAN TruckScenes Labels
- Use the trained model to perform inference and evaluate performance.

### Third Inference - Trained on Merged Labels
- Inference using the YOLOv8 model trained with merged label sources.

> 📝 **Note**: These steps require the trained models. You can either train them yourself or **download the pre-trained models** from the GitHub repository (see below).

---

## Using Pre-trained Models

To use the pre-trained models:

1. Clone the GitHub repository.
2. Download the trained YOLOv8 models.
3. Use the provided Colab notebook to run inference with the models.

---

## How to Run (Google Colab)

All main steps are implemented in the provided **Google Colab notebook**.

Each step is **independent** and can be run individually — except the **second and third inferences**, which require trained models.

