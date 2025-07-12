# DrowsinessDetection
Real-time Drowsiness Detection using YOLOv5 – A custom object detection model that classifies 'awake' vs 'drowsy' states via webcam. Trained with custom data and annotated using labelImg. Ready for integration and deployment.

## 📸 Demo

| Awake Detection | Drowsy Detection |
|-----------------|------------------|
| ![awake](realtime%20detection%20screenshots/Awake.png) | ![drowsy](realtime%20detection%20screenshots/Drowsy.png) |

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
```
## 🚀 How It Works

1. **Data Collection & Annotation**  
   - Images were collected and annotated using [labelImg](https://github.com/tzutalin/labelImg).
   - Two classes were defined: `awake` and `drowsy`.

2. **Model Training**  
   - YOLOv5s was used as the base model.
   - Training was performed with the following command:
     ```bash
     python train.py --img 320 --batch 16 --epochs 15 --data dataset.yml --weights yolov5s.pt
     ```

3. **Inference & Real-Time Detection**  
   - The trained model is loaded and used for image or webcam-based prediction:
     ```python
     import torch
     model = torch.hub.load('ultralytics/yolov5', 'custom', path='yolov5/runs/train/exp6/weights/last.pt')
     results = model('path/to/image.jpg')
     results.print()
     results.show()
     ```

   - For real-time webcam detection:
     ```python
     import cv2

     cap = cv2.VideoCapture(0)
     while cap.isOpened():
         ret, frame = cap.read()
         if not ret:
             break

         results = model(frame)
         annotated_frame = results.render()[0]
         cv2.imshow('YOLO Drowsiness Detection', annotated_frame)

         if cv2.waitKey(10) & 0xFF == ord('q'):
             break

     cap.release()
     cv2.destroyAllWindows()
     ```

4. **Detection Results**  
   Sample predictions on real-time webcam frames:

   ![awake](realtime%20detection%20screenshots/Awake.png)
   ![drowsy](realtime%20detection%20screenshots/Drowsy.png)

  ## 🧠 Tools & Technologies Used

- Python 3.13
- YOLOv5 (Ultralytics)
- OpenCV
- PyTorch
- labelImg
- Jupyter Notebook (for development)
- macOS (for local testing)

## 📂 Folder Structure
```
Drowsiness Detection/
│
├── yolov5/ # YOLOv5 cloned repo
├── dataset/ # Custom dataset
│ ├── images/
│ └── labels/
├── realtime detection screenshots/ # Sample output screenshots
├── dataset.yml # Dataset config file
├── detect.py # Inference script
├── train.py # Training script (YOLOv5)
└── README.md # Project documentation
```

## 📌 Future Improvements

- Enhance dataset with more diverse lighting and subjects
- Optimize model for mobile/embedded deployment
- Add alert system (beep or vibration) on drowsiness detection
- Deploy with a real-time dashboard for monitoring

---


## 📫 Contact

For collaboration or inquiries:

**📧 Email:** [office.sanish@gmail.com]  
**🔗 GitHub:** [SanishCodes](https://github.com/SanishCodes)  
**📸 LinkedIn:** (https://linkedin.com/in/mr.sanishshrestha)


