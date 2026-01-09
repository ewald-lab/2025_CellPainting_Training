# 🧪 Ewald Lab Training on Cell Painting Data
Welcome to the Ewald Lab Cell Painting Training Repository!
This repository provides a step-by-step tutorial for learning how to process, evaluate, and analyze Cell Painting datasets — from raw CellProfiler outputs to meaningful biological insights.
# 📘 Overview
The **Cell Painting assay** is a high-content imaging approach that captures morphological features of cells across multiple fluorescent channels.

This tutorial walks you through:
- Setting up the environment
- Processing CellProfiler output data
- Evaluating data quality and reproducibility
- Performing downstream analyses to link morphological profiles with biological activity

# 🧭 Learning Objectives
By the end of this tutorial, you will be able to:
- Understand the Cell Painting workflow from image data to feature-level insights
- Use PyCytominer to process, normalize, aggregate data
- Evaluate data reproducibility and activity using GRIT and mAP metrics
- Perform biological interpretation of morphological profiles
  
# 🧰 1. Prerequisites & Environment Setup
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
# 📂 2. Data Preparation
You will need a Cell Painting dataset processed with CellProfiler.
Typical input data includes:
Image-based features (*.csv or *.parquet)
Metadata files (e.g., plate map, compound annotations)
If you do not yet have a dataset, you can download a public Cell Painting dataset, such as those available from the Broad Institute Cell Painting Gallery.

[TODO] Give details of the different files

# ⚙️ 3. Data Processing
All steps for processing raw CellProfiler output into analysis-ready data are contained in:

📄 01_processing/01_processing.ipynb

Processing is performed using [PyCytominer](https://github.com/cytomining/pycytominer), a standard toolkit for Cell Painting data normalization, feature selection, and aggregation.
# 🔍 4. Experiment Evaluation
Evaluate data quality, reproducibility, and activity:

📄 01_processing/02_evaluate.ipynb

This notebook includes:
- Replicate correlations — assess consistency between replicates
- GRIT score — evaluate phenotypic strenght ([GRIT](https://github.com/broadinstitute/grit-benchmark))

For more imformation on the replicate correlation and the grit score see the [cytominer-eval package](https://github.com/cytomining/cytominer-eval).

- Mean Average Precision (mAP) — assess intra- vs inter-group similarities ([copairs package](https://github.com/cytomining/copairs)).
# 📊 5. Downstream Analysis
After evaluation, continue with biological interpretation and visualization.

📄 03_downstream_analysis/03_analysis_evaluation.ipynb

Explore generated evaluation data:
- Explore experimental setup
- Correlation between replicates
- Grit and AP (average precision) per plates

📄 03_downstream_analysis/04_results_analysis.ipynb

Dive deeper into:
- Linking morphology to biological mechanisms
- Comparing compound activities
