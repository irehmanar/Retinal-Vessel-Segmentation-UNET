# DRIVE 2004 Dataset for Retinal Vessel Segmentation

This repository provides an implementation for retinal vessel segmentation using the **DRIVE 2004 Dataset**. The goal of this project is to apply deep learning techniques for segmenting the retinal blood vessels, which is essential for diagnosing and monitoring eye diseases such as diabetic retinopathy and glaucoma. This dataset is widely used in the medical image segmentation community.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Installation](#installation)
- [Data Preparation](#data-preparation)
- [Model Architecture](#model-architecture)


## Introduction

The **DRIVE 2004 dataset** contains **retinal images** that are annotated with corresponding **binary masks**, marking the blood vessels in the retina. This dataset is used to train and evaluate machine learning models for the task of retinal vessel segmentation. The **UNET** architecture is commonly used for this task because of its ability to capture fine-grained details in segmentation problems.

In this repository, we implement a **UNET-based deep learning model** in **PyTorch** to segment the retinal blood vessels using the DRIVE 2004 dataset. The dataset consists of **20 training images** and **20 testing images**, each with corresponding binary ground truth masks.

## Dataset

The dataset can be downloaded from **Kaggle**:

- **[DRIVE 2004 Dataset](https://www.kaggle.com/datasets/zionfuo/drive2004)**

The DRIVE dataset contains the following:

1. **Training images**: 20 retinal images used for training the model.
2. **Test images**: 20 retinal images used for evaluating the model.
3. **Ground truth masks**: Binary masks for both training and test images.

The images are 584x565 pixels in size and are in **PNG format**. The ground truth masks are also in **binary PNG format**, where the vessels are marked as white (1) and the background is black (0).



## Installation

To run this project, you will need to install the necessary dependencies.

### Clone the repository

git clone https://github.com/your-username/retinal-vessel-segmentation.git


## Data Preparation

### 1. Data Augmentation
Data augmentation is performed to improve the model's generalization ability. The augmentation techniques used in this project are:

- **Horizontal Flip**
- **Vertical Flip**
- **Rotation**

The augmented images and masks will be saved into separate directories for training and testing.

## Model Architecture

The model used in this project is the **UNET** architecture, which is commonly employed for image segmentation tasks. The UNET architecture consists of:

- **Encoder (Contracting Path)**: A series of convolutional layers and pooling operations that reduce the spatial dimensions and increase the depth of the feature maps.
  
- **Bottleneck**: The deepest layer of the network that captures high-level feature representations.
  
- **Decoder (Expansive Path)**: A series of upsampling layers that gradually reconstruct the spatial dimensions of the image, using skip connections to retain fine-grained information.
  
- **Output**: A final convolutional layer that generates the segmentation mask (vessel vs. background).

The model is implemented in **PyTorch** with the following key components:

- **Convolutional blocks** for feature extraction.
- **Max-pooling layers** for downsampling.
- **Transpose convolutions** for upsampling.
- **Skip connections** between the encoder and decoder to preserve fine spatial details.

