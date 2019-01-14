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