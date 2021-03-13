# **Finding Lane Lines on the Road** 






The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./images/pipeline.jpg "Grayscale"
[image2]: ./test_images/solidYellowCurve.jpg
[image3]: ./test_images/output_solidYellowCurve.jpg

---

| ![alt text][image2] | ![alt text][image3] |
|:--:|:--:|
| *Original Image* | *Image with line drawn* |

## Reflection

### 1. Pipeline of the Project




* Read the image and convert it to grayscale.
* Apply the gaussian blur to smooth the image.
* Detect the edges using canny function from OpenCV.
* Select the region of interest and mask it to remove unwanted information in the image.
* Apply the hough transformation. Play around with parameteres a bit find the ideal fit.  
<br /> 

![alt text][image1]

<br /> 

* Draw the line on the image. Use the slope to determine if it is the right line or the left line. Needed to do a trial and error to find the parameters for the hough tranformation. To draw a single line, I gathered all the start and end x-coordinates and y-coordinates for the lines and used numpy polyfit to find the slope and the intercept. For the video, I applied the same logic for each frame. 




### 2. Potential shortcomings 


* Video images are jumping a bit.
* The curves are not handled well.
* The low light, shadows, and poor image quality will cause problems.


### 3. Suggest possible improvements to your pipeline

* Need to handle curves in the road lanes.
* Probaby HSV would help dealing with poor image quality.
* Kalman filter or EKF will help to smooth out the lines.