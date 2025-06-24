# Traffic-Flow-Analysis-with-Computer-Vision
# Business Understanding

## Project Overview

This project aims to develop a computer vision-based system for analyzing traffic flow at city intersections using video footage. By leveraging modern object detection and tracking techniques, the system will automatically identify and classify vehicles, quantify traffic flow patterns, and generate actionable data to inform city planning, traffic management, and public safety initiatives. The insights generated will be useful for city authorities, transportation planners, and other stakeholders seeking to optimize intersection operations and urban mobility.

## 1. Problem Statement

Urban intersections frequently experience unpredictable and heavy traffic, resulting in congestion, increased travel times, and a higher risk of accidents. City authorities often lack real-time, detailed, and actionable data that would enable them to optimize traffic management, plan infrastructure upgrades, and enhance road safety. Traditional manual counting and sensor-based approaches are expensive, labor-intensive, or limited in scope.

## 2. Project Objectives

- Automatically detect and classify vehicles (cars, buses, trucks, motorcycles, etc.) in video footage from city intersections using computer vision.
- Quantify traffic flow patterns, including vehicle counts, types, and movement directions over time.
- Generate actionable reports and visualizations to support data-driven decisions by city planners and transportation authorities.

## 3. Stakeholders

- City traffic managers and urban planners  
- Public transportation authorities  
- Urban infrastructure developers  
- Law enforcement agencies  
- Policy makers and government agencies

## 4. Business Value / Expected Impact

- Enable data-driven decisions for traffic signal optimization and congestion reduction.
- Improve road safety by identifying high-risk intersections or times.
- Support better investment in urban infrastructure by providing evidence-based insights.
- Reduce manual labor and operational costs associated with traditional traffic monitoring methods.

## 5. Success Criteria

- Achieve high accuracy in vehicle detection and classification (e.g., >90% detection accuracy on test data).
- Successfully analyze and report on traffic flow patterns for selected intersections.
- Deliver actionable insights or reports that are validated as useful by at least one stakeholder group.
- Provide visualizations and summary statistics that are clear, interpretable, and directly inform decision-making.

# Data Understanding
## 1. Data Sources

The primary dataset consists of images collected from city intersections, stored in the `valid` folder of the project repository. These images are intended for training and validating computer vision models for vehicle detection and traffic flow analysis.

## 2. Data Structure & Format

- **Image Files:**  
  - Format: `.jpg`
  
-
## 3. Initial Data Exploration

- **Sample visualization:**  
  A subset of images was visualized to verify image quality and content. The images depict urban intersections with varying lighting and weather conditions, featuring multiple vehicle types.

- **Potential Issues:**  
  - Some images may be blurry, poorly lit, or partially obstructed.
  - There may be class imbalance (e.g., more cars than buses or motorcycles).
  - Annotation coverage and accuracy will need to be verified.

## 4. Data Quality Assessment

- **Missing Data:**  
  (State if any images or annotation files are missing or mismatched.)
- **Consistency:**  
  (Note any inconsistencies in file naming or annotation format.)

## 5. Next Steps

- Explore and visualize more images to better understand scene variability.
- Analyze annotation files to confirm class distribution and annotation quality.
- Identify and address any data quality issues before proceeding to model development.

## Exploring the Images

![image](https://github.com/user-attachments/assets/e82a01a2-2d54-4fe6-bfd9-b9cab629fed0)

![image](https://github.com/user-attachments/assets/55fbd9c4-e5bc-4913-86d6-bb1e28267cd7)

![image](https://github.com/user-attachments/assets/9acb1bbc-eead-49cf-8744-929e519b878c)

# Exploratory Data Analysis

## Class Distribution

![image](https://github.com/user-attachments/assets/559ba315-96e4-4819-931b-3eea3a0da7cb)

*Observations**

Based on the class distribution bar chart:

1. **High Class Imbalance**
   - The dataset is overwhelmingly dominated by the "car" class, which has a significantly higher count than all other vehicle classes.

2. **Underrepresented Classes**
   - Classes such as "van" and "motorcycle" are present in much fewer numbers compared to "car".
   - "truck", "jeepney", and "bus" are severely underrepresented, each appearing rarely in the dataset.

3. **Potential Issues for Model Training**
   - The substantial class imbalance may lead to a model that is biased towards detecting cars, while struggling to accurately detect less common classes.
   - Underrepresented classes may suffer from poor recall and precision, impacting the overall effectiveness of multi-class vehicle detection.

4. **Diversity of Data**
   - While the dataset contains multiple vehicle types, its usefulness for tasks that require balanced detection across all classes (e.g., traffic flow analysis by vehicle type) may be limited unless the class imbalance is addressed.

# Modeling with YOLOv5

## Results and Outcomes

![image](https://github.com/user-attachments/assets/806e8df1-59fd-47d8-917f-33e2f9d7d696)

![image](https://github.com/user-attachments/assets/9ae32723-749c-4503-a775-fc60bb6adf80)

![image](https://github.com/user-attachments/assets/5fcef546-bc81-4c4e-882e-6fb9f966d8c0)

![image](https://github.com/user-attachments/assets/648a2600-0bc4-4884-9f80-1f0618a53f7c)

![image](https://github.com/user-attachments/assets/8dd908a5-047c-4f3e-b95c-ae4e4020bd95)

![image](https://github.com/user-attachments/assets/5e7cb611-540e-4035-b864-62a2b64826d8)

# Conclusions

1. YOLOv5 is effective for real-time vehicle detection.
- The model accurately detects and classifies multiple vehicle types, including cars, trucks, and motorcycles, making it well-suited for traffic monitoring tasks.

2. Detection confidence is high and reliable.
- With appropriate thresholding (e.g., confidence > 0.4), the model filters out false positives and focuses on clear objects.

3. Model generalizes well to standard traffic images.
- Even without custom training, the pretrained model performs well on common traffic scenarios, suggesting strong generalizability to similar environments.

4. Vehicle counts and classes can be extracted for traffic statistics.
- The per-image or per-frame vehicle counts give immediate insight into traffic density, which can be used to infer congestion or flow patterns.

5. The detection pipeline is now deployment-ready.

- The trained model (yolov5su.pt) can be used in local applications like Streamlit dashboards or integrated into APIs for edge deployment.

# Recommendations

1. Automate vehicle counting over batches or live video.
Extend the image-based detection pipeline to process entire videos or streams for hourly/daily traffic flow analytics.

2. Integrate Deep SORT or BYTETrack for vehicle tracking.
Assign unique IDs to each vehicle to enable movement tracking, line crossing detection, and speed estimation.

3. Collect and analyze detection logs.
Save vehicle types, counts, and timestamps in a CSV or database to track long-term trends and patterns.

4. Enhance the UI with Streamlit or Dash.
Create an interactive interface where users can upload footage, view detections, and explore traffic metrics visually.

5. Train a custom model (optional but valuable).
If your traffic environment differs significantly (e.g., local signage, camera angles), retrain YOLOv5 on custom annotated data for even better accuracy.

6. Consider edge deployment for real-time field use.
With optimization (e.g., ONNX, TensorRT), deploy the model to edge devices like Jetson Nano, Raspberry Pi, or surveillance units for real-time monitoring.
