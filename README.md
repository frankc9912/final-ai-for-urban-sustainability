# Road Extraction from Aerial Imagery Using Deep Learning

by Frank Chen

This repository contains the implementation of a deep learning model for automatic road segmentation from high-resolution satellite images, based on an enhanced UNet architecture. The project was developed as a final assignment for a AI for Urban Sustainability at UPenn.

## Overview

Extracting roads from aerial imagery is critical for applications such as urban planning, navigation, and disaster response. This project implements an improved UNet model that integrates:

- Residual Convolution Blocks for deep feature learning
- ASPP (Atrous Spatial Pyramid Pooling) for multi-scale context
- Attention Gates to focus on relevant regions
- Learnable UpConvolutions for better spatial reconstruction

## Dataset

The project uses the [DeepGlobe Road Extraction dataset](https://www.kaggle.com/datasets/balraj98/deepglobe-road-extraction-dataset), which includes:

- 6,226 RGB satellite images (1024×1024 pixels)
- Corresponding binary masks for roads

Images are resized to 256×256 for training.

## Model Architecture

The architecture builds on the original UNet with several enhancements:

- Encoder: Residual blocks with downsampling
- Bottleneck: ASPP for capturing multi-scale features
- Decoder: Attention-based upsampling with transposed convolutions
- Output: 1×1 convolution with sigmoid activation

## Training Details

- Optimizer: Adam
- Evaluation Metric: Intersection over Union (IoU)
- Epochs: 20
- Batch Size: 8
- Hardware: NVIDIA RTX 3070

## Results

- Final model achieves a mean IoU of 0.5259
- Improved road continuity and segmentation accuracy over baseline UNet
- Training time: approximately 70 minutes

## Visual Output

Predictions include side-by-side visualizations of:
- Original Image
- Ground Truth Mask
- Predicted Mask
