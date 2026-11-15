# Manual Distraction Detection while Driving

**Acknowledgment:** 
This project is a subpart of a broader research project done under the supervision of **Dr. Anirban Dasgupta** of the **Department of Electronics and Electrical Engineering** of **IIT Guwahati** as part of a Summer Research Internship.

---

### About the Project
Distracted driving is a leading cause of road accidents. This project tackles the problem through a sequential, two-stage computer vision pipeline designed to monitor driver behavior using transfer learning with EfficientNetB0 and ResNet50 architectures. 

* **Stage 1 (Hand Placement Classification):** The pipeline first analyzes the live frame to detect the driver's grip on the steering wheel. The classification task consists of three baseline classes: `both_hands`, `no_hands`, and `one_hand`.
* **Stage 2 (Driver Activity Classification):** If Stage 1 detects a potential high-risk or cautionary posture (such as a missing hand on the wheel), the flow dynamically proceeds to Stage 2 to pinpoint the specific distraction. This stage classifies the driver's ongoing activity into four classes: `drinking`, `eating`, `phone_use`, and `other`. These specific activities were chosen because they introduce highly distinguishable posture and object-level visual cues.

Both stages leverage ImageNet pretrained weights, allowing the models to quickly extract meaningful features using transfer learning.

### Key Features
* **Custom Model Training**: Utilizes Transfer Learning with ResNet-50 and EfficientNetB0 pipelines to extract robust features from interior vehicular environments.
* **Live Inference Bridge**: Includes a custom WebRTC/JavaScript bridge built for Google Colab. This captures live webcam feeds, processes frames in real-time, and runs inference dynamically in the cloud without requiring a local GPU setup.
* **Automated Logging**: Generates session reports tracking the ground truth, model predictions, and confidence scores, which are exported directly as CSV files for research documentation and empirical review.

### Tech Stack
* **Programming Languages:** Python, JavaScript, HTML5
* **Machine Learning & Deep Learning:** TensorFlow, Keras, Pre-trained CNNs (ResNet-50, EfficientNetB0)
* **Computer Vision:** OpenCV (`cv2`)
* **Data Analysis & Environments:** Pandas, NumPy, Google Colab
