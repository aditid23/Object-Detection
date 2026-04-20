# 🏭 Industrial Defect Detection using YOLOv8

## 📌 Overview
This project builds an **industrial defect detection system** using **YOLOv8**.  
It automatically downloads a real-world casting dataset, converts it into YOLO format, and trains a lightweight object detection model to classify defective and non-defective products.

---

## 📂 Dataset
- Source: Kaggle – *Real-life Industrial Dataset of Casting Products*
- Classes:
  - `def_front` → Defective products  
  - `ok_front` → Non-defective products  

The dataset is automatically downloaded using `kagglehub`, so no manual setup is required.

---

## ⚙️ Installation

Install all required dependencies:

```bash
pip install ultralytics kagglehub opencv-python matplotlib
🚀 Workflow
🔹 1. Dataset Download
Automatically downloads dataset from Kaggle using kagglehub.
🔹 2. Data Preprocessing
Organizes images into:
Training set
Validation set
Converts labels into YOLO format:
Defective images → Full bounding box
Non-defective images → Empty label file
📁 Dataset Structure
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
🧠 Model
Model Used: YOLOv8 Nano (yolov8n.pt)
Chosen for:
Fast training
Lightweight architecture
Suitable for quick experimentation
🏋️ Training
model.train(
    data="yolo_dataset/data.yaml",
    epochs=10,
    imgsz=640,
    batch=16,
    verbose=False
)
⚙️ Training Parameters
Epochs: 10
Image Size: 640
Batch Size: 16
📊 Evaluation
metrics = model.val()

print(metrics.box.map50)  # mAP@50
print(metrics.box.map)    # mAP@50-95

Optional (to save predictions):

results = model.val(save_json=True)
📈 Results

The model outputs:

Detection performance metrics:
mAP@50
mAP@50-95
Optional JSON file containing predictions
✨ Features
✅ Automatic dataset download
✅ YOLO format dataset generation
✅ Lightweight YOLOv8 training
✅ Minimal preprocessing pipeline
✅ Standard evaluation metrics
⚠️ Limitations
Non-defective images contain no bounding boxes
Defects are labeled using full-image bounding boxes
Performance is limited due to:
Simplified annotations
Small number of training epochs
🔧 Future Improvements
Add precise bounding box annotations
Train with larger YOLO models (YOLOv8m / YOLOv8l)
Increase dataset size and diversity
Implement real-time defect detection
Multi-class defect classification
👩‍💻 Author

Aditi Damodar
B.Tech AI & DS | ML Engineer

🙏 Acknowledgements
Ultralytics YOLOv8
Kaggle Dataset Contributors
⭐ If you found this useful, consider starring the repository!

---

If you want, I can upgrade this further with:
- 📸 Results images section (very useful for GitHub)
- 🚀 Demo GIF
- 📊 Comparison table (before vs after improvements)
- 🧪 Experiment section (since you’re doing lab work)

Just tell me 👍
give workflow also in the same way

Got it — you want the workflow section also formatted cleanly for GitHub just like the rest. Here’s an upgraded version you can directly paste into your README:

## 🚀 Workflow

The complete pipeline is automated and consists of the following steps:

---

### 🔹 Step 1: Install Dependencies
Required libraries are installed:
- ultralytics (YOLOv8)
- kagglehub (dataset download)
- opencv-python
- matplotlib

```bash
pip install ultralytics kagglehub opencv-python matplotlib
🔹 Step 2: Dataset Download
Dataset is downloaded automatically using kagglehub
No manual Kaggle API setup required
path = kagglehub.dataset_download("ravirajsinh45/real-life-industrial-dataset-of-casting-product")
🔹 Step 3: Data Organization
Extracts paths for:
Training defective images
Training non-defective images
Validation defective images
Validation non-defective images
Creates YOLO directory structure:
yolo_dataset/
├── images/train
├── images/val
├── labels/train
├── labels/val
🔹 Step 4: Label Generation
Converts classification dataset → detection dataset
Image Type	Label File Content
Defective	0 0.5 0.5 1.0 1.0
Non-defective	(empty file)
This means:
Class ID = 0 (defect)
Bounding box = full image
🔹 Step 5: YAML Configuration

Creates data.yaml file:

path: /content/yolo_dataset
train: images/train
val: images/val
names:
  0: defect
