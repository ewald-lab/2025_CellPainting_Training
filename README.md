# 🧪 Ewald Lab Training on Cell Painting Data

Welcome to the Ewald Lab Cell Painting Training Repository!
This repository provides a step-by-step tutorial for learning how to process, evaluate, and analyze Cell Painting datasets.

## 📘 Overview

The **Cell Painting assay** is a high-content imaging approach that captures morphological features of cells across multiple fluorescent channels.

This tutorial walks you through:

- Setting up the environment
- Processing CellProfiler output data
- Performing downstream analyses to link morphological profiles with biological activity

## 🧭 Learning Objectives

By the end of this tutorial, you will be able to:

- Use PyCytominer to process raw morphological profiles
- Evaluate phenotypic activity using mAP metrics
- Perform biological interpretation of morphological profiles
  
## 🧰 Prerequisites & Environment Setup

Before starting, ensure you have Python ≥ 3.9, uv (for package management), and git installed on your computer. We also highly recommend using an IDE like VSCode. Once you have this basic software installed, use your command line to clone the repository:

```bash
git clone https://github.com/ewald-lab/2025_CellPainting_Training.git
cd 2025_CellPainting_Training
```

Set up the environment and install dependencies:

```bash
uv venv .env
source .env/bin/activate
uv pip install -r requirements-dev.txt
```

This repository contains the example dataset that we will process and analyse in the `inputs` folder.

## ⚙️ Data Processing

All steps for processing raw CellProfiler output into analysis-ready data are contained in:

📄 analysis/01_processing.ipynb

Processing is performed using [PyCytominer](https://github.com/cytomining/pycytominer), a standard toolkit for Cell Painting data normalization, feature selection, and aggregation.

## 🔍 Downstream analysis

Evaluate activity between compounds and the negative controls using mean average precision (mAP) with the ([copairs package](https://github.com/cytomining/copairs)), then cluster compounds according to their phenotypic profiles.

📄 analysis/02_analysis.ipynb

## 📚 Glossary

Here are some definitions that you may find helpful throughout the tutorial.

**Plates**  
Containers that hold multiple wells where cells are grown and treated with perturbations or compounds. Cell Painting experiments commonly use **96-well** or **384-well** plates.

**Wells**  
Individual compartments within a plate. Each well contains a population of cells exposed to a specific **perturbation**, **treatment**, or **control** condition.

**Batch**  
A group of plates processed together under similar experimental conditions (e.g., same day, same microscope, same operator). Batch information is critical for identifying and correcting **batch effects** — systematic differences unrelated to biology.

**Profiles**  
High-dimensional representations of cell morphology obtained after feature extraction. Each profile summarizes thousands of **features** that describe cellular shape, texture, and intensity across multiple imaging channels.

**Features**  
Quantitative measurements extracted from microscopy images (using software like CellProfiler). Examples include cell size, nuclear intensity, texture patterns, and spatial relationships between organelles. Features are often normalized and aggregated to create a **profile** per well, treatment, or cell population.

**Metadata**  
Contextual information describing each sample, such as plate ID, well position, compound name, concentration, gene target, or imaging parameters. Metadata allows linking image-derived features to experimental design and biological meaning.

**Perturbation / Treatment**  
The experimental condition applied to cells to induce a phenotype of interest.  
This can be:

- A **chemical compound** (e.g., drug or small molecule). The same chemical tested at **different concentrations**  
- A **genetic perturbation** (e.g., CRISPR knockout, RNAi, overexpression)  

**Replicate**  
Repeated experimental samples under identical conditions (same perturbation, same concentration).

**Channel**  
A fluorescence imaging band capturing a specific cellular component (e.g., nucleus, mitochondria, actin). Each channel provides complementary morphological information.

**Feature Aggregation**  
The process of combining single-cell features into summary statistics (e.g., mean, median) at the well or treatment level using tools like **PyCytominer**.

**Normalization**  
A data processing step to remove technical variability between wells or plates (e.g., z-score normalization, median-mAD scaling).

**Batch Effect**  
Systematic differences between samples introduced by technical variations between experiments or imaging runs. If batch is confounded with our biological variables of interest, it is nearly impossible to make robust inferences.
