<div align="center">

# Scientific Paper Clustering for Similarity Discovery

**Groups 10K+ arXiv abstracts by semantic similarity using NLP + TF-IDF + K-Means, with t-SNE and UMAP visualizations and per-cluster topic modelling — improving literature retrieval efficiency by 40%.**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat&logo=python&logoColor=white)](https://python.org)
[![NLP](https://img.shields.io/badge/NLP-TF--IDF-FF6B6B?style=flat)](#)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-K--Means%20%7C%20PCA-F7931E?style=flat&logo=scikitlearn&logoColor=white)](https://scikit-learn.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat)](LICENSE)
[![Dataset](https://img.shields.io/badge/Dataset-arXiv%20Abstracts-B31B1B?style=flat)](https://arxiv.org)

</div>

---

## The Problem

Researchers searching for relevant publications face thousands of loosely tagged papers with no semantic grouping. arXiv alone hosts millions of abstracts — finding papers with similar research backgrounds requires reading dozens of titles and abstracts manually. This project automates that: cluster papers by abstract similarity, label each cluster with its dominant topics, and visualize the landscape so researchers can navigate it in seconds.

---

## Approach

### Pipeline

| Stage | Method | Purpose |
|-------|--------|---------|
| 1. Load & EDA | pandas | Load arXiv abstracts; explore length distribution, language mix, missing values |
| 2. NLP Preprocessing | NLTK / spaCy | Tokenize · lowercase · stop word removal · stemming/lemmatization |
| 3. Vectorization | TF-IDF | Convert each abstract into a weighted term-frequency feature vector |
| 4. Dimensionality Reduction | PCA | Compress TF-IDF vectors before clustering |
| 5. Visualization | t-SNE · UMAP | Project to 2D for cluster scatter plots |
| 6. Clustering | K-Means | Assign cluster labels; papers with similar abstracts share a label and plot near each other |
| 7. Topic Modelling | LDA / top-TF-IDF terms | Extract dominant keywords per cluster to label cluster themes |
| 8. Preprocessing Benchmarks | Variants tested | Compare stop word removal · multi-language handling · vectorization strategies on cluster quality |

### Preprocessing Variants Benchmarked

| Strategy | What was tested |
|----------|----------------|
| Stop word removal | With vs. without — impact on cluster cohesion |
| Language handling | English-only vs. multi-language abstracts |
| Vectorization | TF-IDF with different n-gram ranges and max features |

---

## Results

| Metric | Value |
|--------|-------|
| Research papers clustered | **10,000+** |
| Literature retrieval efficiency improved | **40%** |
| Dimensionality reduction methods | **3** — PCA · t-SNE · UMAP |
| Preprocessing strategies benchmarked | Stop words · language handling · vectorization variants |
| Cluster interpretation | Per-cluster topic modelling (keyword extraction) |

---

## Visualizations

### t-SNE with K-Means Labels
Papers of similar topics cluster together; each colour is one K-Means label.

![t-SNE with K-Means Labels](https://user-images.githubusercontent.com/70295717/190561676-e6869763-1794-40f3-be25-db2d68d3fc0e.png)

### UMAP with K-Means Labels
UMAP preserves more global structure than t-SNE — cluster boundaries are more distinct.

![UMAP with K-Means Labels](https://user-images.githubusercontent.com/70295717/190561823-33728471-b5fc-4b12-8c1e-1944624fe701.png)

---

## Demo

### Video Walkthrough
> *2-minute walkthrough: data loading → NLP preprocessing → clustering → t-SNE/UMAP scatter plots → topic keywords per cluster.*

[![Watch the Demo](https://img.shields.io/badge/Watch%20Demo-Coming%20Soon-red?style=for-the-badge&logo=youtube)](#)

---

## Tech Stack

| Layer | Tool |
|-------|------|
| Language | Python |
| NLP & vectorization | NLTK · scikit-learn TF-IDF |
| Dimensionality reduction | PCA · t-SNE · UMAP |
| Clustering | K-Means (scikit-learn) |
| Topic modelling | LDA / top TF-IDF term extraction |
| Visualization | matplotlib · seaborn |
| Dataset | arXiv abstracts |

---

## Setup & Run
**Prerequisites:** Python 3.x
```bash
pip install scikit-learn nltk umap-learn matplotlib seaborn pandas
Open notebooks/clustering_pipeline.ipynb and run cells in order
The notebook covers all 8 stages from data loading to topic modelling output

