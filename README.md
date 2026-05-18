# VisDrone Dataset: Human and Car Detection Using YOLOv8

This project explores human and car detection from VisDrone Dataset using YOLOv8 paired up with slicing techniques.

# Preprocessing

Our dataset exploration tells us that the bounding boxes are very small and there are variations of image resolutions.
![bbox1](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/eda/bbox1.png)

![bbox2](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/eda/bbox2.png)

![resolution](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/eda/resolution.png)

The standard YOLOv8 input size is 640x640. However, if we down-res our images, the bounding boxes will become much more smaller and the model will struggle to learn from it.

To avoid this problem, we've decided to use slicing techniques to slice our training images into 640x640 tiles (keeping only images with at least 1 label to save space and reduce noise).

As SAHI slicing was not available for training data, we've used a custom slicer to slice the images first, then used SAHI slicing when running the test set on model.

# Model

We've used YOLOv8s for it's capability to detect small objects, fast training and inference. You can find the model from [here](https://github.com/prantooshhh/visdrone-human-car-yolov8/tree/main/model).

# Results

Our model performs well on detecting car but generally struggles when detecting human and processes 3.2 frames per second. Here's the model's scoring metrics:

![res1](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/results/res1.png)

![res2](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/results/res2.png)

![res3](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/results/res3.png)

![res4](https://raw.githubusercontent.com/prantooshhh/visdrone-human-car-yolov8/refs/heads/main/images/results/res4.png)

# Sample Prediction Images

![img1](https://raw.githubusercontent.com/prantooshhh/ANTS/refs/heads/main/sample_images/3.png)

![img2](https://raw.githubusercontent.com/prantooshhh/ANTS/refs/heads/main/sample_images/1.png)

![img3](https://raw.githubusercontent.com/prantooshhh/ANTS/refs/heads/main/sample_images/2.png)

