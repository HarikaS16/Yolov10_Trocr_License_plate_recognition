# License Plate Recognition System

This project focuses on recognizing and extracting text from license plates, utilizing **YOLOv10** for object detection and **Microsoft’s TrOCR** (Text Recognition) model. The system was collaboratively developed by me and my friend to handle the entire process, from data preprocessing to model training and evaluation.

## Project Overview

The main objective of this project is to create a robust pipeline for recognizing and extracting text from license plates. The workflow includes:

1. **Dataset Preprocessing**:
   - Normalizing image sizes.
   - Formatting the dataset for YOLOv10 and TrOCR.

2. **Model Training**:
   - Custom training of YOLOv10 for object detection of license plates.
   - Fine-tuning Microsoft's TrOCR model for text recognition on the license plate dataset.

3. **Evaluation**:
   - Assessing model performance and accuracy in detecting and recognizing license plates.

## Dataset Preprocessing

### Step 1: Converting CSV Format for YOLOv10

The original dataset provided bounding box coordinates in the following format:

ymin, ymax, xmin, xmax

To make this compatible with YOLOv10, these values were transformed into the required format:

class_id, center_x, center_y, width, height

This conversion process involved:
- **Calculating the Center Coordinates**: Derived the center coordinates of the bounding box (center_x, center_y).
- **Calculating Width and Height**: Determined the width and height of each bounding box.
- **Normalization**: Adjusted these values based on the dimensions of the images to fit within the YOLOv10 framework.

### Step 2: Image Normalization

All images were resized to a uniform size to ensure consistency during training. This normalization step is essential for enhancing model performance and minimizing training inconsistencies.

### Step 3: Formatting for TrOCR

To prepare for text recognition, the dataset was converted into a format suitable for Microsoft’s TrOCR model. This required:
- **Restructuring Image Filenames**: Organized the image filenames to correspond with their respective text data.
- **Adhering to TrOCR Format**: Ensured that the dataset structure met the specifications necessary for custom training with TrOCR.

## Training Process

### YOLOv10 for Object Detection

The YOLOv10 model was trained to detect license plates in images. After preprocessing the bounding box data, the model was custom-trained using the formatted dataset to enhance its detection capabilities.

### TrOCR for Text Recognition

Microsoft’s TrOCR model was adapted to recognize text from the detected license plates. This process involved:
- **Dataset Formatting**: Ensured the dataset was formatted according to TrOCR's requirements.
- **Model Fine-tuning**: Customized and fine-tuned the model on the specific license plate dataset to improve accuracy and recognition performance.

## Results

After successfully training both models, the system achieved the following capabilities:
- **License Plate Detection**: Utilizing YOLOv10, the system can accurately detect license plates in images.
- **Text Extraction and Recognition**: The fine-tuned TrOCR model can effectively extract and recognize text from the detected license plates.

The project showcases an integrated approach to license plate recognition, leveraging advanced machine learning techniques for real-world applications.
