# 🛡️ NU-Traditional-Uniform-Detection

> **A low-latency YOLOv11 computer vision pipeline designed for real-time institutional uniform compliance and edge-inference.**

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Framework](https://img.shields.io/badge/framework-YOLOv11-green.svg)]()
[![Privacy](https://img.shields.io/badge/Privacy-Compliant-brightgreen.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🏛️ System Architecture
This repository contains the real-time inference engine developed for institutional uniform compliance. Deployed initially as a live demonstration system, it utilizes YOLOv11 for high-speed optical detection of localized uniform standards. 

**Privacy by Design:** This pipeline operates strictly on edge-inference. No facial data or raw frames are stored during execution to ensure compliance with the **Data Privacy Act of 2012 (Republic Act No. 10173)**.

## ⚙️ Hardware Modularity
The inference script (`run.py`) is engineered to handle multiple input streams dynamically:
* Standard USB Webcams
* Pre-recorded Video / Image Folders
* **Edge Deployment:** Native support for Raspberry Pi camera modules (`picamera2`).

## 🛠️ Quick Start & Reproducibility
### 1. Environment Setup
Clone the repository and install the strict dependencies.
```bash
git clone https://github.com/matlih/NU-Traditional-Uniform-Detection.git
cd NU-Traditional-Uniform-Detection
pip install -r requirements.txt
```

### 2. Live Inference Execution
Run the detection pipeline using a standard USB webcam. Note: Ensure your trained weights file (best.pt) is placed in the weights/ directory.
```bash
python src/run.py --model weights/best.pt --source usb0 --thresh 0.5
# Note for Edge Deployment: If running inference directly on a Raspberry Pi using a native Pi Camera (--source picamera0), ensure the picamera2 library is installed on your local system environment. Standard USB webcams do not require this module.
```

### 3. Training Metrics
*This model was trained in a cloud GPU environment (Google Colab, NVIDIA T4).*
#### **Proprietary Data Engineering:** The dataset utilized for this pipeline was entirely custom-built.
* All training and validation imagery was physically acquired, curated, and manually annotated using [Anaconda](https://www.anaconda.com/) to ensure high-fidelity localization of the traditional uniform. 
Due to PII (Personally Identifiable Information) constraints regarding student identities, raw validation batches are not published. 
#### Automated MLOps metrics:

* Mean Average Precision (mAP@50): 99.5%
* Precision: 99.8%
* Recall: 100%
____________________________________

Developed by Matlih
