The program is hardcoded for a specific folder structure, so if you want to run it for images on your
machine you'll have to change the path variables on lines 11, 13, 15, 38, 79, 80, and 103. In general,
in whatever folder you have the __init__.py file you should copy and paste the folders (ImClass and sky)
that I've included in the zip as they already have most of the structure needed. For instance,
if the path is this in the code: "C:\workspace\Visual Recognition\VisualRecognition\sky\sky_train_pink.jpg"
you'll just have to change the "C:\workspace\Visual Recognition\VisualRecognition\" to whatever
your path is and the rest should be the same.

The ImageClassification output is included in a .txt file and it runs with 8 bins, 16 bins, and 4 bins.

REPORT:
Problem 1: The accuracy for 8 bins was 83.33 percent, for 16 bins it was 75 percent, and for
4 bins it was also 83.33 percent. Thus it seems that the number of bins does not contribute to
the accuracy of the algorithm.

Problem 2: The main issue with the algorithm for problem 2 is that it only compares color and does not
factor in the actual location of pixels in the image. For example in sky_test3, there are parts near
the bottom of the image that were similar enough in color to be classified as sky pixels but since they
are in the bottom of the image with a bunch of non-sky pixels around them they obviously cannot be sky.
The opposite problem happens in sky_test4 where some of the parts of the sky are similar in color to 
parts of the ground and are put in a cluster with nonsky pixels despite being surrounded by other sky
pixels. The algorithm works when the sky and nonsky are relatively distinct in their rgb values. An
improvement would be to incorporate the location of the pixel in the k-means algorithm so that if a sky
pixel is surrounded by non-sky pixels or vice-versa, the algorithm will know to change that pixel to nonsky
or sky respectively.