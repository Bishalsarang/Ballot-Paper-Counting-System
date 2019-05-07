
# Ballot-Paper-Counting-System
A Computer Vision Project on counting votes from ballot paper that count votes and display the result for Nepali Ballot Papers.

## How we created datasets ? :
We downloaded a sample ballot paper from [election.gov.np](http://www.election.gov.np/)
and synthesized datasets using ***PIL library*** by  overlaying *swastika* symbol on blank ballot paper in order and by randomization.
       **Here is how the process looks like:**
|  ![Randomization](https://media.giphy.com/media/Quz1v7new156VQnAJj/giphy.gif)| ![Generating Ballot Papers](https://media.giphy.com/media/TF04ZlAYL2xnsSYcQA/giphy.gif) |



## How it Works

### For Valid Ballot

 **1**. Read the image<br>
 **2**. Preprocess the image(Gaussian blur, edge detection, thresholding)<br>
 **3**. Apply contour detection( includes all contour including texts)<br>
 **4**. Approximate polygon with the contour and include only if it has 4 corners and satisfy size constraints<br>
 **5**. Sort the rectangular by top to bottom, left to right as they appear on paper<br>
 **6**.  Process each rectangular contours and find if there is red pixel inside any of the box<br>
 **7**.  Set that index to True if particular index contains red color<br>
 **8**. Check red pixel lies outside the boxes by filling contours with black color and searching for red pixel<br>
**9**. Valid if there are 39 rectangular contours and no red color in multiple boxes and no red color outside these 39 rectangular boxes<br>

    See images below for stepwise illustration:

| ![Original Sample](https://i.ibb.co/Nmp9N3L/img2.jpg) | ![After Applying filters](https://i.ibb.co/hBZnJZQ/img1.jpg)|
| ![Contour Detection](https://i.ibb.co/98BmSLP/imgt.jpg) |![Contour Detection(Only Boxes)](https://i.ibb.co/c3pSFxR/img3.jpg)|
| ![enter image description here](https://i.ibb.co/w0cV0K6/img5.jpg) |![enter image description here](https://i.ibb.co/ZTVDwm8/win.jpg)  |



