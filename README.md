
# Faster R-CNN for Fabric Defect Detection  

## 📌 Project Overview  
This project implements a **custom Faster R-CNN** object detection model in **PyTorch** to detect **fabric defects** (holes, stains, irregularities, etc.) using a dataset exported from **Roboflow** in **COCO format**.  

Unlike prebuilt libraries, this implementation builds the pipeline **from scratch**, including:  
- **Backbone (ResNet50 C4)** for feature extraction  
- **Region Proposal Network (RPN)** for candidate object regions  
- **RoI Align & ROI Heads** for classification and bounding box regression  
- **Training & Loss functions** for both RPN and ROI stages  

The goal is to provide a **transparent, modular, and educational Faster R-CNN implementation** that can be extended to other defect detection or industrial quality inspection tasks.  

---

## 📂 Dataset  
- Source: [Roboflow – Fabric Defect Detector](https://roboflow.com)  
- Format: **COCO JSON** with bounding box annotations  
- Classes: `background`, `defect`  

The dataset is automatically downloaded in the notebook via the Roboflow API.  

---

## ⚙️ Installation  

Clone the repo and install dependencies:  

```bash
git clone https://github.com/yourusername/fabric-defect-fasterrcnn.git
cd fabric-defect-fasterrcnn

pip install -r requirements.txt





