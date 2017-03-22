#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used Canny Edge Detection to detect the gradient of the image. I masked that image to a appropriate polygon and then performed Hough transformation in order to detect the lane lines on both sides in image space.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by separating the segments of the Hough transform by their slope ((y2-y1)/(x2-x1)) to decide which segments are part of the left lane line and which segments are part of the right lane line. Then I fitted linearly the points being part of the left and right lane line separately.

###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when a guardrail is included in the video stream. 

Another shortcoming could be that the weather, day time,... could be different.


###3. Suggest possible improvements to your pipeline

A possible improvement would be to have a camera with a higher resolution filming the video stream.

Another potential improvement could be to optimize the parameters for the Canny Edge Detection and the Hough transform.
