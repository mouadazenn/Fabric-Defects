Fabric Defect Detection with Faster R-CNN


📌 Project Description

This project implements a custom Faster R-CNN from scratch in PyTorch to detect fabric defects.
Instead of using a prebuilt model from torchvision, all key components are written manually:

Backbone (ResNet50 C4 features, stride=16)

Region Proposal Network (RPN) with custom anchor generator

RoI Align

RoI Heads (two fully-connected layers, classification + box regression)

Loss functions (classification + Smooth L1 regression for both RPN and RoI)

The model is trained on a COCO-style dataset exported from Roboflow, containing labeled images of fabrics with different types of defects.

Dataset

Source: Roboflow Universe

Format: COCO JSON (annotations + bounding boxes)

Classes: background (0) + fabric defects (1..N)

Train/Val/Test splits are provided.

⚙️ Installation

Clone this repository and install dependencies:

git clone https://github.com/your-username/fabric-defect-fasterrcnn.git
cd fabric-defect-fasterrcnn
pip install -r requirements.txt

Requirements (main):

Python 3.9+

PyTorch 2.0+

Torchvision

Matplotlib

Pillow

Roboflow (for dataset download)

🚀 Training

To train the model on your dataset:

python train.py


Or run the provided Jupyter notebook step by step.

During training, the model optimizes:

RPN losses (objectness classification + bbox regression)

ROI losses (classification + bbox regression)

🧪 Evaluation

To run inference on test images:

model.eval()
with torch.no_grad():
    detections = model(images)  # list of detections per image


Each detection returns:

[x1, y1, x2, y2, score, label]

📊 Results & Visualization

Bounding boxes can be visualized either from:

Ground-truth annotations (_annotations.coco.json)

Predicted detections after inference.

Example output:

🛠 Tools & Frameworks

PyTorch (model training)

Torchvision (ops: NMS, RoI Align)

Roboflow (dataset management)

Matplotlib (visualization)
