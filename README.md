FLAME 3: Autonomous Wildfire Detection via Thermal-Optical Data Fusion
This project aims to develop an advanced wildfire detection system by leveraging thermal and optical (RGB) datasets. The core objective is to train a YOLOv8-nano model capable of performing real-time fire detection on edge computing devices such as Raspberry Pi or Jetson Nano.

1. Data Preprocessing & Engineering (Completed)
I have processed the FLAME 3 radiometric thermal dataset to make it compatible with deep learning workflows. The following steps were executed:

Radiometric Data Extraction: Used Rasterio to parse raw .TIFF files and extract pixel-level temperature values in Celsius.

Automated Thresholding: Implemented a decision mechanism based on the 200 
∘
 C threshold (as per FLAME 3 literature) to generate binary fire masks. This automates the labeling process and eliminates manual annotation.

Normalization: Scaled raw temperature values to a [0,1] range (8-bit 0-255 scale) to optimize the model's convergence and learning stability.

Format Conversion: Converted processed thermal data into 8-bit PNG format to ensure compatibility with standard computer vision pipelines.

2. Directory Structure
Processed data is organized as follows to maintain synchronization with optical imagery:

/Normalize_Goruntuler/: Contains 8-bit normalized thermal PNGs ready for training.

/Tum_Maskeler/: Contains the corresponding black-and-white ground truth masks (Fire/No-Fire).

3. Team Roles & Integration
To achieve the final goal, the following modules are being integrated:

Thermal Module (Me): Data cleaning, normalization, and mask generation.

Optical Module (Taha): RGB image sorting and side-by-side alignment with thermal data.

System Integration (Zeynur): Integration of the trained model into the autonomous decision-making mechanism (SAC-P).

4. Tech Stack
Language: Python

Libraries: Rasterio, OpenCV, NumPy, Matplotlib

Model: YOLOv8-nano

Deployment Target: Edge AI (Raspberry Pi / Jetson Nano)

Next Steps

The next phase involves the Side-by-Side Visual Alignment of the processed thermal images with the optical (RGB) frames. Once data fusion is complete, the YOLOv8-nano training phase will commence.
