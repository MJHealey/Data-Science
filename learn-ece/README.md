# LEARN-ECE
**Leveraging Attention for Robust Neural Event Causality Extraction**
`UC Berkeley · Dec 2024`

---

## Overview

Developed an event causality extraction pipeline on the MAVEN-ERE dataset, training 
and evaluating transformer-based models to predict next events in textual sequences 
across 2,913 documents and 570 event types.

---

## Contents

| File/Folder | Description |
|-------------|-------------|
| `data/` | Notebooks for data acquisition, EDA, preprocessing, and train/dev/test splits |
| `preprocess/` | Script to load data as event streams |
| `prior/` | Prior distribution pickle file used by PAIN model |
| `transformer/` | Eight scripts defining transformer architectures for PAIN, TES, and PC_TES |
| `results/` | CSV files containing training results for each model |
| `PAIN_Main_MAVEN_ERE.py` | Main script for PAIN model |
| `TES_Main_MAVEN_ERE.py` | Main script for TES model |
| `PC_TES_Main_MAVEN_ERE.py` | Main script for PC_TES model |
| `RAWDAG.ipynb` | DAG-based model (teammate's contribution) |
| `*.ipynb` | Colab notebooks for running models end-to-end and as subprocesses |
| `learn-ece-paper.pdf` | Full research paper |

---

## My Contributions

I was responsible for the PAIN and TES model implementations, including data 
preprocessing, model training, hyperparameter tuning, and evaluation. The 
DAG-based model (RAWDAG.ipynb) was developed by a teammate.

---

## Models

**PAIN** — Probabilistic Attention-to-Influence Network
- Models pairwise causal relationships between events using a prior distribution

**TES** — Transformer for Event Sequences *(Best Performer)*
- Standard transformer architecture adapted for temporal event prediction

**PC_TES** — Pairwise Causality Transformer for Event Sequences
- Extends TES with explicit pairwise causality guidance

**RAWDAG** *(teammate's contribution)*
- DAG-based approach to event causality extraction

---

## Key Results

| Model | Log-Likelihood |
|-------|---------------|
| TES | **-0.909** Best |
| PAIN | -1.0063 |

TES outperformed PAIN, demonstrating that a standard transformer architecture 
can capture event dependencies more effectively than the probabilistic 
attention-influence approach on this dataset.

[Full Research Paper](./learn-ece-paper.pdf)

---

## Running the Models

**TES (Google Colab)**
```python
!python TES_Main_MAVEN_ERE.py -data data/MAVEN_ERE/ -epoch 5 -batch_size 32 \
-d_model 512 -d_inner 256 -d_k 256 -d_v 256 -n_head 4 -n_layers 4 \
-dropout 0.1 -lr 1e-4 -event_interest 7
```

**PAIN (Google Colab)**
```python
!python PAIN_Main_MAVEN_ERE.py -data data/MAVEN_ERE/ -prior prior/MAVEN_ERE/sparse/ \
-epoch 1 -batch_size 16 -d_model 512 -d_inner 256 -d_k 256 -d_v 256 \
-n_head 4 -n_layers 4 -dropout 0.1 -lr 1e-4 -num_samples 1 \
-event_interest 7 -threshold 0.4
```

**PC_TES (Google Colab)**
```python
!python PC_TES_Main_MAVEN_ERE.py -data data/MAVEN_ERE/ -epoch 3 -batch_size 32 \
-d_model 512 -d_inner 256 -d_k 256 -d_v 256 -n_head 4 -n_layers 4 \
-dropout 0.1 -lr 1e-4 -type_z 5 -type_y 8 -sle 1 -excites 1 -alpha 0.001
```

---
