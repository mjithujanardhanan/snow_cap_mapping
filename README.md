# 🏔️ Snow Cover Mapping in Indian Himalayas using Machine Learning

This project uses satellite imagery and machine learning techniques to map snow cover in the Indian Himalayan region. It combines classical remote sensing indices like NDSI/NDFSI with modern image segmentation using U-Net to estimate fractional snow cover area with high precision.

## 📌 Overview

- **Goal**: Accurately map and quantify snow-covered regions in the Himalayas using Landsat 8 satellite data.
- **Techniques**: Raster Indexing (NDSI/NDFSI), K-means Clustering, Deep Learning (U-Net)
- **Tools**: QGIS, Python, Keras, TensorFlow, NumPy, Landsat 8 satellite data

## ❄️ Objectives

- Acquire and preprocess Landsat 8 data
- Segment satellite imagery to distinguish snow-covered pixels
- Combine classical NDSI/NDFSI indices with deep learning methods
- Estimate fractional snow cover and compute snow-covered area in sq. km

## 🛰️ Data & Tools

- **Satellite Data**: Landsat 8 (Bands 2, 3, 4, 5, 6)
- **Platform**: [USGS Earth Explorer](https://earthexplorer.usgs.gov/)
- **Software**:
  - QGIS (for raster operations and NDSI/NDFSI mask generation)
  - Python (for training U-Net and post-processing)
  - TensorFlow & Keras (for model development)

## 📊 Methodology

### ✅ Classical Remote Sensing

- **NDSI (Normalized Difference Snow Index)**  
  Formula: `(Green - SWIR) / (Green + SWIR)`  
  Threshold: 0.4

- **NDFSI (Normalized Difference Forested Snow Index)**  
  Formula: `(NIR - SWIR) / (NIR + SWIR)`  
  Threshold: 0.4

- Used QGIS Raster Calculator to create snow masks using the above indices

### 🧠 Machine Learning

- **K-means Clustering**:
  - Unsupervised clustering into 3 clusters to identify snow pixels (based on intensity)
  - Used as a baseline method

- **U-Net for Image Segmentation**:
  - Input: Landsat Bands 3, 5, 6
  - Output: Binary mask of snow-covered area
  - Trained on NDFSI-generated masks as ground truth

### 📐 Area Estimation

- Landsat resolution: 30m × 30m = 900 m²/pixel
- Formula: `Total Snow Area = (#snow pixels × 900) / 1e6 (sq. km)`

## 📈 Results

- **Date of Observation**: August 20, 2023
- **Area Analyzed**: Region around Sikkim, extending to parts of China, Nepal, and Bhutan
- **Estimated Snow Cover**:  
  - 4371 snow pixels  
  - Snow cover %: ~6.67%  
  - Total region area: 33300 sq.km  
  - Estimated snow-covered area: **~2221 sq.km**

## 📁 Directory Structure

