# Industrial Defect Detection using YOLOv8

## Overview
This project builds an **industrial defect detection system** using **YOLOv8**.  
It automatically downloads a real-world casting dataset, converts it into YOLO format, and trains a lightweight object detection model to classify defective and non-defective products.

---

## Dataset
- Source: Kaggle – *Real-life Industrial Dataset of Casting Products*
- Classes:
  - `def_front` → Defective products  
  - `ok_front` → Non-defective products  

The dataset is automatically downloaded using `kagglehub`, so no manual setup is required.

---

## Installation

Install all required dependencies:

```bash
pip install ultralytics kagglehub opencv-python matplotlib
```
## Workflow
### 1. Dataset Download
Automatically downloads dataset from Kaggle using kagglehub.
### 2. Data Preprocessing
Organizes images into:
Training set
Validation set
Converts labels into YOLO format:
Defective images → Full bounding box
Non-defective images → Empty label file
## Dataset Structure
```bash
yolo_dataset/
│
├── images/
│   ├── train/
│   └── val/
│
├── labels/
│   ├── train/
│   └── val/
│
└── data.yaml
```
## Model
Model Used: YOLOv8 Nano (yolov8n.pt)
Chosen for:
Fast training
Lightweight architecture
Suitable for quick experimentation
## Training
```bash
model.train(
    data="yolo_dataset/data.yaml",
    epochs=10,
    imgsz=640,
    batch=16,
    verbose=False
)```
## Training Parameters
```bash
Epochs: 10
Image Size: 640
Batch Size: 16
## Evaluation
metrics = model.val()

print(metrics.box.map50)  # mAP@50
print(metrics.box.map)    # mAP@50-95

Optional (to save predictions):

results = model.val(save_json=True)```
## Results

The model outputs:

Detection performance metrics:
mAP@50
mAP@50-95
Optional JSON file containing predictions
