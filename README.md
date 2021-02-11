# **Finding Lane Lines on the Road** 

## Writeup Template

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on the work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. First, I converted the images to grayscale, then I applied a 
Gaussian filter. After that, I detected the image edges using Canny's transform. Later, I applied
an image mask to identify edges on the specific region of interest. After identifying these edges I used Hough's transformation to further filter undesired line segments. Thereafter, I used the draw_lines() function to average and extrapolate the detected line segments. Finally I weighted and plotted the averaged and extrapolated lines into the original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by creating two lists containing the line points describing the left and right lanes. After that, I fitted a linear model for the left and right line points to obtain average lines for the left and right lanes.

If you'd like to include images to show how the pipeline works, here is how to include an image: 


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would take place when the parameters that filter out undesired line segments have filtered out relevant lines partially or completelly.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to optimize the selection of parameters that filter out undesired line segments.
