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
