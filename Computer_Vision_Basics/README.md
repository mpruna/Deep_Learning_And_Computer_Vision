### Computer Vision fundamentals

Science that allows computers to understand images and video and 
determine what the computer "sees" or "recognizes”.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/human_computer_vision.png))

#### Computer Vision can be used for:
 - object clasification
 - object detection
 - object indentification
 - object restoration
 
### Where can we use computer vision:  
* Self Driving Cars 
* pedestrian/car detection
* Face recognition
* Object detection
* Handwriting Recognition
* License plate numbers detection
* Snapchat filters

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/computer_vision_use_cases.png)

One of the challenges in computer vision is the object classification. An object can be presented at a different angle, different lighting, different shape.
While is it's easier for humans to classify these objects we need to teach a computer to do the same.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/computer_vision_chalanges.png)

### View point limitations

Example below shows an example where the view point can cause some problems. In the picture we see Toronto Tower but from a different angle.
We need to train the algorithm to recognize those images as instances of the same object.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/image_view_point.png)

### Camera resolution limitations

As the resolution gets better we can see an object in greater detail. Part of the challenge is to do image correction in a low resolution image

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/camera_resolution.png)

### Lighting limitations

It's hard to extract the object features when is dark.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/scaling_limitations.png)


Requirements for an artificial eye to convert a conventional vehicle into autonomous one

Camera | Human Eye
-|-
Must provide 360° coverage around the vehicle. | 3D vision for 130° of the Field of view ‘blind-spot’
Must identify objects in 3D close and far from the vehicle. | Only central 50° FOV is ‘high-resolution’, outside central zone,
perception drops
Must meet all requirements in various lighting/weather conditions. | Good performance in varying lighting conditions
Process data in real-time. | Equivalent video ‘frame rate’ good in central zone, poor at peripheral vision

Overall human eyes provide acceptable vision in a very narrow field of view facing forward.
For the camera we would like to develop computer vision algorithms and machine learning algorithms to actually
start  detect all kinds of objects and become even better than humans.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/self_driving_car.png)

Self driving cars have set of sensors that give perception of the world, and a machine learning algorithms to process sensors data and take actions.
* Cameras : provides detailed images but require machine-learning algorithms to interpret 2-D images. 
* LIDAR (Light Detection and Ranging): works like radar, but instead of sending radio waves it emits infrared laser beams to measure how long they take to come back. Creates a 3-D map of the world in real time.
* Radars: sends radio waves to detect objects, reliable and cheaper than LIDAR systems.
* GPS: Global positioning system provides information about current location of driverless car on the road using set of maps.

### Representing images in digital format

How human eye perceives an object:
• Waves are observed by the human eye and translated in the visual cortex into color.
• When you look at a banana, the wavelengths of reflected light determine what color you see.
• The light waves reflect off the banana and hit your eye has a wavelengths of 570 to 580 nanometers. These are
the wavelengths of yellow light.

### Representing an image on a gray scale

* A greyscale image is system of 256 tones with values ranging from 0-255. 
* '0' represents black and '255' represents white. 
* Numbers in between represents greys between black and white.
* Binary systems use digits '0' and '1‘ where '00000000' for black, to '11111111' for white (8-bit image).
* Note: binary value of '11111111' is equal to decimal value of '255'

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/gray_mona_lisa.png)

### Colored image representation

* Each pixel coordinate (x, y) contains 3 values ranging for intensities of 0 to 255 (8-bit).
* RGB image is split into 3 matrices corresponding to red, green, and blue channels.
* Any other colour can be created by mixing several intensities of RGB.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/color_picture.png)

### Digitally represent a colored image

* Each RGB pixel has three sets of 8-bit binary numbers which in turn translates into 24 bits of computer
information in total, i.e.: '24-bit colour'.
* Assuming same number of pixels, RGB image is three times bigger in file size than a Greyscale one.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/colored_image.png)

### Challenges of the color extracting technique for lane detection

* What if the lane colour is not white?
* What if it is dark outside under different weather or lighting conditions?
* What if outside is snowing and most of the environment is covered in white
* What if there are no demarcation signs/lanes?

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/color_selection_chalenge.png)


### Posible sollutions

* A possible solution would be to detect edges
* More features has to be extracted from the camera image using more sophisticated computer vision techniques.
* Vehicles use LiDAR systems to create high resolution 3D digital maps of the surroundings.
* Example: in ideal weather conditions, the car collects 2.8 million laser points per second to create the LiDAR map
* This is equivalent to collecting up to 600 gigabytes of data per hour.
* The car can utilize the map created of the commute during summertime to be used as a reference during winter
time.


### RGB color space

* RGB color space is made of red, green, and blue and mixing them up can produce any color defined by those
primary colors.
* OpenCV stores color in the BGR format.
* Let’s try some colors in paint!

### HSV color space

* HSV (Hue, Saturation & Value/Brightness) is a color space that stores color information in a cylindrical representation.
* HSV color space aligns with the way human vision perceives color-making attributes.
    * Hue – Color Value (0 – 179) (represents in a circular angle the actual color)
    * Saturation – Vibrancy of color (0-255) (represents how vibrant is a color, more paint, the density of the paint)
    * Value – Brightness or intensity (0-255) (represents the brightness)
* Hue is arranged in a radial slice, around a central axis of neutral colors ranging from black at bottom to white at the top.
* The saturation dimension resembling various shades of brightly colored paint.
* Value dimension resembling the mixture of those paints with varying amounts of black or white paint.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/HSV_color_space.png)

