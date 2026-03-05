# 🌊 Satellite-Based Flood Detection using Deep Learning & SAR Imagery

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-orange?style=flat-square&logo=pytorch)
![SAR](https://img.shields.io/badge/Sentinel--1-SAR%20Imagery-green?style=flat-square)
![IEEE](https://img.shields.io/badge/IEEE-Published%20Research-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

> **IEEE Accepted Research Paper** — Presenting at IEEE Conference, April 2026  
> *Satellite-Based Flood Detection Using Deep Learning and Probabilistic Mapping: A Case Study of Ganga Floodplain*

A deep learning framework for automated flood detection and severity mapping from Sentinel-1 SAR satellite imagery using a U-Net based convolutional neural network. The model generates spatial flood probability maps and classifies affected regions into severity zones — designed as a decision-support tool for disaster response.

---

## 📌 Overview

Floods are among the most destructive natural disasters globally. Accurate and timely flood mapping is critical for disaster response — yet traditional methods relying on field surveys, hydrological models, and optical satellite imagery fail under real-time, cloud-covered monsoon conditions.

**Synthetic Aperture Radar (SAR)** imagery solves this — operating in all weather conditions, day and night, even during the heaviest monsoon cloud cover.

This project proposes an end-to-end deep learning pipeline that:
- Automatically detects flood events from Sentinel-1 SAR imagery
- Generates interpretable spatial flood **probability maps**
- Classifies affected regions into **Low / Medium / High severity zones**
- Demonstrates real-world application on the **Ganga floodplain, India**

---

## 📊 Model Performance

| Metric | Score |
|--------|-------|
| Accuracy | 0.683 |
| Precision | 0.700 |
| **Recall** | **0.833** |
| F1 Score | 0.755 |

> **Why recall matters here:** In flood detection, missing a flood event (false negative) has far more severe consequences than a false alarm. The model is intentionally optimized for high recall — ensuring the majority of real flood events are detected.

---

## 🚀 Key Features

- Flood detection using **Sentinel-1 dual-polarization SAR** (VV + VH)
- **U-Net CNN architecture** with encoder-decoder and skip connections
- Generates **spatial flood probability maps** per pixel
- **Severity zoning** — classifies regions into Low / Medium / High risk
- Event-level flood classification via mean pooling + threshold decision rule
- Applied to **Ganga floodplain riverine flood events**
- Designed as a **decision-support tool** for disaster monitoring systems

---

## 🛰 Dataset

This project uses the **[SEN12-FLOOD dataset](https://ieee-dataport.org/open-access/sen12-flood-sar-and-multispectral-dataset-flood-detection)** — a multi-modal satellite dataset containing Sentinel-1 SAR and Sentinel-2 optical imagery across multiple flood events and geographic regions.

**This implementation uses Sentinel-1 SAR only** due to its all-weather operational reliability during flood events.

| Property | Detail |
|----------|--------|
| Sensor | Sentinel-1 SAR |
| Polarizations | VV + VH (dual-polarization) |
| Labels | Event-level (Flood / Non-flood) |
| Split | Train / Validation / Test |
| Case Study | Ganga Floodplain, India |

---

## 🧠 Methodology

```
Sentinel-1 SAR Images
        ↓
  Preprocessing
  (Normalize + Center Crop)
        ↓
  Stack VV + VH Channels
        ↓
   U-Net CNN Model
        ↓
  Sigmoid Activation
        ↓
Flood Probability Map (per pixel)
        ↓
  Mean Pooling → Event Classification
        ↓
  Threshold → Severity Zones
  (Low / Medium / High)
```

### Model Architecture — U-Net

- **Encoder** — convolutional blocks extract spatial backscatter features
- **Skip connections** — preserve fine-grained spatial information
- **Decoder** — reconstructs spatial flood regions at full resolution
- **Sigmoid output** — each pixel value = flood probability at that location

```
Input:  Sentinel-1 SAR Image   →  Shape: (4, 512, 512)
Output: Flood Probability Map  →  Shape: (1, 512, 512)
```

---

## 💻 Installation

```bash
git clone https://github.com/Conceal34/Flood-Detection-Severity-Mapping.git
cd Flood-Detection-Severity-Mapping
```

---

## ▶ Running the Project

every '.ipynb' can be found in the notebooks folder

**1. Prepare the dataset**
```bash
# Run dataset_builder.ipynb
```

**2. Train the model**
```bash
# Run model_training.ipynb
```

**3. Generate flood probability maps**
```bash
# Run inference_and_prob_maps.ipynb
```

**4. Launch interactive demo**
```bash
python demo.ipynb
```
---

## 🗺 Applications

- Disaster response and emergency management systems
- Real-time flood monitoring platforms
- Climate impact and flood risk assessment
- Government flood management agencies
- Satellite-based environmental monitoring

---

## 🔬 Research Context

This implementation is part of an **IEEE accepted research paper**:

> Vinner, Vandana Sharma, Prakash Velusamy. *"Satellite-Based Flood Detection Using Deep Learning and Probabilistic Mapping: A Case Study of Ganga Floodplain."*  
> IEEE Conference. Accepted February 2026. Presenting April 2026.

---

## ⭐ Future Work

- Integration of **Sentinel-2 optical imagery** for multi-modal fusion
- **GIS-based severity mapping** incorporating elevation, land use, and distance to rivers
- Training on larger, more geographically diverse flood datasets
- Real-time flood monitoring pipeline deployment
- Socio-economic impact layer integration for severity assessment

---

## 👨‍💻 Author

**Vinner** — Full-Stack Engineer · IEEE Published Researcher  
MCA, Christ University, Delhi NCR  

[![GitHub](https://img.shields.io/badge/GitHub-Conceal34-black?style=flat-square&logo=github)](https://github.com/Conceal34)
[![Email](https://img.shields.io/badge/Email-vinnerhooda@gmail.com-red?style=flat-square&logo=gmail)](mailto:vinnerhooda@gmail.com)
