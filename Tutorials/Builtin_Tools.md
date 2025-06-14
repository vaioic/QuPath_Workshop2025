# QuPath's Built in Analysis Tools
There are three main sets of analysis tools built into QuPath v5.1:
- Cell Detection
- Object Classifiers
- Pixel Classifiers

**Cell Detection** uses more traditional methods of segmentation to find objects like nuclei, cell bodies, or other blob-like objects. The interactive tool allows the user to adjust parameters to smooth the image, correct background, and set a threshold that work well with the data.

**Object Classifiers** allow the user to group their existing detections into different categories. For example, if two different populations of cells existed in a fluorescent image - positive or negative for a marker of interest - an object classifier could be taught with examples of what a positive or negative cell looks like to then classify the rest of the detected cells.

**Pixel Classifiers** are similar to object classifiers in that the user is teaching the software how to group the pixels in the image by providing examples. Pixel classifiers are great for segmenting complex shapes or structures that may not be easily defined by a single channel or signal in the image data.

## Cell Detection
Add/open the Kidney_3Chan.czi image to/in your QuPath project. Navigate and zoom into a region of the image that contains a few glomeruli and draw a small rectangle using the rectangle annotation tool.

![Image of an ROI on the kidney image](/Tutorials/Tutorial_Imgs/Kidney_ROI.png)


