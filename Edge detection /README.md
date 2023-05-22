# introduction
A technique known as **edge detection**  is used in image processing, computer vision,
and machine vision. It is important to understand that edge detection is an important
component of image analysis, including image segmentation, texture feature
extraction, and shape feature extraction.The purpose of detecting sharp changes in
image brightness is to capture important events and changes in properties of the world
around us by detecting changes in image brightness.
In this afile techniques will be used, which are: Canny, Sobel and Robert.
# Implementation
### the original image 
![Creativity](https://github.com/SaraFaisalX/Computer-vision/assets/108310176/6382fcda-dc0e-425c-9033-509797a34adc)
### The code
% Image

`figure,`

`S=rgb2gray(imread("Creativity.jpg"));`

`subplot(2, 2, 1),`

`imshow(S);`

`title("Original Image");`

% Sobel

`A = edge(S, 'Sobel');`

`subplot(2, 2, 2),`

`imshow(A);`

`title("Sobel");`

% Robert

`R = edge(S, 'Roberts');`

`subplot(2, 2, 3),`

`imshow(R);`

`title("Robert");`

% Canny

`A = edge(S, 'Canny');`

`subplot(2, 2, 4),`

`imshow(A);`

`title("Canny");`
### The result
![image](https://github.com/SaraFaisalX/Computer-vision/assets/108310176/87068a9d-e54d-490b-bb96-aa88d2c9da26)
# Conclusion
Knowing the differences between edge detection techniques is important since edge detection
is the first step in object recognition. The advantage of representing an image by its edges is
that less data is required to store the image while most of the image information is retained.
By transferring the edge pixels in an image or multimedia, a great deal of compression would
be achieved. Fortunately, edge maps can be used to reconstruct the entire image. Canny edge
detection algorithm has been found to produce better results than Sobel and Robert edge
detection algorithms in terms of accuracy and execution time.
