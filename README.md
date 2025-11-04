# Custom Multitask Indian Road Dataset

This repository contains a **custom annotated dataset** created for **multitask learning on Indian unstructured roads**, specifically designed for **YOLO-based models**.

---

## Dataset Overview
- **Name:** Custom Multitask Indian Road Dataset  
- **Size:** ~95 MB (ZIP format)  
- **Format:** YOLO-compatible annotations  
- **Tasks:**  
  - Object Detection  
  - Semantic Segmentation  
  - Lane Detection  
- **Environment:** Indian unstructured road scenes with diverse lighting, weather, and traffic conditions.  

---

## Motivation
Autonomous driving in Indian roads poses unique challenges due to unstructured traffic, diverse road markings, and inconsistent infrastructure.  
This dataset aims to provide a **reproducible benchmark** for multitask perception models like YOLO that can perform detection, segmentation, and lane understanding simultaneously.

---

## Reproducibility
This dataset is shared publicly to enable **reproducible research**.  
Researchers and practitioners can:
- Train and benchmark multitask models.
- Validate results reported in related papers.
- Extend or refine the dataset for new tasks.

Please cite or reference this repository if you use it in your work.

---

## 📦 File Details
The dataset is provided as a ZIP file:
Unzip the file to access:
- `/images/` — raw images  
- `/labels/` — YOLO-format annotations for detection and segmentation tasks  
It has total of 12 classes 10 detection class + 1 drivable area segmentation + 1 lane line segmentation

---

## 🚀 Example Usage (YOLOv8)
To train using YOLOv8:
```bash
yolo task=detect mode=train model=yolov8m.pt data=data.yaml epochs=100 imgsz=640


### 📁 Dataset Structure
After extracting the ZIP, the folder structure looks like this:

# The id represent the correspondence relation
├─dataset root
│ ├─images
│ │ ├─train
│ ├─detection-object
│ │ ├─labels
│ │ │ ├─train
│ ├─seg-drivable-10
│ │ ├─labels
│ │ │ ├─train
│ ├─seg-lane-11
│ │ ├─labels
│ │ │ ├─train

Classes:
# Classes for all tasks
names:
  0: person
  1: auto
  2: car
  3: bus
  4: pothole
  5: bike
  6: cracks
  7: manhole
  8: speedbump
  9: waterlogging
  10: drivable  
  11: lane  
