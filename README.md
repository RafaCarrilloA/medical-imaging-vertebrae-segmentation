Aquí tienes el archivo **README.md** completo, sin emojis, con un lenguaje técnico avanzado y siguiendo el estándar de los repositorios de investigación en Inteligencia Artificial Médica.

Copia y pega este bloque íntegro en tu archivo:

```markdown
# 3D Automated Spine Segmentation and Volumetric Reconstruction

This repository contains the implementation of a medical imaging pipeline for the semantic segmentation and 3D reconstruction of the human spine from Computed Tomography (CT) scans. The project evaluates high-performance deep learning architectures, specifically comparing convolutional-based models against hierarchical vision transformers.

---

## Project Overview

Manual segmentation of the spinal column is a high-latency task, typically requiring 2 to 4 hours per patient, and is highly susceptible to inter-observer variability. This project automates the process using state-of-the-art neural architectures, enabling clinical applications in robotic surgical planning, personalized orthopedic design, and automated clinical diagnostics for pathologies such as scoliosis or vertebral fractures.

## Technical Architecture

The study performs a comparative analysis of two flagship architectures within the medical imaging domain:

### 1. 3D ResUNet (Residual U-Net)
A volumetric evolution of the classical U-Net. By integrating residual blocks, the architecture mitigates the vanishing gradient problem in deep 3D networks, facilitating faster convergence and superior feature propagation across spatial scales.

### 2. Swin UNETR (Swin-Transformer-based UNETR)
A hybrid architecture that utilizes a Hierarchical Swin Transformer as the encoder. This allows the model to capture long-range spatial dependencies and multi-scale self-attention, which is critical for identifying complex anatomical structures where global context is essential.



---

## Data Engineering Pipeline

The implementation leverages the MONAI (Medical Open Network for AI) framework to ensure a standardized and reproducible medical imaging workflow:

* **Dataset:** VerSe (Large Scale Vertebrae Segmentation Challenge).
* **Spatial Standardization:** Reorientation to RAS (Right, Anterior, Superior) coordinate system.
* **Anisotropy Correction:** Isotropic resampling for uniform voxel dimensions.
* **Intensity Normalization:** Clipping and scaling based on Hounsfield Units (HU) to optimize bone structure contrast.

---

## Experimental Results

The models were evaluated based on the Dice Similarity Coefficient (DSC), measuring the overlap between the predicted segmentation and the ground truth.

| Architecture | Mean Dice Score | Key Strengths |
| :--- | :---: | :--- |
| **3D ResUNet** | 0.852 | Computational efficiency and high stability in GPU memory. |
| **Swin UNETR** | 0.874 | Superior capture of complex vertebral morphologies. |

### Visual Validation
The following visualization highlights the reconstruction accuracy in both axial slices and 3D Maximum Intensity Projections (MIP).

![Segmentation Comparison](assets/resultado.png)
*Figure 1: Comparative analysis of (a) ResUNet and (b) Swin UNETR performance against Ground Truth (VerSe Dataset).*

---

## Repository Structure

```text
├── assets/          # Visual results, architectural diagrams and MIP projections.
├── docs/            # Technical report (PDF) and project presentation.
├── notebooks/       # Main implementation: spine_segmentation_3d_resunet.ipynb.
├── requirements.txt # Environment dependencies.
└── README.md        # Project documentation.

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

