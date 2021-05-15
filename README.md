# Lane Detection
Dataset: [CULane](https://arxiv.org/pdf/1712.06080.pdf) + Custom images

CULane is a large scale challenging dataset for academic research on traffic lane detection. It is collected by cameras mounted on six different vehicles driven by different drivers in Beijing. More than 55 hours of videos were collected and 133,235 frames were extracted. Data examples are shown above.

We have divided the dataset into 88880 for training set, 9675 for validation set, and 34680 for test set.

## Method
OpenCV

## Introduction
OpenCV is a cross-platform library using which we can develop real-time computer vision applications. It mainly focuses on image processing, video capture and analysis including features like face detection and object detection.

Computer vision is a process by which we can understand the images and videos how they are stored and how we can manipulate and retrieve data from them.

It plays a major role in real-time operation, one can process images and videos to identify objects, faces, or even handwriting of a human

Lane detection is a critical component of self-driving cars and autonomous vehicles. It is one of the most important research topics for driving scene understanding. Once lane positions are obtained, the vehicle will know where to go and avoid the risk of running into other lanes or getting off the road. This can prevent the driver/car system from drifting off the driving lane.

## Steps
1. Perspective transform to rectify binary image ("birds-eye view").
2. Use color transforms, gradients, etc., to create a thresholded binary image.
3. Detect lane pixels and fit to find the lane boundary.
6. Determine the curvature of the lane and vehicle position with respect to center.
4. Warp the detected lane boundaries back onto the original image.
5. Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

In Perspective Transformation, we can change the perspective of a given image or video for getting better insights about the required information. In Perspective Transformation, we need provide the points on the image from which want to gather information by changing the perspective. We also need to provide the points inside which we want to display our image. Then, we get the perspective transform from the two given set of points and wrap it with the original image.

## Conclusion
The experimental results show that the algorithm can accurately identify the road lane-line and give the deviated
information of vehicle and the direction of the curve. 


It has great significance to improve the active safety driving
and assisted driving of the vehicle which is in the curved road conditions. 

Eventhough, lot of progress has been
attained in the lane detection and tracking area, further improvements can be made as per the requirements.
