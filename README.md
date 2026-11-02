
# Cherry Leaf Disease Severity Analysis

An image-processing-based approach for analyzing cherry leaf health and disease severity using computer vision, feature extraction, and K-Means clustering.

## Overview

This project explores the analysis of cherry leaf diseases, particularly Powdery Mildew, through image processing techniques. It focuses on identifying disease-affected regions, extracting measurable image features, and analyzing variations between healthy and diseased leaves.

The project uses computer vision techniques to segment leaf regions, enhance image contrast, identify potential disease areas, and quantify disease-related characteristics.

## Objectives

- Segment cherry leaves from their backgrounds.
- Identify potential disease-affected regions within leaf boundaries.
- Extract quantitative image features associated with disease severity.
- Apply K-Means clustering for disease severity grouping.
- Compare healthy and diseased leaf characteristics through statistical analysis and visualizations.

## Methodology

### 1. Leaf Image Segmentation
- Convert images into HSV color space.
- Identify green leaf regions using color thresholds.
- Apply morphological operations to remove noise and fill gaps.
- Extract the largest connected component to isolate the leaf.

### 2. Image Enhancement
- Convert images into LAB color space.
- Apply Contrast Limited Adaptive Histogram Equalization (CLAHE).
- Enhance image contrast to improve the visibility of potential disease regions.

### 3. Disease Region Extraction
- Identify potential disease regions using HSV and LAB color characteristics.
- Detect low-saturation and bright regions.
- Restrict candidate disease regions to the segmented leaf area.
- Apply morphological operations to reduce noise.

### 4. Feature Extraction

The analysis focuses on the following image features:

| Feature | Description |
|---|---|
| Coverage | Percentage of leaf area identified as potentially affected |
| Patches | Number of detected disease regions |
| Largest Patch | Area of the largest detected region |
| Average Patch | Average size of detected regions |
| Brightness | Image brightness characteristics |

### 5. K-Means Clustering

K-Means clustering is used in the project workflow to group cherry leaf images into severity categories:

- Healthy
- Early
- Moderate
- Severe

The final dataset contains 4,386 image records with the following expected distribution:

| Severity Stage | Images |
|---|---:|
| Healthy | 2,282 |
| Early | 1,156 |
| Moderate | 834 |
| Severe | 114 |
| **Total** | **4,386** |

### 6. Statistical Analysis and Visualization

The project includes:
- Healthy versus Powdery Mildew feature comparisons.
- Mean and median feature analysis.
- Statistical summaries.
- Box plots and feature distribution visualizations.
- Normalized feature comparisons.

## Technology Stack

- Python
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn (K-Means workflow)
- Google Colab
- Google Drive

## Dataset

The project uses cherry leaf images belonging to healthy and Powdery Mildew categories.

The processed dataset is maintained as a CSV file containing image paths, severity stages, original classes, and extracted image features.

**Note:** Dataset files and original images are not included in this repository.

## Project Structure

```text
cherry-leaf-disease-analysis/
│
├── notebooks/
│   └── cherry_disease_analysis.ipynb
│
├── results/
│   └── feature_visualizations/
│
├── README.md
└── requirements.txt
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/cherry-leaf-disease-analysis.git

cd cherry-leaf-disease-analysis
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Upload the notebook to Google Colab or open it using Jupyter Notebook.

### 4. Configure the dataset

Update the dataset and image paths according to your local environment or Google Drive directory.

### 5. Run the analysis

Execute the notebook cells sequentially to perform image processing, feature analysis, and visualization.

## Limitations

- Color-based disease region extraction depends on image quality and lighting conditions.
- Brightness and saturation thresholds may identify non-disease regions as candidates.
- The extracted image features are indicators for analysis and do not independently establish a clinical or agricultural diagnosis.
- Results depend on the quality and consistency of the input images.

## Future Improvements

- Improve disease-region segmentation using advanced computer vision techniques.
- Evaluate clustering performance against manually annotated severity labels.
- Explore machine learning and deep learning approaches for disease classification.
- Develop an interactive interface for uploading and analyzing leaf images.

## License

This project is available for educational and research purposes.
