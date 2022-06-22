# Morse Code to Text Translator

## Group Members

- David Cairuz da Silva, 10830061, davidcairuz@usp.br
- Luiza Pereira Pinto Machado, 7564426, lmach@usp.br
- Maria Fernanda Lucio de Mello, 11320860, mariafernanda.mello@usp.br
- Marina Fontes Alcantara Machado, 10692040, marina.fmachado@usp.br

## Abstract

The goal of the project is to build a tool that, given an image with written Morse Code, is able to identify sequences of characters on the image, translate the code, and display it in plain text. To develop this tool we'll use Image Segmentation to identify where each morse code character is in the image and Image Description techniques to identify the meaning of each character.

This tool can be useful for scenarios in which the user who received a morse code message is not familiarized with how to decode it. This way, all the user needs to do is to write the code by hand and scan it with its phone to figure out the meaning of the message.

In the future, the set of features of this tool can be expanded and improved to include translation of other codes or/and languages, such as Braille and Elven languages from the Lord of the Rings.

## Input Images Description

As for the partial report update, we are going to use only digital images with the symbols " . " and " _ " representing, respectively, dots and dashes, the standardized sequence of two signal durations. For better comprehension, each line contains one letter. 

The images are .jpeg with a white background and the symbols are written in black.

For the final report, the group aims to use hand-written Morse Code as well, and hopes that the algorithm built can identify the difference between the symbols even with slightly inconsistencies caused by humans. 

## Description of Steps to Reach the Objective

The first step is to turn the image to gray scale to prepare it for further processing. Next up, the image is segmented using the adaptive thresholding technique, which considers different thresholds for different areas of the image. To decide how the threshold value is calculated, the gaussian-weighted sum of neighbourhood values is used as well as the function THRESH_BINARY_INV, which sets the max value to whatever is different from zero.

The second step aims to morphologically transform the image in order to make it easier to deal with it later on. The transformation used is the opening, which consists on an erosion followed by a dilation. The erosion transformation is responsible for removing any pixels with a different color form the background that is not within the limits of the foreground object. Afterwards, the dilation transformation takes part in the process, executing the opposite of what erosion just did. It turns any pixel element into '1' if at least one pixel under the kernel is '1'. This increases the area of the foregroung object. The reason why theses two transformations are used in the specific order is that erosion removes white noises while it also shrinks the object. Dilation, then, is used to increase the object size once again.

At this point, after the image is segmented and properly transformed, the plan is to make another transformation in which the dot from the Morse code input are turned into squares. That decision was made in order to facilitate the codification of the form. This isn't implemented yet.

Following, the image as a whole is analyzed, pixel by pixel. The differentiation between the dot and the dash is made by measuring the width of a line of white pixels which, at this point of the development of the project, was chosen as the color of contrast. The background is currently set as black. This part is not working properly yet and we believe the last step of image processing might fix it.

Finally, after the set of dots and dashes have been recognized from the image and turned into text, a simple translation is made using a input dictionary from Morse code to the Latin alphabet.

## References
* https://opencv24-python-tutorials.readthedocs.io/en/latest/py_tutorials/py_imgproc/py_morphological_ops/py_morphological_ops.html
* https://docs.opencv.org/4.x/d7/d1b/group__imgproc__misc.html#ga72b913f352e4a1b1b397736707afcde3
* Image Processing Course SCC0251 - https://edisciplinas.usp.br/course/view.php?id=95776
