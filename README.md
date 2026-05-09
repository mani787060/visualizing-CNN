# Visualizing CNN Architecture (VGG-16)
[![Computer Vision](https://img.shields.io/badge/Domain-Computer%20Vision-blue)](https://en.wikipedia.org/wiki/Computer_vision)
[![Model](https://img.shields.io/badge/Model-VGG--16-red)](https://arxiv.org/abs/1409.1556)
[![Python](https://img.shields.io/badge/Python-3.9%2B-green)](https://www.python.org/)

## 🏗️ Project Overview
Why do Convolutional Neural Networks (CNNs) work? This project provides a visual answer. By using the **VGG-16** architecture, this notebook extracts the intermediate "activations" (feature maps) to see exactly what the model "sees" at different depths. 

By analyzing layers **2, 5, 9, 13, and 17**, we can observe the hierarchical decomposition of an image—starting from simple pixel gradients and evolving into complex structural components.

---

## 🛠️ Key Technical Implementations

### 1. Hierarchical Feature Extraction
We specifically target five distinct layers to observe the transformation of data:
*   **Layer 2:** Early-stage edge and color blob detection.
*   **Layer 5:** Combination of edges into basic shapes and textures.
*   **Layer 9:** Mid-level feature detection (patterns, grids, circles).
*   **Layer 13 & 17:** High-level semantic features where the model begins to recognize complex object parts (eyes, wheels, textures specific to a class).

### 2. VGG-16 Interpretation
* **Pre-trained Weights:** Leveraging `ImageNet` weights to ensure the filters have already learned meaningful spatial hierarchies.
* **Functional API:** Using the Keras/TensorFlow Functional API to create a multi-output model that returns the activations of specific internal layers.

### 3. Activation Map Visualization
* **Feature Inversion:** Converting high-dimensional tensors into 2D heatmaps.
* **Filter Diversity:** Visualizing multiple channels per layer to show how different filters react to the same input image (e.g., one filter looking for vertical lines, another for horizontal ones).

---

## 💻 Tech Stack
* **Language:** Python 3.9+
* **Deep Learning:** TensorFlow / Keras
* **Visualization:** Matplotlib, OpenCV
* **Environment:** Jupyter Notebook

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/visualizing-cnn-feature-maps-vgg16.git](https://github.com/your-username/visualizing-cnn-feature-maps-vgg16.git)

2. **Install Dependencies:**
   ```bash
   pip install tensorflow matplotlib opencv-python

3. **Run the Analysis:**
   Open `visualizing-cnn-architecture.ipynb` and provide any image to see the VGG-16 internal breakdown.
   
