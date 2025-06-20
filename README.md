# 🧭 Field Boundary Detection in Flevoland using Sentinel-2 and GEE

This project performs **supervised land segmentation** and **field boundary extraction** using Sentinel-2 imagery and the Google Earth Engine Python API. It focuses on the **Flevoland region in the Netherlands**, a well-known agricultural zone with highly structured fields, making it ideal for segmentation.

---

## 🎯 Objectives

- Classify land into **Field** vs. **Non-Field** areas using spectral features and NDVI.
- Perform **supervised segmentation** using manually labeled ground truth.
- Detect field boundaries via **Canny edge detection**.
- Vectorize the boundaries into usable shapefiles or overlays.

---

## 📍 Region of Interest

- **AOI**: Flevoland, Netherlands
- **Date Range**: July 1 – July 31, 2022 (peak crop season)
- **Satellite Data**: Sentinel-2 Surface Reflectance (S2_SR_HARMONIZED)

---

## 🧪 Methodology Overview

1. **AOI Definition**: Use a rectangle over Flevoland.
2. **Image Processing**:
   - Filter Sentinel-2 images for July 2022 with <10% cloud cover.
   - Apply cloud and cirrus masking.
   - Calculate NDVI.
   - Generate a median composite image.
3. **Ground Truth Creation**:
   - Manually define polygons for “Field” and “Non-Field” areas.
4. **Classification**:
   - Train a Random Forest classifier (20 trees).
   - Classify pixels into binary classes.
5. **Edge Detection**:
   - Use Canny edge detector to detect sharp land transitions.
   - Convert detected edges into binary format.
   - Vectorize edge pixels into polygons.
6. **Visualization**:
   - Display RGB composite, classification map, and vector boundaries using `geemap`.

---

## 🎨 Class Definitions

| Class      | Value | Color   |
|------------|--------|---------|
| Field      | 1      | Green   |
| Non-Field  | 0      | Gray    |

---

## 🗺️ Outputs

- 🌾 **Field vs. Non-Field Classification Map**
- 🧱 **Detected Field Boundaries** (converted to vector lines)
- 🖼️ **RGB Composite** for visual inspection

---

## 🛠️ Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/YOUR_USERNAME/field-boundary-segmentation.git
cd field-boundary-segmentation
