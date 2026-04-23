# DeepLearning_ProjectA_Group8
A Deep Learning solution for automated brain tumor detection in MRI scans using Convolutional Neural Networks (CNNs). Built for high-accuracy medical image classification.


🚀 How to Run:
Unzip the CS464_Group8_BrainTumorClassification_1.ipynb.zip folder.

Open the .ipynb file in Google Colab or Jupyter Notebook.

Ensure all dependencies (timm, pytorch-grad-cam) are installed.

📌 Project Overview:
This project implements a deep learning pipeline to classify brain tumor MRI scans into four categories: Glioma, Meningioma, Pituitary, and No Tumor. By leveraging Transfer Learning and explainable AI techniques, the model achieves high diagnostic accuracy while providing visual justifications for its predictions.

Note on Project Files: Due to the high-resolution visualization outputs (Grad-CAM and Batch Augmentations), the .ipynb file exceeds GitHub's preview limits. The full notebook with all executed cell outputs is available in the  CS464_Group8_BrainTumorClassification_1.ipynb.zip folder in this repository.

📊 Key Results:
Our final model, based on the EfficientNet-B0 architecture, significantly outperformed all baseline measures.

Model	Accuracy	Macro F1-Score
Majority-Class Predictor	25.0%	0.10
Simple CNN (From Scratch)	72.4%	0.72
EfficientNet-B0 (Ours)	91.6%	0.92
Per-Class Performance

The model demonstrated exceptional reliability in identifying healthy scans (99.7% Recall) and distinguishing pituitary tumors (99.4% Precision). The balanced Macro F1-score of 0.916 confirms that the network performs consistently across all pathological classes.

🛠 Methodology:
1. Data Engineering & Augmentation

To ensure clinical reliability, we implemented a stochastic augmentation strategy (rotations, flips, and affine shears). This acts as a critical form of regularization, forcing the network to learn generalized pathological features rather than memorizing specific training samples.

2. Two-Phase Training

We employed a surgical training strategy:

Phase 1: The backbone was frozen to stabilize the custom classification head.

Phase 2: The entire model was unfrozen for fine-tuning at a lower learning rate (3×10 −5), allowing the deep filters to adapt to subtle MRI textures.

🔍 Explainability (Grad-CAM)
To bridge the gap between "black-box" AI and clinical trust, we used Grad-CAM to generate heatmaps. These visualizations confirm that the model focuses on the actual tumor masses within the cranial cavity to make its decisions, rather than relying on imaging artifacts or background noise.


