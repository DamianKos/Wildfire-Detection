I am currently working on my final year project where I am using Computer Vision and training You Only Look Once (YOLO) models that will be able to detect fire and smoke for early wildfires detection and prevention.

During the course of this project I will be comparing and evaluating the performance and accuracy of the YOLOv5, YOLOv6 and YOLOv7 object detection models.


**How To Train**

!git clone https://github.com/ultralytics/yolov5
%cd yolov5
%pip install -r requirements.txt


set KMP_DUPLICATE_LIB_OK=TRUE


!python train.py --data (dataset location)/data.yaml --weights (choose model weights .pt file) --epochs 1

**How to Detect**

!python detect.py --source (test file location) --weights (weights location)
