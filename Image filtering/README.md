This file is an image filtering function to apply on input images. Image filtering (or convolution) is a fundamental image processing tool to modify the image with some smoothing or sharpening affect.

# Image filtering in spatial domain
This code supports several features

1- Support grayscale images

2- Support arbitrarily shaped filters where both dimensions are odd (e.g., 3 × 3 filters, 5 × 5
filters),

3- Support different types of smoothing and sharpening filters (Gaussian)

4- Support padding operation so that output filtered image resolution remains the same

5- Support image window and filter

## The original image
![image](https://github.com/SaraFaisalX/Computer-vision/assets/108310176/156612e5-516f-43e6-ab4e-0bd23be6991b)
## The code 
`function imagefilterng = SARAfilter(S_image)`

`newimage= imread(S_image);`

`gray_img = rgb2gray(newimage);`

`img = gray_img;`

`kernel_size = 5;`

`sigma = 1;`

`[x, y] = meshgrid(-(kernel_size-1)/2:(kernel_size-1)/2);`

`gaussian_kernel = exp(-(x.^2 + y.^2) / (2*sigma^2)) / (2*pi*sigma^2);`

`gaussian_kernel = gaussian_kernel / sum(gaussian_kernel(:));`

`[height, width, channels] = size(img);`

`F_image = zeros(height, width, channels);`

`for g = 1:channels`

`padded_img = padarray(double(img(:,:,g)), [floor(kernel_size/2)`

`floor(kernel_size/2)], 'replicate');`

`for s = 1:height`

`for f = 1:width`

`neighborhood = padded_img(s:s+kernel_size-1, f:f+kernel_size-1);`

`filtered_value = sum(sum(gaussian_kernel .* neighborhood));`

`F_image(s, f, g) = filtered_value;`

`end`

`end`

`end`

`imagefilterng = uint8(F_image);`

`figure;`

`subplot(1,3,1);`

`imshow(gray_img);`

`title('Original');`

`subplot(1,3,2);`

`imshow(gaussian_kernel, []);`

`title(' Gaussian Filter');`

`subplot(1,3,3);`

`imshow(imagefilterng);`

`title('Sara Filter');`
## The Result
The results of the filters on the image will appear by writing a command in the command window
`SARAfilter('computer vision.jpg')`
![image](https://github.com/SaraFaisalX/Computer-vision/assets/108310176/caad19d3-37a2-4295-9c5d-3b00fd6b97c5)


