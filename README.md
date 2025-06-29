# 🛰️ DOTA: A Large-scale Dataset for Object Detection in Aerial Images

<br>
This repository provides a baseline implementation for object detection using the DOTA dataset — a large-scale benchmark for detecting objects in high-resolution aerial images.
It contains a diverse set of aerial images with various object categories, making it a valuable resource for researchers and practitioners in the field of computer vision.
<br>
<br>

![DOTA Logo](https://datasetninja.com/github/dataset-ninja/dota/main/visualizations/poster.png?width=800)

---

## 🔗 Links

- 📄 Paper: [arXiv:1711.10398](https://arxiv.org/abs/1711.10398)
- 🌐 Dataset Website: [https://captain-whu.github.io/DOTA/dataset.html](https://captain-whu.github.io/DOTA/dataset.html)
- 💾 Download Dataset: [DOTA Downloads](https://captain-whu.github.io/DOTA/dataset.html#download)
- 📓 Colab/Notebook: `notebooks/dota_baseline.ipynb`

---

## 🗂️ Dataset Overview

- **Name**: DOTA (Dataset for Object deTection in Aerial images)
- **Source**: Remote sensing images from multiple sensors and platforms (satellites, drones, etc.)
- **Content**:
  - 2,806 aerial images
  - Over 188,000 annotated object instances
  - 15 object categories (e.g., plane, ship, bridge, vehicle, etc.)
  - Varying object orientations and scales
- **Images**: 2,806 aerial images from satellites, drones, and surveillance aircraft
- **Annotations**:
  - Over 188,000 objects
  - 15 categories including plane, ship, bridge, small vehicle, large vehicle, etc.
  - Supports both *oriented bounding boxes (OBB)* and *horizontal bounding boxes (HBB)*
- **Resolution**: 800×800 to 4000×4000 pixels per image
- **Format**: VOC XML and custom `.txt` format; COCO JSON conversion supported

---

## 🧩 Baseline Model

This repository provides a basic object detection pipeline based on Faster R-CNN:

- **Model**: Faster R-CNN (backbone: ResNet‑50)
- **Backbone**: ResNet-50
- **Framework**: PyTorch + Detectron2
- **Input**: Cropped tiles of high-res aerial images
- **Output**: Bounding boxes (OBB/HBB), class, and confidence score

You can switch between different detection models (Faster R-CNN, RetinaNet, etc.) via config files.

---

## 🚀 Quickstart

```bash
# Install dependencies
pip install -r requirements.txt

# Train the baseline detector
python train.py --config configs/dota_baseline.yaml

# Evaluate on validation/test set
python evaluate.py --config configs/dota_baseline.yaml
