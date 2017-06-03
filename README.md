### **SDCND_Proj1: Finding Lane Lines on the Road**

### Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 
1. Use a color filter to find white and yellow pixels - I need to do the filtering work in hsv space to reduce the influence of light intensity

2. Output a grayscaled image - nothing special

3. Edge detection using Gaussian Noise kernel and Canny transform - nothing special

4. Find the region of interest - this is a bit tricky as the video in "optional challenge" is recorded in a different resolution and each frame is bigger than the first two, therefore I need to use relative ratio instead of absolute value to set the left_bottom, right_bottom and apex.

5. Use Hough transform to find and then draw lines - nothing special about the Hough transform, but it will call the draw_lines() function which needs modification. My idea is to average the slope of lines detected and find one point to draw the single line on the image. The sign of slope could be used to differentiate the left and right lane lines.

6. Annotate the lines on original images - nothing special, just need to set each contribution to be one.

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when light color cars/rocks appear in the region of interest. This leads to the fluctuation of the lines drawn.

Another shortcoming could be the light intensity changes (e.g., shades from the trees)


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
