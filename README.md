# Road-Detection-Damage-_Pattern_Recognition_
# Road Damage Detection System using YOLOv8

## Final Assignment – Computer Graphics  
**Badr University in Assiut**  
**School of Artificial Intelligence and Data Management**

---

## Project Overview

This project presents a **Road Damage Detection System** using **YOLOv8 Object Detection** to automatically detect and classify road damages such as potholes and cracks from road images.

The purpose of this system is to support road maintenance and infrastructure monitoring by identifying damaged areas efficiently and accurately.

The model performs:

- Road damage detection
- Damage classification
- Bounding box localization
- Confidence score prediction
- Damage counting
- Basic severity estimation

---

## Project Category

**Object Detection**

---

## Objectives

The main objectives of this project are:

- Detect road damages automatically
- Classify different road defects
- Apply computer vision to a real-world infrastructure problem
- Train a custom YOLOv8 model using annotated road damage data
- Perform experiments to improve model performance
- Visualize predictions with confidence scores and bounding boxes

---

## Dataset

The dataset was collected and prepared using **Roboflow** and exported in **YOLOv8 format**.

The dataset includes annotated road images containing different damage types such as:

- Potholes
- Cracks
- Surface road damages

Dataset preparation included:

- Annotated images
- Training set
- Validation set
- Testing set
- YOLO-compatible labels

Dataset platform:

:contentReference[oaicite:0]{index=0}

---

## Data Preprocessing

Before training, several preprocessing techniques were applied:

- Image resizing
- Dataset splitting
- Annotation handling
- Data augmentation
- Automatic normalization (handled internally by YOLOv8)

The training pipeline was configured to improve model generalization and detection performance.

---

## Model Architecture

This project uses:

**YOLOv8 (You Only Look Once Version 8)**

YOLOv8 is a modern object detection model capable of real-time detection with high accuracy.

Framework used:

:contentReference[oaicite:1]{index=1}

---

## Training Configuration

The model was trained using YOLOv8 with custom parameters.

Example training configuration:

```python
results = model.train(
    data=data_yaml,
    epochs=30,
    imgsz=640,
    batch=16,
    optimizer="Adam",
    lr0=0.001,
    name="road_damage_model_v2",
    augment=True,
    patience=20
)
```

### Training Parameters

| Parameter | Value |
|----------|-------|
| Epochs | 30 |
| Image Size | 640 |
| Batch Size | 16 |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Data Augmentation | Enabled |

---

## Experiment

To improve performance, we performed experiments by modifying:

- Number of epochs
- Data augmentation

The goal was to analyze how training settings affect detection performance and model accuracy.

---

## Detection Pipeline

The detection process follows these steps:

1. Load and prepare dataset from Roboflow  
2. Train YOLOv8 model  
3. Run inference on road images  
4. Detect road damages  
5. Draw bounding boxes around detected damages  
6. Display class labels and confidence scores  
7. Count total damages  
8. Estimate severity level

---

## Output Results

The system provides the following outputs:

### 1. Bounding Boxes

Road damages are localized using bounding boxes.

### 2. Class Labels

Detected damages are classified into categories such as:

- Crack
- Pothole

### 3. Confidence Scores

Each prediction includes a confidence score.

Example:

```text
Crack - Confidence: 0.89
Pothole - Confidence: 0.95
```

### 4. Damage Counting

The system counts the total number of detected damages.

Example:

```text
Detected damages count: 5
```

### 5. Severity Estimation

A basic severity estimation was implemented using bounding box area.

Example logic:

```python
if area < 5000:
    severity = "Low"

elif area < 15000:
    severity = "Medium"

else:
    severity = "High"
```

Severity Levels:

- Low
- Medium
- High

---

## Model Evaluation

The model performance was evaluated using:

- mAP (Mean Average Precision)
- Precision
- Recall

These metrics were used to measure detection quality and prediction accuracy.

---

## Visualization

The final system visualizes:

- Bounding boxes
- Class labels
- Confidence scores
- Damage counting
- Severity estimation

Example output:

```text
Detected damages count: 4

Crack → 0.91 → Medium
Pothole → 0.95 → High
```

---

## Technologies Used

The project was implemented using:

- Python
- YOLOv8
- PyTorch
- OpenCV
- Roboflow
- Ultralytics

---

## Project Structure

```text
Road-Damage-Detection/
│
├── dataset/
├── runs/
├── results/
├── train.py
├── detect.py
├── README.md
│
└── models/
```

---

## Team Members

- Magdy Ibrahim  
- Nour Ahmed  
- Nour Mahmoud  
- Wasem Boshra  
- Mohamed Maher  
- Hesham Abdel Ghany

---

## Notes

* Comments were added according to assignment requirements.

```cpp
// I used AI tools
```

AI tools were used for assistance in understanding concepts, debugging, and improving implementation.

---

## Conclusion

This project demonstrates how computer vision and object detection techniques can be applied to solve real-world infrastructure problems.

Using YOLOv8, the system successfully detects road damages, classifies them, estimates severity, and visualizes predictions using bounding boxes and confidence scores.

The project also highlights the importance of training experiments and preprocessing techniques in improving model performance and detection quality.
