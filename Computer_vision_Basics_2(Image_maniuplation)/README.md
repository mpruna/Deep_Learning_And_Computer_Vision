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

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/Computer_vision_Basics_2(Image_maniuplation)/images/erorion_dilation.png))
