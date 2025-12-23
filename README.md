# 🚦 Traffic Flow Analysis with Computer Vision

![Status](https://img.shields.io/badge/Status-Active-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Computer%20Vision](https://img.shields.io/badge/Computer_Vision-OpenCV-orange)
![Object%20Detection](https://img.shields.io/badge/Object_Detection-YOLOv5-red)
![License](https://img.shields.io/badge/License-BSD--3--Clause-green)

This project develops a **computer vision-based system for analyzing traffic flow** using images and video. By detecting and classifying vehicles in frames, it generates traffic insights useful for city planning and traffic management.

---

## 📌 Project Overview
Urban traffic analysis is essential for reducing congestion and improving road safety. Traditional monitoring is manual and costly. This project automates vehicle detection and traffic quantification using **YOLO-based object detection** and Python computer vision techniques.

---

## 🎯 Objectives
- Detect and classify vehicles (cars, buses, trucks, motorcycles)  
- Count vehicles per frame to analyze traffic flow  
- Provide visualizations and statistics for traffic insights  
- Create a foundation for real-time or batch traffic analysis

---

## 📁 Dataset & Inputs
- **Image Data:** Collected from city intersections  
- **Annotations:** Bounding boxes and labels for vehicle types  
- **Challenges:** Variable lighting, angle, and occlusion; imbalanced classes  

---

## 🧠 Computer Vision Approach
1. **Object Detection (YOLOv5)** – Detects vehicles per frame  
2. **Vehicle Classification** – Assigns vehicle type labels  
3. **Traffic Metrics Extraction** – Counts vehicles per frame  
4. *(Optional: Future tracking with DeepSORT/ByteTrack for multi-frame analysis)*

---

## 📊 Exploratory Data Analysis (EDA)
Although the notebook is too large to host, the EDA performed includes:  
- Checking class distributions and image quality  
- Inspecting annotations for accuracy  
- Visualizing sample frames and bounding boxes  
- Analyzing feature distributions such as vehicle types and traffic volume

### 📊Visuals  

<img width="631" height="409" alt="image" src="https://github.com/user-attachments/assets/871efd81-13f5-47df-b9c2-b2f691ecbcdf" />

<img width="704" height="531" alt="image" src="https://github.com/user-attachments/assets/c3007f59-ad74-4520-92a7-a9343eee6fb2" />


**Insights:**  
- Common classes like cars and vans dominate, creating class imbalance  
- Lighting and occlusion affect detection accuracy  
- Traffic patterns can be approximated using counts per frame

---

## 🛠️ Model approach 

Model used was the YOLOv5 model

### Results and Outcomes 

<img width="640" height="640" alt="image" src="https://github.com/user-attachments/assets/8d04a968-5452-44d4-b37c-8cd60e034ea4" />

<img width="640" height="640" alt="image" src="https://github.com/user-attachments/assets/deba3c8c-d333-41b1-b7dc-378d14e2ad3e" />

<img width="640" height="640" alt="image" src="https://github.com/user-attachments/assets/9b16db2d-a206-4210-8aee-0426c6ccf4c7" />

## 📦 Conclusions

1. YOLOv5 is effective for real-time vehicle detection.
- The model accurately detects and classifies multiple vehicle types, including cars, trucks, and motorcycles, making it well-suited for traffic monitoring tasks.

2. Detection confidence is high and reliable.
- With appropriate thresholding (e.g., confidence > 0.4), the model filters out false positives and focuses on clear objects.

3. Model generalizes well to standard traffic images.
- Even without custom training, the pretrained model performs well on common traffic scenarios, suggesting strong generalizability to similar environments.


## 🏗️ Usage
Since the notebook is large, it is **not included in the repository**. To run the analysis locally:

1. Clone the repository
   
       git clone https://github.com/kennethnyangweso/Traffic-Flow-Analysis-with-Computer-Vision

## **👤 Author**

**Kenneth Nyangweso**

**Data Scientist | Electrical & Telecommunications Engineer**
