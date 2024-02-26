I am currently working on my final year project where I am using Computer Vision and training You Only Look Once (YOLO) models that will be able to detect fire and smoke for early wildfires detection and prevention. I am training and evaluating the performance and accuracy of three versions of the YOLO object detection models: YOLOv5, YOLOv6, and YOLOv7. My goal is to develop a reliable system capable of detecting fire and smoke signs in various environments to assist in rapid response and mitigation efforts.

YOLO  is a state-of-the-art, real-time object detection system that is known for its speed and accuracy. It divides images into a grid system and predicts bounding boxes and probabilities for each grid cell. The versions used in this project, YOLOv5, YOLOv6, and YOLOv7, represent advancements in architecture, speed, and accuracy, making them ideal for real-world applications like wildfire detection.

**Getting started**

Python 3.8 or later

Conda environment

To get started with YOLOv5, clone the official repository and install the required dependencies.

!git clone https://github.com/ultralytics/yolov5

%cd yolov5

%pip install -r requirements.txt


Due to library conflicts after installing YOLOv7 dependencies in the same environment, additional environment variables are set to prevent errors. 
(warnings.warn("loaded more than 1 DLL from .libs:")

set PYTHONWARNINGS=ignore # Ignore Python DLL conflict warnings

set KMP_DUPLICATE_LIB_OK=TRUE # Resolve OpenMP library conflict

![KMP Error](https://github.com/DamianKos/Wildfire-Detection/assets/118854797/0cdda828-a84d-41d6-9051-badb4807d86e)




**How To Train**

To train a YOLO model with your dataset, use the following command template. Replace placeholders with your specific dataset location, chosen model weights file, desired number of epochs, and number of workers if necessary.

python train.py --data (dataset location)/data.yaml --weights (choose model weights .pt file) --epochs (choose number of epochs) --workers (set workers if needed)


runs/: Ou![40epoch_yolov5s](https://github.com/DamianKos/Wildfire-Detection/assets/118854797/4f5ed328-abf0-45c0-b19e-16b37872d228)


**How to Detect**

After training your model, you can perform detection on new images or videos by using the trained weights as follows

python detect.py --source (test file location) --weights (weights location from trained model)


![detect eg](https://github.com/DamianKos/Wildfire-Detection/assets/118854797/6bb021e0-17a1-44aa-b4e6-71ebf0c5e77f)

![Screenshot 2024-02-26 215134](https://github.com/DamianKos/Wildfire-Detection/assets/118854797/82308537-bdb7-43b2-b240-bd60ff53d9f1)


**Project Structure**

yolov5/: YOLOv5 repository cloned from Ultralytics.

yolov7/: Directory for YOLOv7-specific files and weights (setup similar to YOLOv5).

data/: Contains datasets, including images and annotations for training and testing.

models/: Custom model configuration files for YOLOv5, YOLOv6, and YOLOv7.

runs/: Output directory for training sessions and detection results.

**Freezing Layers**

Freezing layers is a technique used to prevent certain layers of a neural network from being updated during training. 

When training your model, you can specify which layers to freeze by using the --freeze command followed by the layer indices. 

python train.py --data (dataset location)/data.yaml --weights (model weights .pt file) --epochs (number of epochs) --freeze 0-8

![freezing backbone](https://github.com/DamianKos/Wildfire-Detection/assets/118854797/e9a1747a-a585-4bf4-b8e1-5ea19f505a44)
