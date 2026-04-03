# Pawpularity
**Predicting Engagement with a Pet's Profile Based on Profile Picture**
`UC Berkeley · May 2024`

---

## Overview

Built an image regression pipeline to predict a pet's "pawpularity" engagement score 
from profile pictures, fine-tuning a ResNet model on 9,912 pet images from a Kaggle 
competition dataset.

---

## Contents

| File | Description |
|------|-------------|
| `pawpularity.ipynb` | Full analysis and modeling notebook |
| `pawpularity.pdf` | Project presentation slides |

---

## My Contributions

**Exploratory Data Analysis**
- Analyzed 9,912 pet images; identified and removed 27 duplicate images with 
  inconsistent labels that could have introduced noise into model training

**Preprocessing Pipeline**
- Collaborated on building the preprocessing pipeline including a 60-20-20 
  train/validation/test split, image transformations, and augmentation techniques 
  (brightness, contrast, saturation, random flips) applied to the training set

**Modeling**
- Contributed to fine-tuning a ResNet model through extensive hyperparameter 
  experimentation, evaluating learning-rate schedules, decay strategies, and 
  final-layer configurations

---

## Key Results

- **Test RMSE: 20.39**
- Primary performance limitation: label inconsistency in visually similar images
- All work aligned with the **NeurIPS Responsible AI Checklist**, emphasizing data 
  quality, transparency, and reproducibility

[Project Presentation](./pawpularity.pdf)

---
