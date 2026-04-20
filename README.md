# Object-Detection
# 🏭 Industrial Defect Detection using YOLOv8

## 📌 Overview
This project implements an object detection pipeline using YOLOv8 to identify defects in industrial casting products. The dataset is automatically downloaded, converted into YOLO format, and used to train a lightweight detection model.

---

## 📂 Dataset
- Source: Kaggle (Industrial Casting Product Dataset)
- Classes:
  - `def_front` → Defective products
  - `ok_front` → Non-defective products

The dataset is automatically downloaded using `kagglehub`.

---

## ⚙️ Installation

Install required dependencies:

```bash
pip install ultralytics kagglehub opencv-python matplotlib
