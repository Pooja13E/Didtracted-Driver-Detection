# Distracted-Driver-Detection-Using-DL

## Project Overview

Distracted driving is one of the leading causes of road accidents worldwide. This project presents a comprehensive deep learning–based framework to detect distracted driver behaviors using dashboard camera images. We evaluate and compare eight state-of-the-art CNN and object detection models for both classification and real-time detection tasks.

The system aims to support intelligent driver monitoring systems that enhance road safety by identifying unsafe driver behaviors accurately and efficiently.

---

## Models Implemented

### Classification Models
- EfficientNetV2M
- Xception
- VGG19
- InceptionV3
- ResNet152V2
- NASNetMobile

### Object Detection Models
- YOLOv8
- YOLOv10

---

## Dataset

- **Dataset**: State Farm Distracted Driver Detection Dataset  
- **Total Images**: 22,424  
- **Classes**: 10 driver behavior categories (c0–c9)  
- **Image Resolution**: 640×480  
- **Link**: https://www.kaggle.com/datasets/rightway11/state-farm-distracted-driver-detection  

### Driver Behavior Classes
- c0: Safe driving
- c1: Texting using right hand
- c2: Talking on the phone using right hand
- c3: Texting using left hand
- c4: Talking on the phone using left hand
- c5: Operating the radio
- c6: Drinking
- c7: Reaching behind
- c8: Hair and makeup
- c9: Talking to a passenger

---

## Methodology

### Preprocessing
- Corrupted image removal using PIL
- SHA-256 duplicate image detection
- Driver-wise group-stratified train/validation split
- Model-specific resizing and ImageNet normalization

### Data Augmentation
- Horizontal flips
- Rotations (±15°)
- Zoom and translation
- Brightness and contrast adjustments

### Training Strategy
- Transfer learning with ImageNet-pretrained weights
- Fine-tuning of top layers
- Early stopping and learning rate scheduling
- Categorical cross-entropy loss

### YOLO Pipeline (Object Detection)
- Manual annotation of a starter dataset using Roboflow
- Baseline YOLOv8 training
- Pseudo-labeling of ~21k unlabeled images
- High-confidence label filtering
- Final driver-wise split and fine-tuning

---

## Results

### Classification Performance

| Model | Accuracy |
|------|----------|
| EfficientNetV2M | 87.67% |
| Xception | 82.87% |
| VGG19 | 82.22% |
| InceptionV3 | 80.80% |
| ResNet152V2 | 77.24% |
| NASNetMobile | 58.79% |

### Object Detection Performance

| Model | mAP50 | mAP50-95 |
|------|-------|----------|
| YOLOv8 | 0.89 | 0.76 |
| YOLOv10 | 0.89 | 0.75 |

---

## Key Findings
- EfficientNetV2M achieved the best overall classification performance
- YOLOv8 provided the strongest real-time detection accuracy
- Driver-wise splitting ensured fair and leakage-free evaluation
- YOLO models are more suitable for real-time deployment

---

## Future Work
- Extend to video-based driver monitoring
- Integrate eye and head movement tracking
- Optimize models for edge and embedded devices
- Add night-time and multi-angle data
- Incorporate Explainable AI (Grad-CAM) for interpretability

---

## Team Members
- Sowjanya R  
- Vishnupriya S  
- Pooja E  
