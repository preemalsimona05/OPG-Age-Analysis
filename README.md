# OPG-Age-Analysis: Automated Dental Age Estimation & PTR Pipeline

## Model Benchmarking & Performance

We benchmarked five segmentation architectures to isolate individual teeth and pulp chambers. **DenseNet121** achieved the highest accuracy and is selected for the final pipeline.

| Architecture | Encoder | Dice Accuracy (%) | Status |
| :--- | :--- | :--- | :--- |
| **U-Net** | **DenseNet121** | **94.83%** | **Selected Model** |
| U-Net | ResNet34 | 92.10% | Benchmarked |
| U-Net | EfficientNet-B0 | 91.80% | Benchmarked |
| U-Net | MobileNetV2 | 90.45% | Benchmarked |
| SegFormer | MiT-B0 | 89.60% | Benchmarked |

---

## Key Features

* **Per-Tooth Component Extraction**: Utilizes Connected Component Analysis (CCA) and horizontal spatial sorting to isolate individual teeth (1st Premolar, 2nd Premolar, 2nd Molar) from quadrant masks.
* **Automated Metrics Calculation**: Computes individual Crown Area, Pulp Area, and Pulp-to-Tooth Ratio (PTR) in pixels.
* **Clinician-Ready Export**: Compiles patient metadata (ID, Age, Sex) alongside multi-tooth metrics directly into a standardized `.xlsx` spreadsheet format for traditional statistical analysis and comparison against the AI model.
