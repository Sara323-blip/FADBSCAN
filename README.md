# FADBSCAN: Firefly Algorithm Optimized DBSCAN Clustering

## Overview

FADBSCAN is a hybrid clustering framework that combines the Firefly Algorithm (FA) with DBSCAN to automatically optimize DBSCAN's sensitive parameters ($\varepsilon$ and MinPts). The algorithm uses swarm intelligence to explore the parameter space and find optimal configurations that maximize clustering quality.

## Key Features

- **Automatic Parameter Tuning**: No manual selection of $\varepsilon$ and MinPts required
- **Fitness Function**: $F = 0.5 \times Silhouette - 0.5 \times DBI - 0.2 \times NoiseRatio$
- **Parameter Bounds**: $\varepsilon \in [0.05, 2.0]$, MinPts $\in [2, 20]$
- **Multiple Algorithm Comparison**: Benchmarks 11 clustering algorithms including KMeans, MeanShift, Spectral, OPTICS, BIRCH, GMM, and DBSCAN variants

## Algorithm Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| `num_fireflies` | 50 | Population size |
| `max_generations` | 50 | Number of iterations |
| `beta` | 1.0 | Attractiveness coefficient |
| `alpha` | 0.2 | Randomization coefficient |
| $\varepsilon$ range | [0.05, 2.0] | Neighborhood radius |
| MinPts range | [2, 20] | Minimum points for core point |

## Datasets

The code generates 6 synthetic datasets (500 samples each):

| Dataset | Description |
|---------|-------------|
| Noisy Circles | Concentric circles with noise |
| Noisy Moons | Crescent-shaped clusters |
| Blobs | Gaussian clusters |
| No Structure | Uniform random noise |
| Anisotropic | Stretched/elongated clusters |
| Varied Variances | Clusters with different densities |

## Output

For each dataset and algorithm, the code prints:
- Silhouette Score (higher is better)
- Davies-Bouldin Index (lower is better)
- Optimized parameters for FADBSCAN


## Usage

```python
# Run the complete comparison
python fadbscan.py
