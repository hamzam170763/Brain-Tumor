# Brain Tumor Classification: Project Report

**Author:** Hamza Mughal  
**Department:** Artificial Intelligence  
**Institution:** The National University of Computer and Emerging Sciences (NUCES-FAST)  
**Location:** Karachi, Pakistan  
**Email:** mughalhamza1998@gmail.com

---

## 1. Problem Statement

Brain tumors are among the most critical medical conditions requiring early and accurate detection for effective treatment planning. Manual interpretation of Magnetic Resonance Imaging (MRI) scans is time-consuming, subjective, and requires significant expertise from radiologists.

**Objective:** Develop an automated deep learning-based classification system to detect the presence of brain tumors from MRI images.

**Classification Task:** Binary classification
- **Tumor Present (Yes)**
- **No Tumor (No)**

---

## 2. Base Paper Results

**Reference Paper:** "Brain Tumor Classification in MRI Images Using VGG19" (Informatica 49, 2025, 163-174)

### Base Paper Methodology:
- **Model:** VGG19 with frozen convolutional layers
- **Preprocessing:** Type-2 Fuzzy Logic image enhancement in CIELAB color space
- **Dataset:** BR35H Brain MRI dataset (23 tumor + 35 non-tumor images)
- **Augmentation:** Rotation, width/height shift, shear, zoom, horizontal flip

### Base Paper Results:
| Metric | Value |
|--------|-------|
| Model Parameters | 140,946,370 (537.67 MB) |
| Input Size | 224 × 224 × 3 |
| Training Accuracy | 99-100% |
| Validation Accuracy | 100% |

---

## 3. Replication Results

We successfully replicated the base paper methodology.

### Our Replication Results (VGG19):
| Epoch | Training Acc | Validation Acc | Training Loss | Val Loss |
|-------|-------------|----------------|---------------|----------|
| 5 | 88.43% | 90.91% | 0.2783 | 0.2319 |
| 10 | 96.97% | 98.18% | 0.0999 | 0.0788 |
| 15 | 98.62% | 98.18% | 0.0512 | 0.0459 |
| 20 | 99.17% | 100.00% | 0.0291 | 0.0128 |
| 25 | 100.00% | 100.00% | 0.0086 | 0.0090 |

**Status:** ✅ Successfully replicated with 100% validation accuracy

---

## 4. Innovation Results (SwinV2 Transformer Models)

### Innovation Overview:
We extended the base paper by implementing modern Vision Transformer architectures (SwinV2) featuring:
- Shifted window self-attention mechanism
- Hierarchical feature representation
- Log-spaced continuous position bias

### 4.1 SwinV2-Large Results

**Model:** `swinv2_large_window12to16_192to256.ms_in22k_ft_in1k`

| Metric | Value |
|--------|-------|
| Parameters | ~197 million |
| Test Accuracy | **100%** |
| F1-Score | **1.00** |
| Precision | 1.00 |
| Recall | 1.00 |

### 4.2 SwinV2-Tiny Results

**Model:** `swinv2_tiny_window8_256.ms_in1k`

| Metric | Value |
|--------|-------|
| Parameters | ~28 million (7x smaller than VGG19) |
| Test Accuracy | **94.74%** |
| F1-Score | **0.948** |
| Precision (Tumor) | 0.875 |
| Recall (Tumor) | **1.00** (Perfect tumor detection!) |

---

## 5. Comprehensive Comparison

| Model | Parameters | Test Accuracy | F1-Score | Tumor Recall |
|-------|------------|---------------|----------|--------------|
| **VGG19 (Base)** | 140.9M | 100% | 1.00 | 1.00 |
| **SwinV2-Large** | ~197M | 100% | 1.00 | 1.00 |
| **SwinV2-Tiny** | ~28M | 94.74% | 0.948 | 1.00 |

### Key Findings:

1. **SwinV2-Large achieves equivalent performance** to VGG19 with transformer architecture benefits

2. **SwinV2-Tiny offers remarkable efficiency:** Only 28M parameters (7x smaller) while achieving 100% tumor recall

3. **Clinical significance:** All models achieve perfect tumor recall - critical for medical applications

---

## 6. Future Work

1. **Multi-class Classification:** Classify tumor types (glioma, meningioma, pituitary)
2. **Larger Datasets:** Validate on BraTS, TCGA-GBM datasets
3. **3D Analysis:** Incorporate volumetric MRI analysis
4. **Model Ensemble:** Combine VGG19 and SwinV2 predictions
5. **Clinical Validation:** Deploy in clinical settings
6. **Edge Deployment:** Optimize for resource-constrained healthcare settings

---

## 7. GitHub Repository

**Repository:** https://github.com/hamzam170763/Brain-Tumor

---

## 8. Conclusion

This project successfully:
- ✅ Replicated VGG19 baseline from reference paper
- ✅ Introduced SwinV2 transformer architectures as innovation
- ✅ Demonstrated transformer efficiency (7x parameter reduction with SwinV2-Tiny)
- ✅ Achieved 100% tumor recall across all models
- ✅ Validated with Grad-CAM explainability

---

*Report generated: November 2025*