🔹 Step 6: Model Initialization
Loads pre-trained YOLOv8 nano model:
model = YOLO("yolov8n.pt")
🔹 Step 7: Model Training
Trains the model on prepared dataset:
model.train(
    data="yolo_dataset/data.yaml",
    epochs=10,
    imgsz=640,
    batch=16,
    verbose=False
)
🔹 Step 8: Model Evaluation
Evaluates performance using validation data:
metrics = model.val()
Key metrics:
mAP@50
mAP@50-95
🔹 Step 9: Save Predictions (Optional)
results = model.val(save_json=True)
Saves predictions in JSON format
🔄 Workflow Summary
Install Libraries
        ↓
Download Dataset
        ↓
Organize Data
        ↓
Generate Labels
        ↓
Create YAML File
        ↓
Load YOLOv8 Model
        ↓
Train Model
        ↓
Evaluate Model
        ↓
Save Results

---

If you want to make your GitHub stand out even more, I can next:
- Convert this workflow into a **diagram (flowchart image)**
- Add **architecture diagram**
- Add **step-by-step screenshots from Colab**

Just tell me 👍
give the entiree read.me file so that i can directly paste into github

Here’s your complete, polished, GitHub-ready README.md — you can copy and paste this directly:

# 🏭 Industrial Defect Detection using YOLOv8

## 📌 Overview
This project builds an **industrial defect detection system** using **YOLOv8**.  
It automatically downloads a real-world casting dataset, converts it into YOLO format, and trains a lightweight object detection model to classify defective and non-defective products.

---

## 📂 Dataset
- Source: Kaggle – *Real-life Industrial Dataset of Casting Products*
- Classes:
  - `def_front` → Defective products  
  - `ok_front` → Non-defective products  

The dataset is automatically downloaded using `kagglehub`, so no manual setup is required.

---

## ⚙️ Installation

Install all required dependencies:

```bash
pip install ultralytics kagglehub opencv-python matplotlib
🚀 Workflow

The complete pipeline is automated and consists of the following steps:

🔹 Step 1: Install Dependencies

Required libraries:

ultralytics (YOLOv8)
kagglehub (dataset download)
opencv-python
matplotlib
🔹 Step 2: Dataset Download

Dataset is downloaded automatically:

path = kagglehub.dataset_download("ravirajsinh45/real-life-industrial-dataset-of-casting-product")
🔹 Step 3: Data Organization
Extracts paths for:
Training defective images
Training non-defective images
Validation defective images
Validation non-defective images
Creates YOLO directory structure:
yolo_dataset/
├── images/train
├── images/val
├── labels/train
├── labels/val
🔹 Step 4: Label Generation
Image Type	Label File Content
Defective	0 0.5 0.5 1.0 1.0
Non-defective	(empty file)
Class ID = 0 (defect)
Bounding box = full image
🔹 Step 5: YAML Configuration
path: /content/yolo_dataset
train: images/train
val: images/val
names:
  0: defect
🔹 Step 6: Model Initialization
from ultralytics import YOLO
model = YOLO("yolov8n.pt")
🔹 Step 7: Model Training
model.train(
    data="yolo_dataset/data.yaml",
    epochs=10,
    imgsz=640,
    batch=16,
    verbose=False
)
🔹 Step 8: Model Evaluation
metrics = model.val()

print(metrics.box.map50)  # mAP@50
print(metrics.box.map)    # mAP@50-95
🔹 Step 9: Save Predictions (Optional)
results = model.val(save_json=True)
🔄 Workflow Summary
Install Libraries
        ↓
Download Dataset
        ↓
Organize Data
        ↓
Generate Labels
        ↓
Create YAML File
        ↓
Load YOLOv8 Model
        ↓
Train Model
        ↓
Evaluate Model
        ↓
Save Results
🧠 Model
Model Used: YOLOv8 Nano (yolov8n.pt)
Advantages:
Lightweight
Fast training
Suitable for quick experimentation
📊 Evaluation Metrics
mAP@50
mAP@50-95

These metrics evaluate how well the model detects defective objects.

📈 Output
Detection performance scores
Optional JSON predictions file
✨ Features
✅ Automatic dataset download
✅ YOLO format dataset generation
✅ Lightweight YOLOv8 training
✅ Simple defect detection pipeline
✅ Standard evaluation metrics
⚠️ Limitations
Non-defective images contain no bounding boxes
Defects are labeled using full-image bounding boxes
Limited accuracy due to:
Simplified annotations
Few training epochs
🔧 Future Improvements
Add precise bounding box annotations
Train with larger YOLO models (YOLOv8m / YOLOv8l)
Increase dataset size and diversity
Implement real-time defect detection
Multi-class defect classification
