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
4. Determine the curvature of the lane and vehicle position with respect to center.
5. Warp the detected lane boundaries back onto the original image.
6. Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

**Perspective Transformation**
We can change the perspective of a given image or video for getting better insights about the required information. In Perspective Transformation, we need provide the points on the image from which want to gather information by changing the perspective. We also need to provide the points inside which we want to display our image. Then, we get the perspective transform from the two given set of points and wrap it with the original image.

**Bird's Eye View Transformation**
Parallel lines appear to converge on images from the front facing camera due to perspective. In order to keep parallel lines parallel for photogrammetry a bird’s eye view transformation should be applied.

**HSLV**
HSL (hue, saturation, lightness) and HSV (hue, saturation, value, also known as HSB or hue, saturation, brightness) are alternative representations of the RGB color model. The HSL representation models the way different paints mix together to create colour in the real world, with the lightness dimension resembling the varying amounts of black or white paint in the mixture while, the HSV representation models how colors appear under light. 

The difference between HSL and HSV is that a color with maximum lightness in HSL is pure white, but a color with maximum value/brightness in HSV is analogous to shining a white light on a colored object

vmin and vmax define the data range that the colormap covers. By default, the colormap covers the complete value range of the supplied data. It is deprecated to use vmin/vmax when norm is given.

For color conversion, we use the function cv2.cvtColor(input_image, flag) where flag determines the type of conversion.
For RGB ￼ HSL conversion we use the flag cv2.COLOR_RGB2HSL. and similarly for HSV.

**Modules** 
- Calibrate the camera 
- Threshold the image using gradients and colors 
- Perspective transform 
- [Identify the lane lines]

Calibrating the camera really means accounting for the distortion in an image introduced by the camera’s lens. This is done using multiple images of checkerboard patters, which should have straight lines. Examining how the checkerboard patterns are distorted (not straight) allows us to precisely identify how the camera lens is distorting images.

Threshold the image using gradients and colors. Thresholding is a method of isolating the pixels we are interested in. This can be done using a combination of gradient and color filters. We applied pixel-gradient and color threshold filters to narrow down the pixels of interest (lane lines).

Perspective transform 
While undistorting and thresholding help isolate the important information, we can further isolate that information by looking only at the portion of the image we care about — the road. To focus in on the road-portion of the image we shift our perspective to a top-down view of the road in front of the car. While we don’t gain any extra information from this step, it’s much easier to isolate lane lines and measure things like curvature from this perspective

Identify the lane lines 
Finally, we take all this information we gathered and draw the results back onto the original image. 
The green lines we identified above are present, and the space between them is colored green to show the lane. The calculated right/left lane curvature and center-lane offset are shown in the top-left of the image as well. (These values would be useful when telling a self-driving car how to steer.)

## Conclusion
The experimental results show that the algorithm can accurately identify the road lane-line and give the deviated
information of vehicle and the direction of the curve. 


It has great significance to improve the active safety driving
and assisted driving of the vehicle which is in the curved road conditions. 

Eventhough, lot of progress has been
attained in the lane detection and tracking area, further improvements can be made as per the requirements.
