# Motion Blur Object Detection Benchmark

**Benchmarking Motion Blur Robustness in Modern Object Detectors**

A comparative robustness study of modern object detection architectures under severe motion blur degradation.

---

## **Overview**

Object detection models achieve impressive performance on standard benchmarks, but real-world deployment often involves degraded visual conditions such as motion blur, noise, adverse weather, and low-light environments.

This project investigates how different object detection paradigms respond to severe motion blur. The study evaluates:

* **YOLOv8n**
* **YOLOv8s**
* **RT-DETR-L**
* **GroundingDINO**

Unlike traditional evaluations that focus primarily on mAP, this benchmark emphasizes robustness-oriented metrics including detection retention and confidence retention under image degradation.

---

## **Abstract**

Motion blur is a common challenge in surveillance systems, autonomous vehicles, robotics, and mobile imaging.

This study presents a comparative benchmark of **YOLOv8**, **RT-DETR**, and **GroundingDINO** under controlled motion blur conditions.

Experimental results demonstrate substantial performance degradation across all models. **RT-DETR** exhibits the strongest robustness, maintaining significantly higher detection and confidence retention rates under severe blur, while YOLO-based detectors experience the largest performance drop.

The findings highlight the importance of evaluating robustness beyond conventional benchmark accuracy and provide insights into architectural behavior under degraded visual conditions.

---

## **Key Findings**

| Model         | Detection Retention Rate (DRR) | Confidence Retention Rate (CRR) |
| ------------- | ------------------------------ | ------------------------------- |
| YOLOv8n       | 23.2%                          | 53.3%                           |
| YOLOv8s       | 22.9%                          | 56.4%                           |
| RT-DETR-L     | 46.4%                          | 77.8%                           |
| GroundingDINO | 39.0%                          | 85.6%                           |

---

## **Main Observations**

* **RT-DETR** demonstrated the highest robustness under severe motion blur.
* **YOLOv8** variants suffered substantial detection degradation.
* **GroundingDINO** retained partial object understanding through vision-language alignment.
* Architectural design significantly influences robustness to image degradation.

---

## **Dataset**

* **100 images** sampled from the COCO Validation dataset
* Corresponding motion-blurred versions generated using OpenCV
* **Total evaluated images:** 200

---

## **Motion Blur Configuration**

| Blur Level | Kernel Size |
| ---------- | ----------- |
| Light      | 15          |
| Medium     | 25          |
| Heavy      | 45          |

Results reported in the manuscript correspond to the **Heavy Blur** setting (**Kernel Size = 45**).

---

## **Evaluation Metrics**

### **Detection Retention Rate (DRR)**

```text
DRR (%) =
(Average Detections on Blurred Images /
 Average Detections on Original Images) × 100
```

### **Confidence Retention Rate (CRR)**

```text
CRR (%) =
(Average Confidence on Blurred Images /
 Average Confidence on Original Images) × 100
```

---

## **Models Evaluated**

### **YOLOv8n**

Lightweight CNN-based detector optimized for speed and efficiency.

### **YOLOv8s**

Higher-capacity YOLO variant with improved feature representation.

### **RT-DETR-L**

Transformer-based detector leveraging global attention mechanisms.

### **GroundingDINO**

Vision-language detector capable of open-vocabulary object detection.

---

## **Experimental Environment**

### **Hardware**

* NVIDIA Tesla T4 GPU
* Google Colab High-RAM Environment

### **Software**

| Package      | Version            |
| ------------ | ------------------ |
| Python       | 3.11               |
| PyTorch      | 2.11.0 + CUDA 12.8 |
| Ultralytics  | 8.4.60             |
| OpenCV       | 4.13.0             |
| Transformers | 5.0.0              |
| NumPy        | 2.0.2              |
| Pandas       | 2.2.2              |

---

## **Manuscript**

The current version of the manuscript is available in this repository:

```text
paper/Benchmarking_Motion_Blur_Robustness.pdf
```

---

## **Publication Status**

### **Research Manuscript Status**

This work is currently available as a repository manuscript.

The paper is undergoing further review and refinement. A preprint version is planned for future submission to arXiv.

Until an official preprint is released, please cite this repository or contact the author directly regarding the manuscript.

---

## **Future Work**

* Larger-scale evaluation on additional datasets
* Robustness benchmarking under:

  * Gaussian noise
  * Low-light conditions
  * Rain and fog
  * Compression artifacts
* Integration of localization-based metrics (**mAP**, **IoU**)
* Statistical significance analysis
* Extension to additional detector architectures and multimodal models

---

## **Author**

### **Hemashree P**

Independent Researcher, India

**Areas of Interest**

* Machine Learning
* Computer Vision
* Explainable AI
* Robust AI Systems
* Medical AI
* Multimodal Learning

---

## **Citation**

```bibtex
@misc{hemashree2026motionblurbenchmark,
  author = {Hemashree P},
  title = {Benchmarking Motion Blur Robustness in Modern Object Detectors: A Comparative Study of YOLOv8, RT-DETR, and GroundingDINO},
  year = {2026},
  note = {Manuscript available via GitHub repository. arXiv submission planned.}
}
```

---

## **License**

This repository is released for academic and research purposes.

Please provide appropriate attribution if referencing the manuscript, code, or experimental findings.

---

## **Note**

The original implementation was developed in Google Colab.

Due to GitHub notebook rendering limitations, the source code is provided as a Python script (`.py`) instead of a Jupyter notebook (`.ipynb`).
