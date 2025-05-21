### Scanning the Earth’s Surface for Water Bodies


A mini project that utilizes image processing techniques, specifically the Normalized Difference Water Index (NDWI), for detecting water bodies in satellite imagery. Implemented using Python libraries such as Rasterio and NumPy.

---

## Repository Structure

```
water-body-detection-satellite/
├── README.md
├── requirements.txt
├── data/
│   └── sample_image.tif               # Input satellite image
├── src/
│   ├── 01_data_collection.py
│   ├── 02_preprocessing.py
│   ├── 03_ndwi_calculation.py
│   ├── 04_thresholding.py
│   ├── 05_postprocessing.py
│   └── 06_evaluation.py
├── images/
│   ├── step1_original_image.png
│   ├── step2_preprocessed.png
│   ├── step3_ndwi_map.png
│   ├── step4_binary_mask.png
│   ├── step5_postprocessed.png
│   └── step6_groundtruth_comparison.png
├── results/
│   └── final_output.png
└── report/
    └── neeraj_detect_report.pdf
```

---
# 🛰️ Scanning the Earth’s Surface for Water Bodies

This project uses satellite imagery and image processing techniques (NDWI) to detect water bodies. Implemented in Python with detailed steps, scripts, and visual outputs.

---

## ✅ Steps

### 🔹 Step 1: Data Collection

We use satellite images from sources like **Landsat** or **Sentinel**. The essential bands required are the **NIR** and **Green** bands.


---
![1](https://github.com/user-attachments/assets/afa50f5d-b60b-4af0-915d-ff797abf95df)

### 🔹 Step 2: Preprocessing

Preprocessing involves:
- Reading image bands using `rasterio`
- Radiometric & geometric corrections
- Atmospheric correction (if needed)

---
![2](https://github.com/user-attachments/assets/fd417975-7a53-4bdd-ac52-fb19d02b5df8)

### 🔹 Step 3: NDWI Calculation

NDWI is calculated using:

```

NDWI = (Green - NIR) / (Green + NIR)

````
---

### 🔹 Step 4: Thresholding

Thresholding is used to separate water from non-water regions using NumPy:

```python
binary_mask = np.where(ndwi > threshold_value, 1, 0)
````


---
![3](https://github.com/user-attachments/assets/e4e46311-e5e5-45ad-ae31-dc9dbdf86f03)

### 🔹 Step 5: Post-processing

We apply morphological operations like erosion and dilation to clean the binary mask.

---
![4](https://github.com/user-attachments/assets/b488bac7-1a09-4e80-b0fe-e182b30461c1)

### 🔹 Step 6: Evaluation

We evaluate results using metrics like:

* Precision
* Recall
* F1-score


---

## 🛠️ Requirements

```bash
pip install rasterio numpy matplotlib scikit-image
```

---

## 📄 Project Report

See the full project report:
[neeraj_detect_report.pdf](https://github.com/user-attachments/files/20367355/neeraj_detect_report.pdf)


---

## 📚 References

* ISRO - [Indian Institute of Remote Sensing](https://www.iirs.gov.in/)
* McFeeters, 1996: NDWI Paper
* OpenAI (ChatGPT) for guidance

---
