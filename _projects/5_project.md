---
layout: page
title: 4D time resolved SSL Unet
description: A Self supervised Unet architecture that can handle 3D + time data.
img: assets/img/sslunet.png
importance: 1
category: work
giscus_comments: false
---

## Overview

The 4D Upper Airway Segmentation project aims to segment the 3D plus time upper airway speech sequences from multiple subjects. In this study, subjects pronounce vowels such as "a", "e", "i", "o", and "u". To achieve accurate segmentation, we utilize a UNet-based Vision Transformer models with self supervised training. For the SSL pre-training with proxy task, we have used the French speaker dataset. After pre-trianing the network is re-trained with data collected from university of iowa research MRI scanner.

## Model Architecture

Given below figure represents the model architecture used for this project. The pre-training is done by doing proxy tasks with the French speaker dataset, and the downstream task will be to segment the airway from the newly collected data.

The architecture is based on a UNet combined with a Vision Transformer (ViT) backbone. This hybrid architecture leverages the strengths of both UNet for spatial features extraction and ViT for capturing long-range dependencies in the data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sslunet.png" title="sslunet" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Network Architecture
</div>


The model consists of:

1. **Encoder**: The encoder uses a Vision Transformer to capture context and relationships within the input sequences efficiently.
2. **Bottleneck**: A UNet-style bottleneck that combines the features extracted from the encoder before passing them to the decoder.
3. **Decoder**: The decoder reconstructs the segmentation maps from the features, utilizing skip connections from the encoder to maintain spatial resolution.
4. **Output Layer**: A final convolutional layer outputs the segmentation mask, indicating the segmented regions of the upper airway.

This architecture facilitates both high-level feature extraction and enabling precise segmentation of the upper airway over the 4D temporal data.

## Key Features

- **Convolutional Layers**: Capture spatial features from 3D inputs.
- **LSTM Layers**: Integrate temporal information, allowing the model to learn dependencies over time sequences.
- **Skip Connections**: Enable better gradient flow and help in preserving spatial features across layers.

## Citations

Please cite the following papers if you are using our code or dataset for development:

   [Automatic Multiple Articulator Segmentation in Dynamic Speech MRI Using a Protocol Adaptive Stacked Transfer Learning U-NET Model](https://www.mdpi.com/2306-5354/10/5/623)
 
   [Airway segmentation in speech MRI using the U-net architecture](https://ieeexplore.ieee.org/abstract/document/9098536)

   [Multimodal dataset of real-time 2D and static 3D MRI of healthy French speakers](https://www.nature.com/articles/s41597-021-01041-3)