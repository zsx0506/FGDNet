# FGDNet: Frequency-Domain Guided Degradation-Aware Network for Object Detection in Adverse Weather


## 📖 Introduction

In adverse environments such as haze and low illumination, object detection is prone to missed detections and localization errors due to spectral distortions and spatial aliasing induced by physical degradations. Existing detection methods primarily rely on spatial-domain representations, making it difficult to effectively disentangle target structures from environmental noise in highly mixed signals.

To address this issue, we propose **FGDNet (Frequency-Domain Guided Degradation-Aware Network)**, a robust object detection network that leverages the complementary advantages of frequency-domain global information and spatial geometric priors. While maintaining a lightweight design (only 13 million parameters), the model achieves 78.5% mAP on the RTTS dataset.

## ✨ Key Contributions

This model systematically enhances the robustness and discriminability of object features in complex imaging conditions through three core modules:

* **Frequency-Selective Interaction Module (FSIM)**: Characterizes degradation components by explicitly analyzing global structural correlations across regions (based on long-range frequency-domain modeling). It introduces a frequency selection mechanism to mitigate noise caused by degradation, thereby enhancing the perception of global spectral information.
* **Frequency-Guided Feature Enhancement Module (FGFE)**: Combines spatial-frequency feature fusion with spectral reconstruction to perform cross-domain feature calibration via learnable frequency modulation. This module collaboratively enhances local textures and global structural representations, addressing high-frequency information loss caused by degradation.
* **Aggregated Channel-Spatial Prior Module (ACSPM)**: Introduces a hierarchical asymmetric geometric prior structure to re-weight fused features. It adaptively strengthens weak-response targets and suppresses complex background interference, effectively reducing feature instability and structural blurring.

## 📊 Datasets

We have extensively validated the model on three challenging real-world benchmark datasets:

* **RTTS Dataset**: A real-world foggy object detection dataset containing 4,322 annotated images.
* **FDD Dataset**: Contains 101 real-world foggy images, primarily used to evaluate the cross-dataset generalization capabilities of the model.
* **ExDark Dataset**: A low-light object detection benchmark containing 7,363 images.

## 🏆 Performance

Experiments demonstrate that FGDNet consistently outperforms state-of-the-art (SOTA) methods in terms of robustness, generalization, and detection accuracy:

* **Foggy Scenes (RTTS)**: Compared to YOLO11, FGDNet improves mAP50 by 2.3% and mAP50-90 by 1.3%; compared to YOLOv12, mAP50 is increased by 4.6%.
* **Cross-Scene Generalization (FDD)**: With only 13M parameters, FGDNet's mAP50 outperforms YOLO11 by 5.5% and YOLOv10 by 6.3%.
* **Low-Light Scenes (ExDark)**: FGDNet achieves state-of-the-art performance with 62.2% mAP50 and 39.1% mAP50-90.

*(Note: As this model is implemented based on the PyTorch and Ultralytics YOLO framework, please refer to the official source code for specific environment configuration and execution instructions.)*
