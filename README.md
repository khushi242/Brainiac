# Brainiac

Brainiac is an AI-powered brain tumor analysis project built around a **3D medical imaging pipeline** for MRI volumes.  
It combines **preprocessing, Swin UNETR-based tumor segmentation, explainability, counterfactual analysis, and downstream risk modeling** into one structured workflow.

## Project Overview

This project is designed to work on multi-modal brain MRI data and support a step-by-step research pipeline:

- preprocess raw MRI scans
- prepare 3D inputs for deep learning
- segment tumor regions using **Swin UNETR**
- analyze model behavior using **attention / explainability**
- generate **counterfactuals** and CSS-style interpretation
- build downstream **risk / decision support** components

The goal is not only to detect or segment tumors, but also to make the system **more interpretable and research-oriented**.

---

## Core Features

- **3D MRI preprocessing pipeline**
- **Swin UNETR segmentation**
- support for multi-modal MRI volumes
- explainability and feature analysis
- counterfactual / CSS-based interpretation workflow
- notebook-based experimentation
- modular structure for further expansion

---

## Model / Research Pipeline

The Brainiac workflow is organized as a staged pipeline:

### 1. Data Preparation
Raw MRI scans are loaded, cleaned, organized, and prepared for downstream training/inference.

Typical tasks include:
- reading MRI volumes
- aligning expected file structure
- separating modalities
- normalizing / resizing data
- preparing masks / labels

### 2. Slice / Volume Extraction
Depending on the experiment, the project may extract slices or prepare 3D patches/volumes for model input.

### 3. Tumor Segmentation
The main segmentation backbone is **Swin UNETR**, which is well-suited for volumetric medical imaging because it combines:
- transformer-style global representation
- UNet-like decoding
- strong spatial modeling for 3D scans

### 4. Explainability
The project includes interpretability-oriented steps such as:
- attention-based inspection
- feature map analysis
- model behavior understanding

### 5. Counterfactual / CSS Analysis
This stage explores what changes in the input may affect model behavior or decision confidence, helping make the system more explainable.

### 6. Risk / Downstream Analysis
The segmented outputs and derived features can be used for later-stage risk modeling and research analysis.

---

## Why Swin UNETR?

Swin UNETR is a strong choice for this project because it offers:

- excellent performance on **3D medical imaging**
- ability to capture both **local and global context**
- strong representation learning for tumor regions
- better suitability for volumetric scans than many plain 2D models
- compatibility with modern MONAI-style research workflows

---

## Repository Structure

A typical structure for this repo looks like:

```text
Brainiac/
│
├── code/                    # main notebooks / code used in the project
├── data/                    # dataset folder (keep large data out of GitHub if needed)
├── models/                  # saved model weights
├── results/                 # outputs, predictions, plots, metrics
├── README.md
└── requirements.txt
```

If your repo currently only contains the `code/` folder, that is completely fine.  
You can expand the structure later as your project grows.

---

## Recommended Notebook Flow

If your `code/` folder contains multiple notebooks, run them in a logical order like this:

1. **preprocessing / extraction notebook**
2. **training notebook**
3. **inference / evaluation notebook**
4. **explainability notebook**
5. **counterfactual / CSS notebook**
6. **risk-model or downstream analysis notebook**

If you renamed files for clarity, make sure the order still matches the pipeline.

---

## Dataset

This project is designed for **brain MRI tumor datasets** with multiple modalities.  
A common setup includes volumes such as:

- T1
- T1CE
- T2
- FLAIR
- segmentation masks

If you are using a dataset like **BraTS**, keep in mind:

- large datasets should usually **not** be pushed to GitHub
- instead, store them locally, in cloud storage, or in Google Drive
- document the expected dataset folder structure in your notebooks

---

## Installation

Clone the repo:

```bash
git clone https://github.com/khushi242/Brainiac.git
cd Brainiac
```

Install dependencies:

```bash
pip install -r requirements.txt
```

If you are working in a notebook environment, also make sure your Jupyter kernel uses the correct Python environment.

---

## Typical Dependencies

Depending on your notebooks, the project may use:

- Python 3.10+
- Jupyter Notebook / JupyterLab
- PyTorch
- MONAI
- NumPy
- Pandas
- Matplotlib
- scikit-learn
- nibabel
- tqdm

If you have not yet created a `requirements.txt`, you can generate one later after finalizing the environment.

---

## How to Run

### Option 1: Jupyter Notebook
Open the notebooks:

```bash
jupyter notebook
```

Then open the notebooks inside `code/` and run them in sequence.

### Option 2: VS Code
- open the `Brainiac` folder in VS Code
- open the notebook inside `code/`
- select the correct Python kernel
- run cells step by step

### Option 3: Google Colab
If your workflow is in Colab:
- upload the notebook
- mount Google Drive if needed
- update dataset paths accordingly

---

## Outputs

The project can produce outputs such as:

- segmented tumor masks
- training metrics
- evaluation plots
- feature maps
- explainability visualizations
- counterfactual results
- derived risk features / tables

---

## Current Status

This project is an active research-style pipeline and may still be evolving.  
Some notebooks may represent:
- intermediate experiments
- renamed cleaned versions
- explainability-focused prototypes
- model comparison work

That is normal for a research workflow.

---

## Notes for GitHub

Large files should usually be excluded from the repo, including:

- raw datasets
- trained model weights
- generated caches
- temporary notebook checkpoints
- zipped archives

Recommended `.gitignore` entries include:

```gitignore
.DS_Store
.ipynb_checkpoints/
__pycache__/
data/
models/
results/
*.pt
*.pth
*.ckpt
*.zip
```

---

## Future Improvements

Possible next steps for Brainiac:

- add a clean `requirements.txt`
- add sample output images
- add an architecture diagram
- add evaluation metrics table
- add a proper inference script
- package notebooks into reusable modules
- add a small demo for prediction / visualization

---

## Author

**Khushi**  
B.Tech AI & ML Student  
Project: **Brainiac**

---

## License

Add a license here if you plan to make the repository public for reuse.
