---
layout: project
title: Project
subtitle: H261 Compression
icon: fa-gear
projectNum: 4
---

As a part of my _Advanced Digital Processing_ option at _BCIT_ I learned about various compression techniques on video, image, and audio files. This project was designed to teach me basic compression on image files in a style similar to .JPEG. In the above image you can see the original image (left), the Luminance values (right top), the chrominance values with the luminance (right middle), and then the values converted from YCrCb to RGB

What my program does is it loads a .BMP or .JPEG image, converts it's RGB pixel values into YCrCb values, and then we process the image in blocks of 8x8 pixels. In each block we compress the Cr and Cb values by throwing away three quarters of the data, only saving every other pixel from every other row. We do this because human eyes are more receptive to luminance (Y) than they are to colour (Cr and Cb), so we can safely eliminate a lot of the colour data and we won't notice much difference. After that we run a fourier transform over the values, which generates the frequencies of each pixel. Next we quantize the block, giving us much smaller values. We quantize the block using a pre-defined quantization matrix for each channel (luminance or chromanence) and multiplying it against each value in the block. This gives us a lot of zeroes or near zeroes.

 Now, we want to compress this using run-length encoding, however it's not optimized for this yet. the top left corner of the block has lots of values, getting to more zeros as we move to the bottom right corner. In order to get the largest run of zeroes we can, we re-order the block in a zig-zag formation, which will line up as many zeroes as we can in a row. After that we can compress using run-length encoding, with 0 as a flag, and the number immediately following to indicate how many zeros there are. 
 
 After all that is done, we save the file as a .JayPeg, I know I'm a genius, and add some header information in order to undo all the compression. This compression is similar to .JPEG compression, however lacks the math that handles entropy as .JPEG has. 