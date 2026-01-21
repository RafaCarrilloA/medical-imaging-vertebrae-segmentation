<<<<<<< HEAD
# Automated 3D Spine Reconstruction via Deep Learning

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)
![Framework: MONAI](https://img.shields.io/badge/Framework-MONAI-green.svg)

Este proyecto presenta un sistema avanzado de **Deep Learning** para la segmentación semántica volumétrica y reconstrucción 3D de la columna vertebral a partir de tomografías computarizadas (CT), comparando arquitecturas convolucionales y de Transformers.

## Descripción del Proyecto

La segmentación manual de la columna vertebral es un proceso ineficiente (2-4 horas/paciente). Este desarrollo automatiza el proceso mediante el uso de redes neuronales de última generación, permitiendo aplicaciones en cirugía robótica y diseño de prótesis personalizadas.

## Aspectos Técnicos y Arquitecturas

El proyecto evalúa y compara dos de las arquitecturas más potentes en el estado del arte actual para imagen médica:

1.  **ResUNet 3D:** Una evolución de la U-Net clásica que utiliza bloques residuales para mejorar la convergencia en volúmenes 3D.
2.  **Swin UNETR (Hierarchical Vision Transformer):** Un modelo híbrido que utiliza *Swin Transformers* como encoder para capturar dependencias espaciales a larga distancia, combinado con un decoder convolucional.

### Pipeline de Datos
* **Framework:** [MONAI](https://monai.io/) (Medical Open Network for AI).
* **Dataset:** [VerSe](https://github.com/anjany/verse) (Large Scale Vertebrae Segmentation Challenge).
* **Preprocesamiento:** Orientación **RAS**, remuestreo isotrópico y normalización de unidades **Hounsfield (HU)**.

## Resultados y Visualización

| Arquitectura | Métrica Dice (Promedio) | Fortalezas |
| :--- | :--- | :--- |
| **ResUNet** | ~0.85 | Estabilidad y eficiencia en GPU. |
| **Swin UNETR** | ~0.87 | Mejor captura de detalles anatómicos complejos. |

![Comparativa de Modelos](assets/resultado.png)
*En la imagen superior (extraída de nuestra memoria técnica) se observa la comparativa de segmentación entre ResUNet (a) y Swin UNETR (b) frente al Ground Truth.*

## Estructura del Repositorio
* `notebooks/`: Implementación completa en `spine_segmentation_3d_resunet.ipynb`.
* `docs/`: Reporte técnico (`technical_report_spine_segmentation.pdf`) y presentación.
* `assets/`: Capturas de resultados y diagramas.

## Instalación y Uso
1. Clonar el repositorio: `git clone https://github.com/TU_USUARIO/spine-segmentation-3d.git`
2. Instalar dependencias: `pip install -r requirements.txt`
=======
# medical-imaging-vertebrae-segmentation
Segmentación semántica volumétrica y reconstrucción 3D de la columna vertebral mediante ResUNet 3D y MONAI sobre el dataset VerSe
>>>>>>> b8efb1bf26b6a68d1bd17fc4cb853a4868640761
