# Image-Edge-Detection
This is a python implementation for an edge-detection algorithm using  both co-occurrence matrices and integral images.

Task 1

The way to simulate/implement edge detection using co-occurrence matrices is as follows:
- Get the co-occurrence matrices of an image.
- In the co-occurrence matrices, nullify (set to 0) the diagonal that represents pixels of close intensities with a 
certain bounding box threshold. The reasoning behind that is if there is an area in the image with matching 
color values/intensities, it’s assumed to be the object itself, setting those to zero leaves the 
occurrences that represent the edges of the objects. *do that for both co-occurrence matrices*
- Reconstruct the original image using the previous resulting co-occurrence matrices by looping on the 
image and checking whether the pixel intensities exist in the co-occurrence matrices or not.
Set the existing ones to white, otherwise with black.

Methods:
1. calculateCooccurrence:
- Input: Image
- Output: Co-occurrence matrices for the given image with given pixel-relationships (North-South 
and West-East).
2. nullifyPixels: Assigns certain pixels in an image with a 0 given a specific threshold.
- Input: Co-occurrence Matrix of an Image
- Output: The Co-occurrence Matrix with the pixels of some radius/window-size on its diagonal set 
to 0.
3. imgWithCooccurrence: reconstructs the image using its nullified co-occurrence matrices.
- Input: Nullified co-occurrence matrices of an image
- Output: The image reconstructed.

Task 2

The way to simulate/implement edge detection using integral images is as follows:
- Calculate the integral image of the image.
- Calculate the integral image of the squared version of the image.
- Using a variance equation and integral images, loop on the 
original image and calculate a new image where each pixel in that image represents the 
variance at the pixel in the original image given some window size. If the variance in some 
locations is high, that means there is a great difference between the pixels in that location, that means that 
area mostly indicates an edge.
- Apply a suitable threshold on resultant image of variances to produce finer-looking edges.

Methpds:

1. integralArray: returns the integral image of an image in the form of an array.
- Input: Image in array format.
- Output: The integral image of the input image
2. localSum: returns the local sum of that area.
- Input: Image, and the boundaries of a box of values “pixels” that needs to be summed up (top left 
and bottom right indices of the box).
- Output: The summation of that box
3. imgWithIntegral: 
- Input: Image and a window size.
- Output: The image of the variances of the pixels in the original image


