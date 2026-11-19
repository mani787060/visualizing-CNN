# Visualizing CNN Architecture (VGG-16)

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Computer Vision](https://img.shields.io/badge/Domain-Computer%20Vision-green)](https://en.wikipedia.org/wiki/Computer_vision)
[![Deep Learning](https://img.shields.io/badge/Domain-Deep%20Learning-blue)](https://en.wikipedia.org/wiki/Deep_learning)
[![TensorFlow](https://img.shields.io/badge/Framework-TensorFlow-orange)](https://www.tensorflow.org/)
[![Model](https://img.shields.io/badge/Model-VGG16-red)](https://arxiv.org/abs/1409.1556)
[![Jupyter](https://img.shields.io/badge/Environment-Jupyter%20Notebook-orange)](https://jupyter.org/)

A practical exploration of **Convolutional Neural Network (CNN) interpretability** using the pretrained VGG16 architecture. This project visualizes intermediate layer activations and feature maps to understand how a CNN transforms an input image into increasingly complex visual representations.

**Repository:** https://github.com/mani787060/visualizing-CNN

---

## Project Overview

Convolutional Neural Networks are widely used in computer vision tasks such as image classification, object detection, and image recognition. However, their internal operations can often feel like a black box.

This project explores what happens inside a CNN by using **VGG16**, a deep convolutional neural network pretrained on the ImageNet dataset.

Instead of looking only at the final prediction, the notebook extracts and visualizes intermediate activations from selected layers:

- Layer 2
- Layer 5
- Layer 9
- Layer 13
- Layer 17

These visualizations help us observe how image representations change as information passes through the network.

The general idea is to understand the progression from lower-level visual patterns, such as edges and textures, toward more complex feature representations.

---

## Key Concepts and Implementations

### 1. Understanding CNN Feature Extraction

CNNs process images through a sequence of convolutional and pooling operations.

During this process, convolutional filters respond to different patterns in the input image. Their outputs are represented as **feature maps**, also known as activation maps.

A simplified representation of the process:

```text
Input Image
     |
     v
Convolutional Layers
     |
     v
Feature Maps
     |
     v
Pooling Operations
     |
     v
Deeper Convolutional Layers
     |
     v
Higher-Level Representations
     |
     v
Final Network Output
```

By examining intermediate feature maps, we can better understand how visual information is transformed throughout the network.

### 2. VGG16 Architecture

This project uses **VGG16**, a convolutional neural network introduced by the Visual Geometry Group at the University of Oxford.

VGG16 consists of:

- 13 convolutional layers.
- 5 max-pooling layers.
- 3 fully connected layers in its original classification architecture.

The model uses small 3 × 3 convolutional filters and a sequential architecture.

The notebook uses pretrained ImageNet weights, allowing the experiment to explore learned visual representations without training the entire network from scratch.

### 3. Hierarchical Feature Visualization

The notebook examines activations from five selected VGG16 layers.

| Selected Layer | What the Visualization Helps Explore |
|---|---|
| Layer 2 | Early visual patterns, edges, and color responses |
| Layer 5 | Combinations of basic visual patterns |
| Layer 9 | More developed textures and spatial patterns |
| Layer 13 | Deeper and more complex feature responses |
| Layer 17 | Higher-level feature representations |

The exact patterns depend on the input image and the learned filters. These visualizations should be interpreted as filter responses rather than definitive object detectors.

### 4. Intermediate Activation Extraction

The Keras Functional API makes it possible to construct a model that returns outputs from selected internal layers instead of only the final prediction.

Conceptually, the workflow is:

```text
Pretrained VGG16
       |
       v
Select Intermediate Layers
       |
       v
Create Feature Extraction Model
       |
       v
Pass Input Image
       |
       v
Collect Layer Activations
       |
       v
Visualize Feature Maps
```

This provides a way to inspect the internal representations learned by a pretrained CNN.

### 5. Feature Map Visualization

The activation outputs of convolutional layers are typically multi-dimensional tensors.

Visualization converts selected channels of these tensors into two-dimensional images or heatmaps.

This makes it easier to:

- Observe which spatial regions activate strongly.
- Compare feature responses across different layers.
- Explore how visual representations change with network depth.
- Understand the role of different convolutional filters.

---

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| TensorFlow | Deep learning framework |
| Keras | Loading VGG16 and extracting activations |
| NumPy | Numerical operations |
| Matplotlib | Visualizing feature maps and activations |
| OpenCV | Image processing utilities, where used |
| Jupyter Notebook | Interactive implementation |

---

## Repository Structure

```text
visualizing-CNN/
│
├── visualizing-CNN.ipynb    # VGG16 feature-map visualization
└── README.md                # Project documentation
```

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/mani787060/visualizing-CNN.git
```

### 2. Navigate to the Project Directory

```bash
cd visualizing-CNN
```

### 3. Create a Virtual Environment (Recommended)

```bash
python -m venv .venv
```

Activate on Windows:

```bash
.venv\Scripts\activate
```

Activate on macOS/Linux:

```bash
source .venv/bin/activate
```

### 4. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install tensorflow numpy matplotlib opencv-python jupyter
```

Use a Python version supported by your installed TensorFlow release.

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
visualizing-CNN.ipynb
```

Run the notebook cells sequentially to load the pretrained model, process the input image, extract intermediate activations, and visualize the selected feature maps.

**Note:** The first model initialization may download pretrained ImageNet weights. An internet connection is generally required for this initial download.

---

## Understanding the Core Workflow

The overall experiment follows these steps:

**Step 1 — Load the pretrained model**

Load VGG16 with ImageNet weights.

**Step 2 — Prepare an input image**

Load and preprocess an image into the input format expected by VGG16.

**Step 3 — Select internal layers**

Choose the layers whose activation outputs will be inspected.

**Step 4 — Extract activations**

Pass the preprocessed image through the feature-extraction model.

**Step 5 — Visualize feature maps**

Display selected activation channels using image plots or heatmaps.

**Step 6 — Compare representations**

Observe how the feature responses differ between early and deeper layers.

---

## Why Is CNN Visualization Important?

Visualizing CNN activations helps us understand neural networks beyond their final predictions.

It can support:

- **Model interpretability:** Exploring internal feature representations.
- **Learning:** Building intuition about convolutional filters and feature extraction.
- **Debugging:** Investigating whether intermediate layers produce meaningful activation patterns.
- **Computer vision research:** Studying how representations change across network depth.

It is important to remember that activation maps are not complete explanations of a model's decision. They provide useful insight into internal responses, but should be interpreted alongside other evaluation and explainability methods.

---

## Learning Outcomes

Through this project, I explored:

- How convolutional neural networks extract visual features.
- The architecture and working principles of VGG16.
- The role of pretrained ImageNet weights.
- How to access intermediate outputs using the Keras Functional API.
- How convolutional feature maps are represented as tensors.
- How to visualize activations from different network depths.
- How CNN representations evolve from early to deeper layers.

---

## Future Improvements

Possible extensions include:

- Visualize more convolutional layers from VGG16.
- Compare activation maps across different input images.
- Visualize learned convolutional filters and their weights.
- Compare feature representations from VGG16 and ResNet50.
- Explore Grad-CAM for class-specific visual explanations.
- Save activation visualizations automatically.
- Compare how different preprocessing choices affect feature maps.

---

## References

- [VGG16 Research Paper — Very Deep Convolutional Networks for Large-Scale Image Recognition](https://arxiv.org/abs/1409.1556)
- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras VGG16 Documentation](https://keras.io/api/applications/vgg/)
- [Keras Functional API](https://keras.io/guides/functional_api/)
