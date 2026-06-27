# ANN-BLOOD-CELL-CLASSIFICATION-PROJECT
ANN-AneRBC PROJECT
What is this project?
This project uses Deep Learning to automatically classify blood cell images into 8 different types. We trained 6 AI models and compared their performance. We also used Explainable AI (Grad-CAM) to see which part of the image the model looks at when making a decision.
Dataset:
Total Images: 17,092
Classes: 8 types of blood cells
Split: 70% Training | 15% Validation | 15% Testing
Class
Images
Basophil
1,218
Eosinophil
3,117
Erythroblast
1,551
IG
2,895
Lymphocyte
1,214
Monocyte
1,420
Neutrophil
3,329
Platelet
2,348
Data Preprocessing:
Resized all images to 224×224
Normalised pixel values
Applied random flip, rotation, colour jitter for augmentation
Used Weighted Random Sampler to handle class imbalance
Removed corrupted images (0 found)
Models:
Custom CNNs (built from scratch)
Model
Layers
Parameters
CNN3
3
1.1M
CNN4
4
3.3M
CNN5
5
3.9M
Each layer uses: Conv → BatchNorm → ReLU → MaxPool → Dropout
Transfer Learning (pretrained on ImageNet)
Model
Frozen
Trainable
MobileNetV2
Early layers
Last 3 blocks + head
SqueezeNet
Early layers
Last fire modules + head
ResNet18
Layer 1-3
Layer 4 + FC head
Results:
Model
Accuracy
F1 Score
CNN3
94.07%
93.88%
CNN4
94.70%
94.27%
CNN5
97.50%
97.33%
MobileNetV2
96.92%
96.94%
SqueezeNet
97.66%
97.61%
ResNet18
98.52%
98.46%
Best Models:
Best Overall → ResNet18 (F1 = 98.46%)
Best Custom CNN → CNN5 (F1 = 97.33%)
Explainable AI — Grad-CAM:
Grad-CAM creates a heatmap showing which part of the image the model focused on.
CNN5 focuses tightly on the cell nucleus
ResNet18 looks at the whole cell area — this helps it perform better
How to Run:
Upload archive.zip to Google Drive
Open notebook in Google Colab
Enable GPU: Runtime → Change runtime type → T4 GPU
Run all cells
Total training time: approximately 60–80 minutes
Technologies Used:
Python, PyTorch, TorchVision, NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, Pillow, Google Colab
Git Commits:
Code
Submitted for ANN & Deep Learning Coursework 
