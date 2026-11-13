# Hyperspectral Image Band Selection Using Correlation-Based and Neighborhood-Based Partitioning

## Project Overview

This project focuses on reducing spectral dimensionality in hyperspectral images using a combination of correlation-based and neighborhood-based band selection techniques.

The proposed approach assigns priority scores to spectral bands based on their correlation information and spatial neighborhood consistency. The top 30 bands are then selected and used for hyperspectral image classification with a 3D Convolutional Neural Network (3D CNN).

The experiments are performed using the **Indian Pines Hyperspectral Dataset**.

## Google Colab Notebook

The complete Python implementation is available on Google Colab:

**[Open the Google Colab Notebook](https://colab.research.google.com/drive/1fK_U4rsQ6ssGIfQTroas-HXpo9bVKqm4?usp=sharing)**

## Dataset Files Required

Before executing the notebook, make sure you have the following three dataset files:

1. `Indian_pines.mat`
2. `Indian_pines_corrected.mat`
3. `Indian_pines_gt.mat`

These files are already included in this GitHub repository.

### Uploading Dataset Files to Google Colab

Follow these steps before running the notebook:

1. Open the Google Colab notebook using the link above.
2. Download the three `.mat` dataset files from this GitHub repository.
3. In Google Colab, open the **Files** panel from the left sidebar.
4. Click the **Upload** button.
5. Select and upload all three dataset files:
   - `Indian_pines.mat`
   - `Indian_pines_corrected.mat`
   - `Indian_pines_gt.mat`
6. Wait until all three files appear in the Colab file panel.
7. Execute the notebook cells in their intended order.

**Important:** All three files must be uploaded to the active Google Colab session before executing the dataset-loading cells. Colab runtime files may be cleared when the session is restarted, so you may need to upload them again.

## Methodology

The project follows these major stages:

1. **Dataset Loading:** Load the Indian Pines hyperspectral image and ground-truth labels.
2. **Preprocessing:** Normalize spectral data and construct spatial patches.
3. **Correlation-Based Partitioning:** Identify highly correlated spectral bands using a correlation threshold.
4. **Neighborhood-Based Partitioning:** Evaluate spatial neighborhood consistency across spectral bands.
5. **Priority Score Calculation:** Combine normalized correlation information and neighborhood consistency.
6. **Band Selection:** Select the 30 highest-priority spectral bands from the original 200 bands.
7. **3D CNN Classification:** Train a 3D CNN using the selected spectral bands.
8. **Performance Evaluation:** Evaluate classification using accuracy, precision, recall, F1-score and Cohen's Kappa.

## Technologies Used

- Python
- Google Colab
- PyTorch
- NumPy
- Pandas
- SciPy
- Scikit-learn
- Matplotlib
- Seaborn

## Dataset Information

| Property | Description |
|---|---|
| Dataset | Indian Pines |
| Image dimensions | 145 × 145 × 200 |
| Original spectral bands | 200 |
| Land-cover classes | 16 |
| Selected spectral bands | 30 |
| Patch size | 5 × 5 |
| Classification model | 3D CNN |

## Proposed Band Selection

The combined priority score is calculated using:

\[
P_i = 0.5\hat{C}_i + 0.5S_i
\]

Where:

- \(\hat{C}_i\) represents normalized correlation information.
- \(S_i\) represents normalized neighborhood consistency.
- \(P_i\) represents the final priority score of spectral band \(i\).

The 30 bands with the highest priority scores are selected for classification.

## Experimental Results

The proposed Priority 30-band approach achieved the following recorded results:

| Metric | Result |
|---|---:|
| Overall Accuracy | 81.8537% |
| Average Accuracy | 71.9472% |
| Cohen's Kappa | 0.7923 |
| Macro Precision | 82.1168% |
| Macro Recall | 71.9472% |
| Macro F1-score | 74.3956% |

These results correspond to the saved prediction arrays evaluated in the project notebook.

## Repository Contents

- **Google Colab Notebook:** Complete implementation and experiments.
- **Dataset Files:** Indian Pines `.mat` files required to run the notebook.
- **Experimental Figures:** Visualizations of band selection, model architecture and classification performance.
- **Project Report:** Detailed project methodology and experimental discussion.

## How to Run

1. Open the Google Colab notebook.
2. Upload the three required `.mat` files.
3. Run the notebook cells in order.
4. Observe the band-selection process and selected spectral bands.
5. Train and evaluate the 3D CNN.
6. Review the generated performance metrics and visualizations.

---

**Project Type:** B.Tech Minor Project  
**Department:** Information Technology  
**Institution:** National Institute of Technology Raipur
