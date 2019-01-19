### Image Transformation introduction

* Image transformations are used to correct distortions and/or change perspectives.
* Affine transformation preserves parallelism.
* Projective (non-affine) transformation does not preserve parallelism, length, and angle.

### Image Transformtation

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/image_transformation.png)

### Image Roation

* OpenCV can perform rotations by using a rotation matrix M
* A rotation matrix is a matrix used to perform rotation in Euclidean space.
* It rotates points in the xy-plane counter clockwise through an angle θ about the origin.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/image_rotation.png)

### Image Translation

* Translation is the shifting of object’s location in X and/or Y direction.
* OpenCV uses Translational matrix T as follows:

### Image resizing

* Resizing using OpenCV can be performed using cv2.resize()
* Preferable interpolation methods are cv.INTER_AREA for shrinking and cv.INTER_CUBIC for zooming.
* By default, interpolation method used is cv.INTER_LINEAR for all resizing purposes.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/image_resize.png)

References:
    
    https://root.cern.ch/TaligentDocs/TaligentOnline/DocumentRoot/1.0/Docs/books/GS/GS_27.html
    https://sites.tufts.edu/autonomousvehicles/?p=30
    https://epsil.github.io/fisheye/

### Perspective Transformation

* Image transformations are used to correct distortions and/or change perspectives.
* Projective transformation (Non-affine) does not preserve parallelism, length, and angle.
M = cv2.getPerspectiveTransform(Source_points, Destination_points)
warped = cv2.warpPerspective(image, M, (width, height))
* M: Transformation matrix

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/image_transform.png)


### Image cropping

* Image cropping(selecting a part of the immage) can be performed as follows:

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/cropped_image.png)

### Dilation and Erosion

* Dilation means adding extra pixels to the boundaries of objects in an image
* Erosion means removing pixels at the boundaries of objects in an image
* Image dilation and erosion can be performed as follows:

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/dilation_erosion_2.png)

### OpenCV has this in reverse

* Erosion means removing pixels at the boundaries of objects in an image (removing pixels from the white background
means increasing thickness of the letters!)
* Dilation means adding extra pixels to the boundaries of objects in an image (adding pixels to the white background so
letters appear thinner!)
* From OpenCV standpoint Erosion means Dilation

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/erorion_dilation.png)


### Region of interest masking

* Our goal is to mask the region of interest so we can focus our search efforts for the lane lines
* This might come in handy when we want to single out pedestrians, lanes, vehicles
* We do this by applying a matrix convolution and blacking out the non interesting area

### High level process for masking is the following:
* define the area we want to mask
* fill the area with black pixels
* apply that area as a mask & perform matrix "and operation"  

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/region_of_interest.png))

### Hough Transform

* A line can be represented with one of the two forms below.
* ρ is the perpendicular distance from origin to the line.
* θ is the angle formed by this perpendicular line and horizontal axis.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/line_representation.png)

### How to get Hough Transform

* In image space, a line is plotted as x vs. y and modeled as y = mx + b or x cos(θ) + y sin(θ) = ρ
* In parameter space (hough), a line is represented by a point in "m vs. b“.
* Each line is represented as a single point with (m, b) coordinates or (ρ, θ) parameters.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/hough_transformt.png)

### Hough Transform example

* Assume 100x100 image with horizontal line in the middle.
* First we create a 2D matrix or accumulator (to hold values of two parameters) and set it to 0.
* Select the first point on the line and try θ values from 0, 1, 2, ..180 and check the obtained value of ρ
* For every (ρ, θ) pair, increment an accumulator by 1 which means cell (50, 90) will be incremented by one
* Try next point, and repeat procedure.
* Cell (50, 90) will be voted up, the accumulator with maximum votes indicates a line!

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/hugh_space.png)

### Hough Transform flow

* We ususaly use hough transform to detect features such as lines, this is typically done using an edge detector like Sobel, Canny
* In an infinite point space a line can be represented by the slope (angle of the line) and the intercept line passing through that point.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/line_in_mc_space.png)

* Or a line can be represented in polar space 

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/line_in_polar.png)

* The goal of the Hough Transform is to find out all the point in a edge detected image that would consitute a line.
* You taken an edge detected image, and for every point that is non black, you draw lines in the mc place. Obviously, some lines will intersect. These intersections mark are the parameters of the line.
* Where point have similar values then we can assume they represent the same line

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/possible_line_space.png)

References:

* https://en.wikipedia.org/wiki/Hough_transform
* http://www.aishack.in/tutorials/hough-transform-basics/
* https://docs.opencv.org/2.4/doc/tutorials/imgproc/imgtrans/hough_lines/hough_lines.html