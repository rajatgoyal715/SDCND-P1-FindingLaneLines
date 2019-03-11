# **Finding Lane Lines on the Road** 

## Writeup

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Pipeline Description

My pipeline consisted of the following steps:

1. Convert the images to grayscale to directly work with pixel intensities (instead of 3 different colors)
2. In order to reduce abrupt changes in consecutive pixels, smoothen the image by using gaussian noise filter
3. Apply Canny edge detection on this smooth grayscale image.
4. The image obtained from above step will clearly lane lines standing out. However it will also contain other edges, so we will mask the image to obtain only the region containing lane lines.
5. Then we will use the Hough transformation to obtain the coordinates of line segments in the masked image. This coordinates will be used to approximate the equation of lane lines. The approximation was done in draw_lines() function function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
