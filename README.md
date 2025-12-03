# Radiometric Clustering Analysis - Southwest UK

2 types of visualisation and a K-means clustering analysis of airborne radiometric survey data to classify geological units across Southwest England.

## Overview

Uses 853,000+ measurement points from the Tellus South West survey to identify distinct geological zones based on potassium, uranium, and thorium signatures. Identifies all five major granite plutons in Cornwall and Devon.

## Notebooks

1. **`01_pyplot_radiometrics.ipynb`** - Data exploration and hexbin visualization
2. **`02_folium_radiometrics.ipynb`** - Interactive folium heatmap (generates large HTML file)
3. **`03_k_means_clustering_analysis.ipynb`** - Main clustering analysis and results

## Outputs

All visualizations in `output/` directory:
- `cluster_optimization.png` - Elbow method and silhouette analysis
- `cluster_profiles.png` - Radar charts of cluster signatures
- `radiometric_clusters_map.png` - Final geological classification map

## Data

Download from [BGS Tellus South West](https://www.bgs.ac.uk/datasets/tellus-south-west/):
- File: `TellusSW_RAD_ALL.csv`
- Place in: `data/` directory

## Requirements

```bash
pip install numpy pandas matplotlib scikit-learn folium
```

## Method

- Feature engineering: K/Th, Th/U, K/U ratios
- MiniBatchKMeans with k=6 (selected via elbow method and silhouette analysis)
- Validated against BGS geological maps
