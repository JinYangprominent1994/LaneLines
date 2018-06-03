# **Finding Lane Lines on the Road**

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I define a kernel size and apply Gaussian smoothing.

After that, define parameters for canny and apply it to get edges.

In the next step, I define a four sided polygon to mask certain region, so I can acquire the region that I am interested in,

and then I define Hough transform parameters.

After running Hough on edge detected image and acquiring a black image

from function hough_lines(), I create create a "color" binary image to

combine with line image and draw the lines on the edge image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image:

image = mpimg.imread('solidWhiteCurve.jpg')

I use it to read an image

![alt text][image1]

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be the masked region is fixed, so when cars are making a turn, the region I selected is not prefect


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to identify a function. the goal of this function is that

region_of_interest function can select different shapes and then select different regions according to the situation, not a fixed region.

Another potential improvement could be to combine other colors with line image, not just red.
