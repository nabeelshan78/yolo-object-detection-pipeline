# 🚗 YOLO Object Detection Pipeline

A professional, end‑to‑end implementation of the YOLO object detection workflow in TensorFlow/Keras.  
From raw images → model inference → clean visualizations → video export, this repo has it all.

---

## 🎯 Project Overview

This repository demonstrates a complete YOLOv2‑style object detection system:

1. **Preprocessing**: Load and resize images.  
2. **Model Inference**: Decode YOLO outputs using a custom `yolo_head`.  
3. **Post‑processing**:  
   - Convert `(x,y,w,h)` to corners  
   - Filter low‑confidence boxes  
   - Apply Non‑Max Suppression (NMS)  
   - Rescale to original image size  
4. **Visualization**: Draw bounding boxes + class labels.  
5. **Exports**:  
   - Save original images  
   - Save predictions separately  
   - Generate side‑by‑side comparison frames  
   - Compile frames into videos

---

## ⚙️ Directory Structure

```bash
yolo_object_detection_pipeline/
│
├── both_images/ # 120 side‑by‑side comparison images
├── images/ # Raw input images
├── originals/ # Saved copies of raw images
├── predictions/ # Prediction outputs (boxes drawn)
├── test_images/ # Sample inputs & their single-frame predictions
├── model_data/ #
│ ├── saved_model.pb # Trained YOLO SavedModel
│ ├── yolo_anchors.txt # Anchor definitions
│ ├── coco_classes.txt # COCO label names
│ ├── pascal_classes.txt # Pascal VOC label names
│ └── variables/ # Model weights
├── videos/ #
│ ├── output_video_orig.mp4 # Original images video
│ ├── output_video_pred.mp4 # Predicted boxes video
│ └── output_video_both.mp4 # Side‑by‑side comparison video
└── notebook.ipynb # Interactive demo: inference → visualization → export
```
---


---

## 🧪 Sample Results

| Original Image | Prediction |
|----------------|------------|
| ![](test_images/cars.jpg) | ![](test_images/cars_pred.png) |
| ![](test_images/giraffe.jpg) | ![](test_images/giraffe_pred.png) |

---

## 🎯 How It Works

### 🔧 1. Load the Model
```python
yolo_model = tf.keras.models.load_model("model_data")


## 🚀 Quick Start

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/yolo-object-detection-pipeline.git
   cd yolo-object-detection-pipeline
```
