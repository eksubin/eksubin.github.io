---
layout: page
title: 4D time resolved Unet
description: A custom Unet architecture that can handle 3D + time data.
img: assets/img/clstmunet.png
importance: 1
category: work
giscus_comments: false
---

## Overview

This project implements a 3D U-Net model enhanced with Convolutional Long Short-Term Memory (CLSTM) cells. This architecture enables the U-Net to effectively leverage temporal resolution by processing both spatial and temporal dimensions in volumetric data. The integration of CLSTM cells allows the model to capture complex dependencies across time, making it particularly suitable for analyzing 4D medical imaging datasets such as dynamic MRI or CT scans, where both spatial and temporal information are crucial for accurate interpretation.

## CLSTM UNet 4D

The CLSTM UNet3D model is a convolutional neural network architecture that combines convolutional and LSTM (Long Short-Term Memory) layers for the purpose of processing volumetric data as given in the figure below. It is particularly useful for tasks such as semantic segmentation in medical imaging.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/unet4D.png" title="unet4D" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Key Features

- **Convolutional Layers**: Capture spatial features from 3D inputs.
- **LSTM Layers**: Integrate temporal information, allowing the model to learn dependencies over time sequences.
- **Skip Connections**: Enable better gradient flow and help in preserving spatial features across layers.

## Applications

The CLSTM UNet3D architecture can be applied in various fields, including:

- Medical image analysis (e.g., MRI, CT scans)
- 3D object detection and segmentation
