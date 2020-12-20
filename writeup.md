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

My pipeline consisted of following steps:

- converting the image to grayscale 
- getting rid of noise elements by applying gaussian filtering
- apply canny algorithm to define edges in the image
- detecting straight lines that potentially describe lane markers on the street using hough transformations
- focus on quadratic area in front of the vehicle to reject detected lines that are irrelevant
- for both left and right lines:
    - calculate slope of line (dy/dx)
    - pick one point of both lines as starting point to draw line with defined slope within previously defined region of interest




### 2. Identify potential shortcomings with your current pipeline


The major shortcomings of the presented pipeline are:

- the resulting lines depend strongly on the point that is picked as an initial starting point
- the pipeline can´t be extended to detecting curves


### 3. Suggest possible improvements to your pipeline

A potential improvement could be a temporal fusion of detected lines to get a more stable output
