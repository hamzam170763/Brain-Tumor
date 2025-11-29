Brain Tumor Conference Paper (IEEE)
=================================

Files:
- `brain_tumor_ieee.tex` : IEEEtran conference LaTeX source (uses images from parent folder).

Included figures (referenced by the LaTeX file):
- `training_results.png`
- `swinv2_training_curves.png`
- `swinv2_performance_curves.png`
- `precision_recall_curves.png`
- `fuzzy_enhancements.png`
- `xai_grad-cam_explanations.png`

How to build (requires a TeX distribution such as TeX Live):

1. Open a terminal in the `Colab Submission Brain Tumor Classification` directory.
2. Change to the `paper` folder and compile:

```bash
cd "Colab Submission Brain Tumor Classification"/paper
pdflatex brain_tumor_ieee.tex
pdflatex brain_tumor_ieee.tex
```

Notes and next steps:
- The LaTeX file contains placeholder author information. Replace with real author names/affiliations.
- Table values and figure captions are taken from the notebook visualizations saved in the repository; double-check numbers if you re-run the notebooks with different seeds or data splits.
- If images are moved, update `\graphicspath` or image paths in the `.tex` file.
