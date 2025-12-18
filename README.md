# Recursion Cellular Image Classification (6-Channel Microscopy)

## Overview
This project implements a deep learning pipeline to classify **6-channel fluorescent microscopy images**
from the **Recursion Cellular Image Classification** dataset. The goal is to identify one of **1,108 siRNA
genetic perturbations** based solely on cellular morphology.

## Dataset
- Cell line used: **HUVEC**
- Image size: **512×512**
- Channels: **6 (fluorescent microscopy)**
- Classes: **1,108**
- Dataset source: Recursion Pharmaceuticals (Kaggle)

⚠️ Dataset not included due to size constraints.

## Model
- Backbone: **EfficientNet-B3 (ImageNet pre-trained)**
- Input modification: First convolution layer adapted for **6 channels**
- Head: Dropout (0.3) → Linear (1108)
- Optimizer: AdamW
- Scheduler: Cosine Annealing

## Training Setup
- Batch size: 32
- Epochs: 40
- GPU: Tesla T4
- Training time: ~6 hours

## Results
| Metric | Value |
|------|------|
| Training Accuracy | 100% |
| Validation Accuracy | 49.47% |
| Random Baseline | 0.09% |

## Observations
- Severe overfitting due to limited cell line usage
- Strong feature learning capability
- Misclassification mainly between morphologically similar perturbations

## Future Improvements
- Data augmentation
- Use all cell types
- Include Site-2 images
- Stronger regularization

## Contributors
- Apoorv
- Sahil
- Tushar
- Priyanshu
