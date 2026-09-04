
# Road Damage Detection using YOLO11 and PyTorch

## Overview

This project focuses on detecting and classifying road damage using a YOLO11 object detection model. The model was fine-tuned using a road damage dataset and evaluated on an unseen test set.

## Problem Statement

Road damage such as cracks and potholes can affect road safety and maintenance. Manual inspection is time-consuming, so computer vision can be used to automatically detect and classify road damage from images.

## Technologies Used

- Python
- PyTorch
- YOLO11
- Ultralytics
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Google Colab

## Dataset

A Roboflow version of the Road Damage Detection dataset was used.

The dataset contains 10 road damage categories:

- D00
- D01
- D0w0
- D10
- D11
- D20
- D40
- D43
- D44
- D50

The dataset was used in YOLO11 format.

## Methodology

1. Loaded a pretrained YOLO11n model.
2. Prepared the road damage dataset in YOLO format.
3. Fine-tuned the model on the custom dataset.
4. Evaluated the trained model on the test set.
5. Conducted a second experiment using additional data augmentation.
6. Compared both experiments using mAP metrics.
7. Analysed class-wise performance and confusion matrices.

## Experiments

### Experiment 1 — Baseline

- Model: YOLO11n
- Epochs: 25
- Image size: 640
- Batch size: 16

Test results:

- mAP@0.5: 44.1%
- mAP@0.5:0.95: 23.1%

### Experiment 2 — Data Augmentation

- Model: YOLO11n
- Epochs: 50
- Image size: 640
- Batch size: 16
- Augmentations included translation, scaling, flipping and mosaic augmentation.

Test results:

- mAP@0.5: 45.6%
- mAP@0.5:0.95: 22.1%

## Results Comparison

| Experiment | Epochs | mAP@0.5 | mAP@0.5:0.95 |
|------------|--------|---------|--------------|
| Baseline | 25 | 44.1% | 23.1% |
| Augmentation | 50 | 45.6% | 22.1% |

The augmentation experiment slightly improved mAP@0.5, but mAP@0.5:0.95 decreased. Therefore, the improvement was not consistent across different IoU thresholds.

## Error Analysis

The confusion matrix showed stronger performance for some damage categories, while several minority or visually subtle classes had higher false-negative rates.

This indicates that class imbalance and visual similarity between damage categories are important challenges.

## Limitations

- Some damage categories have relatively few examples.
- Performance varies significantly between classes.
- The current model is intended as an experimental computer vision project rather than a production-ready system.

## Future Improvements

- Address class imbalance using better sampling strategies.
- Perform systematic hyperparameter tuning.
- Experiment with larger YOLO models.
- Investigate higher-resolution training.
- Perform more detailed error analysis.
- Optimize the model for deployment using ONNX or TensorRT.

## Project Structure

```text
road-damage-detection-yolo11/
├── README.md
├── requirements.txt
└── Road_Damage_Detection_YOLO11n.ipynb
