# **Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

## Reflection

### 1. Pipeline Description

My pipeline consisted of the following steps:

1. Convert the images to grayscale first.
2. Smoothen the image by using gaussian noise filter
3. Apply Canny edge detection on this smooth grayscale image to detect edges on the basis of the difference in pixel intensities.
4. The image obtained from above step will clearly have lane lines standing out. However it will also contain other edges, so we will mask the image to obtain only the region containing lane lines.
5. Then we will use the Hough transformation to obtain the coordinates of line segments in the masked image. These coordinates will be used to approximate the equation of lane lines.
6. These lines were extrapolated to form a complete line segment in draw_lines function.

![Pipeline Steps](/test_images_output/pipeline.png)

![Test Images Output](/test_images_output/side_by_side.png)

### 2. Identify potential shortcomings with your current pipeline

Following shortcomings are possible in the current pipeline:
- When the lines become too curvy
- When there is much shadow in the scene
- When the color of the lines is fading

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to store previous slopes as global variables and check if current slope varies much from the previous slope, then use previous slope only. And if there is no line detected (either left or right), then use the previous line only to remove flickering.
