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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I use Canny edge detection, Gaussian Blur,  and Hough transform on the area of interest specified. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by classifying whether they are the left lane or the right lane, and then average the slope and average the points, which gives me a single line.


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the lanes ends (eg. an intersection).

Another shortcoming could be big turns, so the lanes will no longer be a straight line, and thus trying to make the lane a straight line can cause issues.

Currently for me my pipeline seems to have quite a few glitches in the videos (like it could jump around without staying stable) and are still finding ways to improve it.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to instead of using lines, we cound be using parabolas or part of the circle. Quadratic estimation may work better in real life. Or we could just identify lanes by connecting the dots (which can be more complex in time complexity I think)

Another potential improvement could be to average several frames to present the lanes but I'm worried that what if an emergency came and could the self-driving react fast enough.
