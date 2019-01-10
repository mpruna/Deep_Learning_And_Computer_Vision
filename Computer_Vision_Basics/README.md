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

![IMG]()

### RGB TO HSV
* The Hue color ranges from 0 to 180 (not 360) in OpenCV
    * Green – 45 to 75
    * Red – 165 to 15
    * Blue – 90 to 120
*  Learn how to convert from RGB to HSV:
    http://www.javascripter.net/faq/rgb2hsv.htm
* Don’t forget the 1⁄2 factor in Hue!

![IMG]()