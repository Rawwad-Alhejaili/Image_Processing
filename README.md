# Image_Processing
This is kinda like an image processing toolbox.

During my time with EE663: Image Processing. I found that I have implemented a couple of image processing operations in Python (like convolutions for example), and later I found that I frequenctly return to some of its functions. Therefore, I want to save them here in GitHub.

The function that I return to the most is `imshow`. I am sure that I speak for everyone when I say that the defaults of `matplotlib.pyplot.imshow` leave a LOT to be desired. For example:

- The default DPI is so freaking LOW which causes the output image to have terrible quality.
- The size of the image is so small that even a short title could be wider than the image. This is problematic when you have multiple subplots because their titles will overlap and cause a mess.
- Unless your image has a range from 0 to 1, you will have to convert the input image to uint8 so that `plt.imshow` "shows" the right range (by default, the range is from 0 to 1, but for uint8, it is from 0 to 255).
- For God knows why, grayscale image are shown with pseudo-color.
- Using cmap='gray' will show the normailzed image.
- Images are shown with useless axes.

I could go on, but I guess you get the point now. Having to fix all of this every single time I use plt.imshow gets REALLY annoying after some time. As such, I decided to write what I would call a "convenience function", and it is `imshow` (will probably rename it to `LazyImshow`).

What this function does is very simple. It fixes all of the above issues swiftly for the most part.

Instead of writing:
```
plt.figure(dpi=300, figsize=(5.5,5.5))
plt.axis('off')
plt.title('Boo')
plt.imshow(np.uint8(Im*255), 'gray', vmin=0, vmax=255)
```

Now you only to need to type:
```
imshow(Im, 'title')
```

And the function will take care of the rest.

Why the @$%! did I write all of this! Why would anyone read this XD
