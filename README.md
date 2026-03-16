## MFENet

A lightweight and robust object detection network designed for severe foggy weather, achieving high precision with low complexity.

markdown
# Multi-Scale Feature Enhancement Network for Object Detection in Severe Foggy Weather

## 📖 Introduction

This repository contains the official PyTorch implementation of the paper: **"Multi-Scale Feature Enhancement Network for Object Detection in Severe Foggy Weather"**.

**MFENet** is designed to address the challenges of low contrast and blurred structures in foggy traffic environments. 

## 🔨 Installation

Environment Requirements
* Python 3.8+
* PyTorch 1.10+
* CUDA 11.0+

Setup

Create a virtual environment
* conda create -n mfenet python=3.9
* conda activate mfenet

Install dependencies
pip install -r requirements.txt

## 📂 Data Preparation

We use **VOC-fog** (synthetic),  **RTTS** and **FDD** (real-world) datasets. Please organize your datasets as follows:

```text
├── datasets
│   ├── VOC_Fog
│   │   ├── images
│   │   │   ├── train
│   │   │   └── val
│   │   │   └── test
│   │   └── labels
│   │   │   ├── train
│   │   │   └── val
│   │   │   └── test
│   ├── RTTS
│   │   ├── images
│   │   └── labels
│   ├── FDD
│   │   ├── images
│   │   └── labels
```

## 🚀 Usage

### Training

To train MFENet on the RTTS dataset (Batch size 16, 300 epochs):

```bash
python Mytrain.py --data data/RTTS.yaml --cfg models/MFENet.yaml --batch-size 16 --epochs 300 --lr 0.01

```

### Testing / Evaluation

To evaluate the model on the test set:

```bash
python Mytest.py --weights runs/train/exp/weights/best.pt --data data/RTTS.yaml --img 640

```

## 📊 Results

### Performance on RTTS and FDD (Real-world Fog)

Comparison with SOTA methods (Table 3 in the paper):

| Method | Publication | Year | Type | RTTS Precision↑ | RTTS mAP(%)↑ | FDD Precision↑ | FDD mAP(%)↑ | FPS↑ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Cascade R-CNN | CVPR | 2018 | General | 75.36 | 67.25 | 48.42 | 30.06 | 46 |
| CenterNet | CVPR | 2019 | General | 68.51 | 56.74 | 37.45 | 23.77 | 47 |
| YOLO11 | - | 2024 | General | 76.89 | 74.45 | 50.46 | 34.78 | 126 |
| RT-DETR | CVPR | 2024 | General | 76.63 | 74.18 | 51.26 | 35.41 | 43 |
| DEIM | CVPR | 2025 | General | 77.96 | 75.33 | 50.31 | 35.76 | 87 |
| MASFNet | TGRS | 2025 | Multi-task | 77.82 | 73.68 | 51.19 | 30.95 | **128** |
| YOLO26 | - | 2026 | General | 78.89 | 73.50 | 48.07 | 35.23 | 92 |
| **MFENet (Ours)**| - | - | - | **79.23**| **75.89**| **52.78**| **36.38**| 117 |

> *Note: **Bold** indicates the best result. *

### Visualization

*Qualitative detection results on the RTTS dataset. MFENet demonstrates superior ability to detect occluded pedestrians and vehicles.*

## 🔗 Citation

If you find this work helpful, please consider citing:

```bibtex


```

## 🤝 Acknowledgements

This work was supported by the National Natural Science Foundation of China (Grants 61971444, 62403066, etc.) and the Fundamental Research Funds for the Central Universities.
