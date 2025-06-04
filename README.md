# ObjectDetection-Camera-Lidar-fusion
Object Detection on truck dataset.
Four steps:
- Inference made on YOLOv8
- Projection of LiDAR points on YOLO predictions
- YOLOv8 training
- Inference made on enhanched YOLOv8


# How to use
On the Google Collab notebook all four steps are integrated.
Before running the four steps, it's necessary running the Dataset definition and the Imports
- Dataset Definition:
  - MAN TruckScenes download
  - Install needed packages (ultralytics for YOLO and truckscenes devkit)
  - Truckscenes initialization
- Imports:
  - Importing necessary libraries
- YOLO vs Ground Truth:
  - Inference through YOLOv8 -> Obtain results based on 2D Annotations of MAN Truckscenes
- Lidar Fusion:
  - Projection of LiDAR point clouds on camera images, obtain stats of LiDAR counts based on YOLOv8   bounding boxes
- Enhance YOLOv8 with training:
  - Generate YOLO format annotations from the MAN TruckScenes annotations
  - Divide TruckScenes dataset in training/validation
  - Create data.yaml with new labels obtained from TruckScenes dataset
  - Train YOLOv8n for 50 epochs
- Second Inference:
  - Inference through trained YOLOv8 -> Obtain results
  
