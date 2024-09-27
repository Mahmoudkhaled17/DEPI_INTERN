## YOLOv5 Object Detection with Gradio Interface

This project demonstrates the development of an object detection system using the YOLOv5 architecture.
The model has been trained to detect two specific classes, satellite and debris, and is integrated with a Gradio interface to allow users to upload images and videos for real-time detection. Below is a detailed description of the workflow followed for building the system.

### Overview
Classes: The model has been trained to detect two classes: satellite and debris.
Training Dataset: Images were annotated using Roboflow, defining regions for the two classes, and then exported in YOLO format for training.
YOLOv5 Model: YOLOv5 was selected for its balance of speed and accuracy in object detection tasks. It was fine-tuned with a custom dataset.
User Interface: The project leverages Gradio, a Python library for building easy-to-use UIs, to allow users to upload their own images or videos and get detection results in real time.
Steps Taken

#### 1. Dataset Preparation
Image Collection: A dataset of images containing satellites and debris was gathered for training. The images were uploaded to Roboflow, an annotation tool that streamlines the creation of datasets for machine learning tasks.
Annotations: Using Roboflow, I manually annotated the images by drawing bounding boxes around the objects of interest. These annotations were for two classes: satellite and debris.
Export Format: Once annotations were completed, I exported the dataset in YOLOv5 format, which is suitable for training with the YOLOv5 model.

#### 2. YOLOv5 Training
Model Training: The YOLOv5 model was trained using the annotated dataset. The model was fine-tuned for optimal detection of satellites and debris. I used PyTorch as the backend framework for training.
Model Weights: After training, the best-performing model weights were saved as best.pt and were used for inference in the Gradio app.
Evaluation: The model's performance was monitored using metrics such as precision, recall, and mean average precision (mAP), ensuring that it performs well on detecting both classes.

#### 3. Building the Gradio Interface
Gradio Setup: Gradio was integrated to create a simple web interface for object detection. This allows users to interact with the model without needing to write any code. The interface includes:
An image upload button for single-image detection.
A video upload button for detecting objects frame-by-frame in videos.
Real-Time Detection: The YOLOv5 model processes the uploaded images or videos and returns the result with bounding boxes drawn around detected objects.

#### 4. Application Deployment
The Gradio interface runs locally by default, allowing users to upload images and videos directly from their devices. Once the application is running, a URL is provided to access the interface in any browser.
Running the Project

##### 1. Clone the Repository
bash
Copy code
git clone https://github.com/your-username/yolov5-object-detection-gradio.git
cd yolov5-object-detection-gradio

##### 2. Install Dependencies
Install the required Python libraries by running:
bash
Copy code
pip install -r requirements.txt

##### 3. Download the Model Weights
Download your trained YOLOv5 weights (best.pt) and place them in the correct directory:

bash
Copy code
runs/train/exp/weights/best.pt

##### 4. Run the Application
To launch the Gradio web interface, use the following command:

bash
Copy code
python app.py
This will start the application, and a local URL will be provided to access the Gradio UI for uploading images and videos.

#### Future Improvements
Adding more classes and refining the dataset for improved accuracy.
Optimizing video processing speed.
Deploying the application on a cloud platform for wider access.

### Acknowledgments
YOLOv5 by Ultralytics for the object detection model.
Roboflow for dataset annotation tools.
Gradio for providing a simple and intuitive interface for real-time inference.
