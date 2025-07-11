# DrowsinessDetection
Real-time Drowsiness Detection using YOLOv5 – A custom object detection model that classifies 'awake' vs 'drowsy' states via webcam. Trained with custom data and annotated using labelImg. Ready for integration and deployment.

## 📸 Demo

| Awake Detection | Drowsy Detection |
|-----------------|------------------|
| ![awake](data/demo/awake_demo.jpg) | ![drowsy](data/demo/drowsy_demo.jpg) |

> *Real-time webcam inference using a custom YOLOv5 model.*

---

## 🚀 Features

- 🔍 Real-time object detection with OpenCV
- 🧠 Custom YOLOv5 training on two classes: `awake` and `drowsy`
- 🎯 Manual data collection with webcam
- 🏷️ Image annotation using `labelImg`
- 🛠️ Model export-ready for deployment

---

## 📁 Project Structure

```bash
.
├── data/
│   ├── images/               # Collected images
│   ├── labels/               # YOLO-format annotation files
│   ├── test/                 # Test images
│   └── demo/                 # Optional demo images for README
├── yolov5/                   # Cloned YOLOv5 repo
├── labelImg/                 # Cloned labelImg tool
├── dataset.yml               # Dataset config file
├── drowsiness_detect.py      # Real-time detection script
├── requirements.txt
└── README.md

