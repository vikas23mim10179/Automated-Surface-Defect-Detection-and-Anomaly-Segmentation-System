# Automated Surface Defect Detection and Anomaly Segmentation System

**Course:** Computer Vision  
**Student Name:** Vikas Mewada  
**Registration Number:** 23MIM10179  
**Submission Date:** 13-10-2026

## 1. Abstract

This project presents an automated computer vision solution for detecting surface anomalies and structural defects in high-resolution images. The system uses OpenCV and Python to identify irregularities through adaptive thresholding, edge detection, morphological operations, and contour analysis. It measures defect areas and generates annotated output images and machine-readable JSON reports. The system operates entirely through a command-line interface (CLI), reducing the need for manual inspection and supporting automated quality control in industrial applications.

## 2. Problem Statement and Objectives

### Problem Statement

Manual surface inspection in manufacturing and production processes is time-consuming, subjective, and prone to human error. Small cracks, scratches, and other surface irregularities may be overlooked, potentially affecting product quality and reliability.

### Objectives

1. Develop an automated defect detection pipeline using Python and OpenCV.
2. Detect and segment surface anomalies in input images.
3. Execute the complete workflow through a command-line interface without GUI dialogs.
4. Extract defect contours and calculate their spatial areas.
5. Generate annotated output images and export detection metrics in JSON format.
6. Evaluate the system using defect count, processing time, and total defect area.

## 3. Methodology and System Architecture

The system follows a sequential image-processing pipeline.

### 3.1 Image Preprocessing

The input image is converted into grayscale to simplify intensity analysis. Bilateral filtering is then applied to reduce image noise while preserving important edges.

### 3.2 Defect Segmentation

Morphological gradient operations highlight local intensity changes and surface boundaries. Canny edge detection extracts prominent edges, while adaptive thresholding can help distinguish potential defects from varying background illumination.

### 3.3 Contour Extraction and Classification

The resulting binary image is analyzed to extract contours. Contour measurements, bounding boxes, and geometric properties such as area and eccentricity can be used to characterize potential defects. Appropriate filtering thresholds help reduce false detections.

### 3.4 Output and Report Generation

The system draws bounding boxes and contours around detected regions. It saves the annotated image and exports a JSON summary containing detection metrics, including defect count, defect area, and contour information.

### System Architecture

```text
        Input Surface Image
                 |
                 v
       Grayscale Conversion
                 |
                 v
        Bilateral Filtering
                 |
                 v
       Image Segmentation
                 |
                 v
   Morphological Gradient +
       Canny Edge Detection
                 |
                 v
       Contour Extraction
                 |
                 v
       Defect Measurement
                 |
          +------+------+
          |             |
          v             v
   Annotated Image   JSON Report
          |             |
          +------+------+
                 |
                 v
       Performance Evaluation
```

## 4. Experimental Results and Performance

The system is evaluated using sample surface images with different resolutions and defect patterns. The evaluation considers the number of detected defects, processing time, and percentage of image area classified as defective.

### Performance Metrics

| Image Sample | Resolution | Defects Detected | Processing Time (ms) | Total Defect Area (%) |
|---|---|---:|---:|---:|
| Sample 01 | 1920 × 1080 | 3 | 42 | 4.12% |
| Sample 02 | 1920 × 1080 | 0 | 38 | 0.00% |
| Sample 03 | 1280 × 720 | 5 | 27 | 7.85% |

**Note:** The values above are example results provided for the project report. Replace them with actual measurements obtained by running the implemented system before final submission. Defect counts alone do not establish detection accuracy; ground-truth annotations are required to calculate metrics such as precision, recall, and F1-score.

### Required Screenshots

Include the following screenshots in the final project report:

- **Terminal Execution:** Command-line command used to run the program and the execution completion logs.
- **Input Image:** The original `sample_input.jpg` image.
- **Output Image:** The annotated image generated in the `data/results/` directory.
- **Comparison:** A side-by-side comparison of the original and processed images.
- **JSON Report:** The generated JSON file containing the detection results.

## 5. Technologies Used

- **Programming Language:** Python
- **Computer Vision Library:** OpenCV
- **Numerical Processing:** NumPy
- **Data Export:** JSON
- **Execution Environment:** Command-Line Interface (CLI)

## 6. Project Directory Structure

```text
surface-defect-detection/
├── main.py
├── requirements.txt
├── README.md
├── sample_input.jpg
└── data/
    └── results/
        ├── annotated_output.jpg
        └── detection_report.json
```

The exact filenames may vary depending on the implementation.

## 7. Applications

- Industrial quality inspection
- Manufacturing defect detection
- Crack and scratch identification
- Automated product inspection
- Surface quality monitoring
- Preliminary anomaly screening in production lines

## 8. Limitations and Future Enhancements

The current image-processing approach may be sensitive to lighting conditions, surface texture, and parameter selection. It may also identify normal texture variations as defects or miss subtle anomalies.

Future improvements may include:

1. Using deep learning models such as CNNs or anomaly detection networks.
2. Training and evaluating the system on labeled industrial defect datasets.
3. Adding precision, recall, F1-score, and intersection over union (IoU) metrics.
4. Improving robustness under different lighting and surface conditions.
5. Integrating real-time camera input and automated inspection workflows.

## 9. Conclusion

The Automated Surface Defect Detection and Anomaly Segmentation System demonstrates how traditional computer vision techniques can support automated surface inspection. By combining image preprocessing, segmentation, edge detection, and contour analysis, the system identifies potential defect regions and generates visual and machine-readable outputs. The project provides a foundation for further development toward more robust and intelligent industrial quality control systems.

## 10. References

1. Bradski, G. (2000). The OpenCV Library. *Dr. Dobb's Journal of Software Tools*.
2. Canny, J. (1986). A Computational Approach to Edge Detection. *IEEE Transactions on Pattern Analysis and Machine Intelligence*, (6), 679–698. https://doi.org/10.1109/TPAMI.1986.4767851

---

**Project Author:** Vikas Mewada  
**Registration Number:** 23MIM10179  
**Course:** Computer Vision
