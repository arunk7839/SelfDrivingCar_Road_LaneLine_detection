#**Finding Lane Lines on the Road** 

##Writeup Template


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps. 

1. First I filters the colors from the image and only keep the white and yellow pixel in the images all other become black.
2) After filtering color I grascle the image.
3) Apply gaussian blur.
4) Apply can age detection.
5) Create masked edges using trapezoid-shaped region-of-interest
6) Run Hough on edge detected image
7) Draw lane lines on the original image



In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

1)First I find the  slopes of all lines by using loop. if x2-x1==0 then consider slop =999.0
  otherwise slop=(y2-y1)/(x2-x1)
2) filter the lines base on the slope.
3) Then Spilt the line into right and left line Right and left line must have positive and negative slope and should be on the right/left half of the image.
 4)then run the linear regression to find the best fit line for right and left lane lines.




If you'd like to include images to show how the pipeline works, here is how to include an image: 

1. Call the annotate_image function and give the image path as a parameter like below:

annotated_image = detectLaneLine_image(mpimg.imread('test_images/solidYellowCurve.jpg'))
plt.imshow(annotated_image)



###2. Identify potential shortcomings with your current pipeline


1)One potential shortcoming would be what would happen when the car runing on the road where LaneLines not good or not available on the road.
2)  What happen when detect lane line in the night time... 

3) What would happlen when LanLine cover by another big Vehicle.



###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

1)The lane line not good on the turns this should be perfact on the Road turns.
2)In case of no laneline it should detect Edge if the road.
