# Flood Map Boundary Prediction

A deep learning project for flood map boundary prediction using image-based semantic segmentation. This project explores multiple deep learning architectures to identify and classify different flood intensity regions from flood map images.

## Project Overview

Flood maps represent the spatial extent and intensity of flooding across a geographical region. The objective of this project is to process flood map images and generate pixel-level class masks representing different flood intensity levels.

The project explores and compares the following approaches:

- Simple CNN
- Fully Convolutional Neural Network (FCNN)
- U-Net
- ResNet50
- CNN + LSTM

The models process flood map images and perform pixel-level classification for different flood intensity levels.

## Flood Classes

The generated segmentation masks contain five classes corresponding to different flood intensity levels:

| Class | Flood Intensity |
|------:|-----------------|
| 0 | Very Low |
| 1 | Low |
| 2 | Medium |
| 3 | High |
| 4 | Very High |

The masks are generated from the color-coded flood map images by assigning each pixel to the closest predefined flood-intensity color.

## Dataset

The dataset contains flood map images organized into training and testing subsets.

The dataset structure is:

flood_dataset/
- train/
- test/

The images are processed by:

1. Loading the flood map images.
2. Resizing them to 256 × 256.
3. Converting the images to RGB format.
4. Normalizing pixel values to the range [0, 1].
5. Generating corresponding segmentation masks.

The generated masks are stored separately in the masks/ directory.

## Models

### Simple CNN

A basic convolutional neural network used for pixel-level classification. It primarily captures local spatial information from the input flood maps.

### FCNN

A Fully Convolutional Neural Network using an encoder-decoder architecture. The encoder extracts spatial features while the decoder restores the spatial resolution using transposed convolution layers.

### U-Net

A U-Net architecture with encoder and decoder blocks connected through skip connections. These connections help preserve spatial information and improve the localization of flood boundaries.

### ResNet50

A ResNet50-based approach is explored for flood-map image processing and prediction.

### CNN + LSTM

A CNN + LSTM architecture is explored to combine spatial feature extraction from CNN layers with sequential modeling using LSTM layers.

## Model Training

The segmentation models use:

- Optimizer: Adam
- Loss Function: Sparse Categorical Cross-Entropy
- Evaluation Metric: Accuracy
- Input Resolution: 256 × 256
- Number of Output Classes: 5

The CNN, FCNN, and U-Net approaches are trained and compared based on their training performance and execution time.

## Project Structure

The repository is organized as follows:

flood-map-boundary-prediction/
- CNN-FCNN-UNet.ipynb
- CNN+LSTM.ipynb
- Resnet50.ipynb
- UNet.ipynb
- Untitled.ipynb
- UsingCNN.ipynb
- flood_dataset/
  - train/
  - test/
- masks/
- README.md
- .gitignore

## Technologies Used

- Python
- TensorFlow
- Keras
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Jupyter Notebook

## Purpose

This project explores deep learning-based semantic segmentation techniques for flood mapping and boundary prediction. The different architectures are studied to understand their ability to identify and segment flood intensity regions and boundaries from flood map images.

## Future Work

- Improve segmentation accuracy.
- Use larger flood-map datasets.
- Explore advanced segmentation architectures.
- Incorporate pretrained vision models.
- Evaluate models using IoU and Dice coefficient.
- Develop an interactive flood-map prediction application.