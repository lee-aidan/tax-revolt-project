## Project Overview

This repository contains the full data-processing, analysis, and visualization pipeline for *A World History of Tax Rebellions*. The project was designed as a **methods-forward informatics workflow**, combining document processing, natural language processing (NLP), large language model (LLM)–assisted analysis, and interactive visualization to transform a historical reference text into a structured, uncertainty-aware analytical dataset.

The primary goal is not to automate historical interpretation, but to make **long-run patterns, uncertainty, and scale visible** across thousands of years of tax-related contention.

---

## Data Extraction and Structuring

The project begins with end-to-end processing of the source PDF, including:
- Extraction of tabular event entries
- Preservation of images and their associated captions
- Parsing and cleaning of in-text *“See also”* references for future network and citation analysis
- Post-hoc pruning and normalization to correct formatting irregularities

The result is a reproducible, machine-readable dataframe representing the full contents of the book.

---

## NLP and Machine Learning Analysis

Initial NLP analysis was conducted using standard embedding-based methods applied to event descriptions. Text embeddings were generated using an OpenAI embedding model and analyzed with:
- Dimensionality reduction (PCA and UMAP)
- Density-based clustering (HDBSCAN)

These experiments revealed that unsupervised text clustering overwhelmingly grouped events by **geographic and administrative context**, limiting their usefulness for substantive classification. This finding motivated a shift toward an LLM-assisted approach.

---

## LLM-Assisted Taxonomy and Spatiotemporal Annotation

Large language models were used to:
1. Develop a small, explicit taxonomy of tax-related contention
2. Assign each event to a taxonomy category with a confidence score
3. Infer conservative spatial centroids and temporal intervals, including uncertainty estimates

All LLM outputs are treated as **structured annotations**, not ground truth. Confidence scores are retained throughout the pipeline and used to modulate uncertainty-aware aggregation rather than to assert correctness.

---

## Temporal and Spatial Visualization

The final outputs are interactive visualizations designed to surface uncertainty rather than suppress it:
- Time-binned event distributions that account for imprecise or multi-year dating
- Taxonomy-disaggregated temporal trends
- Global spatial visualizations using centroid-based representations that avoid historical border anachronism

These visualizations are intended as **exploratory tools**, supporting historical inquiry across millennia rather than making definitive claims.

---

## Scope and Use

This repository represents a complete and self-contained methodological pipeline. It is intended for:
- Computational history and digital humanities research
- Methods-focused demonstrations of LLM-assisted annotation
- Exploratory analysis of large historical reference corpora

The project prioritizes transparency, reproducibility, and interpretability throughout.
