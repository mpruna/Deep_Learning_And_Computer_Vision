### IMAGE FEATURES

* Image Features are important areas an image that are unique to a specific image.
* A feature is a piece of information in the image such as points, edges or objects that is different/unique.
* A feature may be a color or a detected edge.
* A good feature has to be repeatable, i.e.: if feature can be detected in two or more different images of the same scene.

![IMG]()

### FEATURE IMPORTANCE

* Image Features are critical in machine learning and self-driving cars because they can be used to analyze, describe and match images.
* Features can be used to train a classifier to detect objects such as pedestrians and cars.

![IMG]()

### OBJECT (TRUCK) DETECTION
* Our goal is to find objects (truck) in this image using template matching.
* OpenCV has functions to perform this easily: cv2.matchTemplate(), cv2.minMaxLoc()

![IMG]()

### TEMPLATE MACTHING

* cv2.matchTemplate() simply slides the template image over the input image (as in 2D convolution) and compares the
template and patch of input image under the template image.
* The function returns a grayscale image, where each pixel denotes how much does the neighbourhood of that pixel
match with template.
* If input image is of size (WxH) and template image is of size (wxh), output image will have a size of (W-w+1, H-h+1).
* Once you got the result, cv2.minMaxLoc() function is used to find where is the maximum/minimum value. Take it as
the top-left corner of rectangle and take (w,h) as width and height of the rectangle. That rectangle is the region of
template.



* cv2.matchTemplate() simply slides the template image over the input image using one of the methods:
method=CV_TM_CCORR_NORMED
* The function slides through image I, compare it to the template T and generate a result image R
* The summation is done over template and/or the image patch