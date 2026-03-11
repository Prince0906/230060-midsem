# Dataset Information

## Source
The **Olivetti Faces** dataset from AT&T Laboratories Cambridge is used as the toy dataset for reproducing the Improved Fisher Kernel method from "Improving the Fisher Kernel for Large-Scale Image Classification" (Perronnin et al., ECCV 2010).

## Dataset
- **Name:** Olivetti Faces (AT&T)
- **Source:** `sklearn.datasets.fetch_olivetti_faces()` — auto-downloaded and cached by scikit-learn
- **Samples:** 400 grayscale face images (64×64 pixels)
- **Classes:** 40 individuals (10 images per person)
- **Features:** 4,096 raw pixel values per image; local descriptors are 8×8 patches (64-D each)
- **Problem type:** Multi-class image classification

## Files in This Folder
- **`olivetti_faces.npz`** — The full Olivetti Faces dataset saved as a NumPy archive containing:
  - `images`: 400 grayscale images of shape (400, 64, 64)
  - `data`: Flattened pixel data of shape (400, 4096)
  - `target`: Class labels (0–39) of shape (400,)

## How to Obtain
The dataset can be loaded from the local file (`olivetti_faces.npz`) or auto-downloaded via `sklearn.datasets.fetch_olivetti_faces()` on first notebook run. The data is cached in `~/scikit_learn_data/`.

## Usage in Notebooks
- **task_2_1.ipynb:** Loads dataset, performs stratified 50/50 split, extracts dense 8×8 patches
- **task_2_2.ipynb:** Runs full Fisher Vector pipeline (PCA → GMM → FV → normalizations → SVM)
- **task_2_3.ipynb:** Reproduces pipeline for result comparison and visualization
- **task_3_1.ipynb:** Ablation study on power and L2 normalizations
- **task_3_2.ipynb:** Failure mode experiment with occluded test images

## Preprocessing
1. Stratified train/test split (50/50, random_state=42)
2. Dense 8×8 patch extraction on 6-pixel grid with small noise (σ=0.05)
3. PCA reduction to 32 dimensions
4. All preprocessing is documented within each notebook
