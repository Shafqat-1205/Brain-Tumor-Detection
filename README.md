# Comparative Interpretability of CNN Architectures for Multi-Class Brain Tumor MRI Classification

![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Captum](https://img.shields.io/badge/Explainable_AI-Captum-blue?style=for-the-badge)

## 📌 Abstract & Clinical Objective
Deep learning models achieve high accuracy in medical image classification, but their "black-box" nature remains a significant barrier to clinical adoption. In neuro-oncology, a model must not only identify a tumor but also provide spatial justification for its prediction to ensure clinical trust and safety.

This project evaluates the performance and **interpretability** of four prevalent Convolutional Neural Network (CNN) architectures in classifying multi-class brain tumors from MRI scans. Using PyTorch and Captum, the project conducts a comparative ablation study of feature attributions using **Grad-CAM** and **Integrated Gradients** to determine which architecture provides the most localized, trustworthy, and clinically relevant predictions.

## 📊 Dataset
The dataset consists of approximately 7,000 clinically categorized MRI images across four classes:
* **Glioma**
* **Meningioma**
* **Pituitary Tumor**
* **No Tumor**

*Data Source: [Brain Tumor MRI Dataset (Kaggle)](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)*

## 🔬 Methodology
1. **Model Benchmarking:** Four pre-trained architectures (ResNet-50, DenseNet-121, EfficientNet-B0, MobileNet-V2) were fine-tuned using transfer learning.
2. **Preprocessing Pipeline:** Implementation of robust data augmentation (dynamic cropping, rotation, normalization) to prevent overfitting on the limited medical dataset.
3. **Interpretability Analysis (XAI):** * **Grad-CAM:** Utilized for baseline spatial visualization of the final convolutional layers.
   * **Integrated Gradients:** Utilized for mathematically rigorous pixel-level attribution, ensuring completeness and overcoming the vanishing gradient problem often seen in deep CNNs.

## 📈 Key Findings
* **ResNet-50 — Accuracy: 93.69%:**, Demonstrated peak clinical reliability. The model's highly connected architecture generated Integrated Gradient heatmaps with tight encapsulation of the pathological mass.