### RGB TO HSV
* The Hue color ranges from 0 to 180 (not 360) in OpenCV
    * Green – 45 to 75
    * Red – 165 to 15
    * Blue – 90 to 120
*  Learn how to convert from RGB to HSV:
    http://www.javascripter.net/faq/rgb2hsv.htm
* Don’t forget the 1⁄2 factor in Hue!

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/rgb_to_hsv.png)

### Convolutions:

Convolutions use a kernel matrix to scan a given image and apply a filter to obtain a certain effect.
* An image Kernel is a matrix used to apply effects such as blurring and sharpening.
* Kernels are used in machine learning for feature extraction to select most important pixels of an image.
* Convolution preserves the spatial relationship between pixels.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/convolutions.png)

### Convolutions: Sharpening and Blurring:

* The sharpen kernel emphasizes differences in adjacent pixel values which makes the image look more vivid.
* The technique is used to bring out detail in an image by enhancing the contrast of pixels on edges.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/sharpen_matrix.png)

* The blurring kernel is used to blur a given image by averaging each pixel value and its neighbors.
* Blurring Kernel is an NxN matrix filled with ones. Normalization has to be performed.
* The values in the matrix has to sum to 1, if sum doesn't add to 1 then image will be brighter or darker

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/blurring.png)


### Convolutions definitions

* Kernel Size: The kernel size defines the field of view of the convolution. A common choice for 2D is 3 — that is 3x3 pixels.
* Stride: The stride defines the step size of the kernel when traversing the image. While its default is usually 1, we can use a stride of 2 for downsampling an image similar to MaxPooling.
* Padding: The padding defines how the border of a sample is handled. A (half) padded convolution will keep the spatial output dimensions equal to the input, whereas unpadded convolutions will crop away some of the borders if the kernel is larger than 1.

The spatial size of the output volume can be computed as a function of the input volume size `W`, the kernel field size of the convolutional layer neurons `K`, the stride with which they are applied `S`, and the amount of zero padding `P` used on the border. The formula for calculating how many neurons "fit" in a given volume is given by

### Neural networks convolution formula


![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/convolution_neural_network.png)

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/convolutions_at_work.gif)

### Edge detection and gradient calculation

* Edge detection is a tool that identifies points in a digital image at which the image brightness changes sharply or
has discontinuities.
* Edge detection is important tool in computer vision especially for feature extraction/detection
* Below you can see a first grade edge detection where the pixel value chan change rapidly from either a bright color to a dark one pr vice-versa..

![IMG]()

### Edge Detection and Gradient Descent calculation: Sobel method

* Sobel edge detector is a gradient based method based on the first order derivatives.
* It calculates the first derivatives of the image separately for X and Y axes.
* Sobel uses two 3X3 kernels which are convolved with original image to calculate the derivatives.
* For image A , G x and G y are two images representing horizontal and vertical derivative approximations

If we define A as the source image, and Gx and Gy are two images which at each point contain the vertical and horizontal derivative approximations respectively.
In theory at least, the operator consists of a pair of 3×3 convolution kernels as shown in Figure 1. One kernel is simply the other rotated by 90°. This is very similar to the Roberts Cross operator.

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/sobel_kernels.png)

The x-coordinate is defined here as increasing in the "right"-direction, and the y-coordinate is defined as increasing in the "down"-direction. At each point in the image, the resulting gradient approximations can be combined to give the gradient magnitude, using: 

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/sobel_math_operations.png)

Using this information, we can also calculate the gradient's direction: 

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/gradient_direction.png)

### Laplacian edge detection:

* Unlike the Sobel edge detector, the Laplacian edge detector uses only one kernel.
* It calculates second order derivatives in a single pass and detects zero crossing.
* Second order derivatives are generally extremely sensitive to noise.
* If we use gradient edge detection the edge of a image is determined by the absolute high point, where as for the Laplacian function it is the zero point where we go from positive to negative.
* The Laplacian kernel is:

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/sobel_vs_laplace.png)

### Canny Edge detection

 1 Smoothing: Smooth the image with a Gaussian filter with spread σ
 
 2 Gradient: Compute gradient magnitude and direction at each pixel of the smoothed image
 
 3 Non-maximum suppression (thinning): Zero out all pixels that are not the maximum along the direction of the
gradient (look at 1 pixel on each side)
 
 4 Thresholding: Threshold the gradient magnitude image such that strong edges are kept and noise is suppressed

![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/canny_steps.png)

3 Non-maximum suppression is applied. This removes pixels that are not considered to be part of an edge. Hence, only thin lines (candidate edges) will remain.

4 Hysteresis: The final step. Canny does use two thresholds (upper and lower):

    If a pixel gradient is higher than the upper threshold, the pixel is accepted as an edge
    If a pixel gradient value is below the lower threshold, then it is rejected.
    If the pixel gradient is between the two thresholds, then it will be accepted only if it is connected to a pixel that is above the upper threshold.

Canny recommended a upper:lower ratio between 2:1 and 3:1.


![IMG](https://github.com/mpruna/Deep_Learning_And_Computer_Vision/blob/master/images/canny_edge_detection.png)

References:

* https://en.wikipedia.org/wiki/Sobel_operator
* https://en.wikipedia.org/wiki/Edge_detection
* https://pdfs.semanticscholar.org/6bca/fdf33445585966ee6fb3371dd1ce15241a62.pdf
* https://homepages.inf.ed.ac.uk/rbf/HIPR2/sobel.htm


