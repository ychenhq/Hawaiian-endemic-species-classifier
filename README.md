
# Hawaiian Endemic Species Classifier

This project aims to classify five distinct Hawaiian endemic species using machine learning. The classifier can assist in monitoring and identifying species, contributing to conservation efforts for Hawaiian wildlife.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [Installation and Usage](#installation-and-usage)

---

## Introduction
The Hawaiian Endemic Species Classifier identifies five unique species:
- Hawaiian Goose
- Apapane
- Hawaiian Coot
- Amakihi
- Elepaio

A convolutional neural network (CNN) was used to perform image classification. By leveraging preprocessing techniques and dataset enhancements, the model achieved improved accuracy, demonstrating its utility for Hawaiian species monitoring.

---

## Dataset
The dataset was self-collected due to the lack of suitable datasets online. Using automated Google searches, approximately 900 images per species were gathered. Challenges included duplicate images, non-photographic visuals, and irrelevant content.

### Dataset Statistics
- Initial dataset size: 4,500 images
- Final dataset size after preprocessing: ~1,864 images

---

## Preprocessing
Steps taken to enhance dataset quality:
1. **Duplicate Removal**: Eliminated duplicate images using `imagehash`.
2. **Content Filtering**: Removed images unrelated to target species.
3. **Background Removal**: Applied `deeplabv3_resnet101` to eliminate backgrounds, retaining only the species.

---

## Model Architecture
The model uses a modified VGG19 architecture up to the `conv4_1` layer as the encoder. Key settings include:
- **Batch Size**: 64
- **Epochs**: 100
- **Learning Rate**: 0.001
- **Activation Function**: ReLU
- **Loss Function**: Cross-entropy

---

## Results
| Dataset                        | Accuracy  |
|--------------------------------|-----------|
| Original Dataset               | 37.89%    |
| Background-Removed Dataset     | 97.66%    |

#### Observations:
- Background removal significantly improved performance.
- Mispredictions primarily occurred between species with similar patterns or colors (e.g., Hawaiian Goose and Elepaio).

---

## Limitations
1. **Dependency on Background Removal**: Errors in background removal may impact predictions.
2. **Loss of Environmental Context**: Backgrounds can contain valuable patterns for classification.
3. **Limited Night Images**: Few night-time images in the dataset limit robustness under varying lighting conditions.

---

## Future Work
1. **Dataset Enhancements**:
   - Incorporate text detection to filter out watermarked images.
   - Apply data augmentation to increase dataset diversity.
2. **Model Improvements**:
   - Extend to more Hawaiian endemic species.
   - Explore style detection for artistic representations of species.
3. **Applications**:
   - Develop a mobile app for real-time species recognition.
   - Deploy for live monitoring using sensors and cameras.

---

## Installation and Usage

### Requirements
- Python 3.8+
- TensorFlow 2.12.0
- fastbook
- imagehash
- CUDA 11.8

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ychenhq/Hawaiian-endemic-species-classifier.git
   ```
---

### Contact
For further inquiries, feel free to contact the project authors:
- Yu-zhen Chen: ychenhq@connect.ust.hk
- Frederic Michel Ortega: fmortega@connect.ust.hk
