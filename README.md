# Quantum Machine Learning for Brain Tumor MRI Classification

This repository contains the demonstration material presented to the Qiskit study group for exploring quantum machine learning methods applied to brain tumor MRI image classification.

The project uses CNN-based feature extraction followed by quantum machine learning classification. Two approaches are provided for comparison:

- **Variational Quantum Classifier (VQC)** — a trainable quantum circuit used as the classification model.
- **Quantum Support Vector Classifier (QSVC)** — a quantum-kernel-based approach using a quantum feature map and kernel evaluation.

Both approaches operate on the same pre-extracted CNN feature representations, allowing the two quantum classification methods to be compared using a common input representation.

## Classification task

The underlying MRI dataset contains four classes:

| Class | Description |
| --- | --- |
| `Glioma` | Glioma brain tumor |
| `Meningioma` | Meningioma brain tumor |
| `Notumor` | No brain tumor |
| `Pituitary` | Pituitary brain tumor |

## Data

The `data_Demo/` directory contains the CNN-extracted feature vectors and corresponding labels used by the notebooks:

```
data_Demo/
├── X_train.npy
├── y_train.npy
├── X_test.npy
└── y_test.npy
```

The notebooks load these feature files directly. The original MRI images are not required to run the classification notebooks.

For completeness and provenance, the original MRI images are also included in:

```
data_Demo/
├── Training_raw_images/
└── Testing_raw_images/
```

These images are retained to preserve the relationship between the original MRI data and the CNN-derived feature representations, and to allow future inspection or reproduction of the feature-extraction stage.

The original images were obtained from a publicly available Kaggle dataset and remain subject to the original dataset's license and terms of use.

## Notebooks

### VQC

`VQC_MRI_Classification.ipynb`

Demonstrates brain tumor classification using a Variational Quantum Classifier.

### QSVC

`QSVC_MRI_Classification.ipynb`

Demonstrates classification using a Quantum Support Vector Classifier and provides a quantum-kernel-based comparison with the VQC approach.

The two notebooks use the same training and testing feature sets so that their classification performance can be compared on the same task.

## Setup

Each notebook specifies its required Qiskit version at the top. VQC and QSVC are intended to be run in **separate environments**, since their Qiskit version requirements are not mutually compatible — check the version pinned in each notebook before installing dependencies.

## Presentation slides

The slides presented to the Qiskit study group are shared separately via email and are not included in this repository.
