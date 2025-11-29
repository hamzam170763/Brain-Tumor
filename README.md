# Brain Tumor Classification Using Deep Learning

**A Comparative Study of VGG19 and SwinV2 Transformer Architectures**

[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue)](https://github.com/hamzam170763/Brain-Tumor)

## Author
**Hamza Mughal**  
Department of Artificial Intelligence  
The National University of Computer and Emerging Sciences (NUCES-FAST)  
Karachi, Pakistan  
Email: mughalhamza1998@gmail.com

---

## Overview

This project implements brain tumor classification from MRI images using deep learning. We compare:
1. **VGG19** - CNN baseline with transfer learning (from base paper)
2. **SwinV2-Large** - Large transformer model (~197M parameters)
3. **SwinV2-Tiny** - Lightweight transformer (~28M parameters)

## Results Summary

| Model | Parameters | Test Accuracy | F1-Score | Tumor Recall |
|-------|------------|---------------|----------|--------------|
| VGG19 (Baseline) | 140.9M | 100% | 1.00 | 1.00 |
| SwinV2-Large | ~197M | 100% | 1.00 | 1.00 |
| SwinV2-Tiny | ~28M | 94.74% | 0.948 | 1.00 |

---

## How to Regenerate Results

### Prerequisites

```bash
# For VGG19 (TensorFlow/Keras)
pip install tensorflow keras numpy pandas matplotlib scikit-learn opencv-python

# For SwinV2 (PyTorch/timm)
pip install torch torchvision timm numpy pandas matplotlib scikit-learn
```

### Step 1: Clone Repository

```bash
git clone https://github.com/hamzam170763/Brain-Tumor.git
cd Brain-Tumor
```

### Step 2: Extract Dataset

```bash
unzip brain_tumor_dataset.zip
```

### Step 3: Run Notebooks

**Option A: Google Colab (Recommended)**
1. Upload notebooks to Google Colab
2. Enable GPU: Runtime → Change runtime type → GPU
3. Upload/mount dataset
4. Run all cells

**Option B: Local Jupyter**
```bash
jupyter notebook
```
Then open and run each notebook:
- `brain_tumor_image_prediction_vgg19.ipynb` - VGG19 baseline
- `Brain_Tumor_Swinv2_large.ipynb` - SwinV2-Large model
- `Brain_Tumor_Swinv2_Tiny.ipynb` - SwinV2-Tiny model

---

## Project Structure

```
Brain-Tumor/
├── brain_tumor_image_prediction_vgg19.ipynb  # VGG19 baseline (TensorFlow)
├── Brain_Tumor_Swinv2_large.ipynb            # SwinV2-Large (PyTorch)
├── Brain_Tumor_Swinv2_Tiny.ipynb             # SwinV2-Tiny (PyTorch)
├── paper/
│   ├── brain_tumor_ieee.tex                  # IEEE paper source
│   └── brain_tumor_ieee.pdf                  # Compiled paper
├── training_results.png                       # VGG19 training curves
├── swinv2_training_curves.png                # SwinV2 training curves
├── fuzzy_enhancements.png                    # Preprocessing samples
├── xai_grad-cam_explanations.png             # Explainability results
├── brain_tumor_dataset.zip                   # Original BR35H dataset
├── SUBMISSION_REPORT.md                      # Detailed project report
└── README.md                                 # This file
```

---

## Dataset

**BR35H Brain MRI Dataset**
- 23 tumor images + 35 non-tumor images (original)
- Augmented to 453 images

---

## Key Findings

1. **VGG19 baseline successfully replicated** with 100% validation accuracy
2. **SwinV2-Large matches VGG19** performance with transformer architecture
3. **SwinV2-Tiny achieves 7x parameter reduction** while maintaining 100% tumor recall
4. **Grad-CAM confirms** models focus on clinically relevant tumor regions

---

## References

- Base Paper: "Brain Tumor Classification in MRI Images Using VGG19" (Informatica 49, 2025)
- SwinV2: Liu et al., "Swin Transformer V2" (CVPR 2022)

---

*Last updated: November 2025*
