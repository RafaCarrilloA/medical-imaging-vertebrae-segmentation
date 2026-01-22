# 3D Automated Spine Segmentation and Volumetric Reconstruction

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![MONAI](https://img.shields.io/badge/Framework-MONAI-green.svg)](https://monai.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Executive Summary

Manual segmentation of the spinal column is a high-latency clinical task, requiring between 2 and 4 hours per patient, and is highly susceptible to inter-observer variability. This repository presents an end-to-end medical imaging pipeline for the **semantic segmentation and 3D reconstruction** of the human spine from Computed Tomography (CT) scans. 

The project conducts a rigorous comparative analysis between state-of-the-art Convolutional Neural Networks (CNNs) and Hierarchical Vision Transformers (ViTs), specifically optimized for high-resolution volumetric medical data.

---

## Technical Architecture

The study evaluates two flagship architectures within the medical imaging domain, leveraging the **MONAI** framework for implementation:

### 1. 3D ResUNet (Residual U-Net)
A volumetric evolution of the classical U-Net. By integrating **Residual Blocks**, the architecture mitigates the vanishing gradient problem in deep 3D networks, facilitating faster convergence and superior feature propagation across spatial scales.

### 2. Swin UNETR (Swin-Transformer-based UNETR)
A hybrid architecture that utilizes a **Hierarchical Swin Transformer** as the encoder. This allows the model to capture long-range spatial dependencies and multi-scale self-attention, which is critical for identifying complex anatomical structures where global context is essential.



---

## Data Engineering & Pre-processing

To ensure reproducibility and clinical relevance, the pipeline implements a standardized workflow using the **VerSe (Large Scale Vertebrae Segmentation Challenge)** dataset:

* **Spatial Standardization:** Reorientation to **RAS** (Right, Anterior, Superior) coordinate system.
* **Anisotropy Correction:** Isotropic resampling for uniform voxel dimensions ($1mm \times 1mm \times 1mm$).
* **Intensity Normalization:** Clipping and scaling based on **Hounsfield Units (HU)** to optimize bone structure contrast (Windowing).
* **Augmentation:** Implementation of random rotations, scaling, and intensity shifts to improve model generalization.

---

## Experimental Evaluation

### Metrics
The models were evaluated using the **Dice Similarity Coefficient (DSC)**, defined as:

$$DSC = \frac{2 |X \cap Y|}{|X| + |Y|}$$

### Comparative Results

| Architecture | Mean Dice Score | Inference Latency | Primary Advantage |
| :--- | :---: | :---: | :--- |
| **3D ResUNet** | 0.852 | Low | Computational efficiency and high stability. |
| **Swin UNETR** | **0.874** | Moderate | Superior capture of complex vertebral morphologies. |

### Visual Validation
Below is a comparative analysis of the segmentation accuracy in both axial slices and 3D Maximum Intensity Projections (MIP).

![Segmentation Comparison](assets/resultado.png)
*Figure 1: Comparative analysis of (a) ResUNet and (b) Swin UNETR performance against Ground Truth.*

---

## Repository Structure

```text
├── assets/             # Architectural diagrams, MIP projections, and result plots.
├── docs/               # Technical report (PDF), poster, and project presentation.
├── notebooks/          # Implementation: spine_segmentation_3d_resunet.ipynb.
├── requirements.txt    # Environment dependencies (PyTorch, MONAI, Nibabel).
└── README.md           # Project documentation.

```


## Installation and Environment Setup

1. **Clone the repository:**
git clone [https://github.com/RafaCarrilloA/medical-imaging-vertebrae-segmentation.git](https://github.com/RafaCarrilloA/medical-imaging-vertebrae-segmentation.git)

2. **Install dependencies:**

pip install -r requirements.txt




## Authors

**University of Granada (UGR)** *Department of Computer Science and Artificial Intelligence*

* Rafael Carrillo Arroyo
* Daniel Chico Valderas
* Miguel Luis Rodríguez Márquez
* Robin Junior Padilla Yuco

