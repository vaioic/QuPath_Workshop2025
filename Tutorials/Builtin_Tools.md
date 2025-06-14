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

Open Cell Detection (Analyze > Cell detection > Cell detection)

![Cell Detection Location](/Tutorials/Tutorial_Imgs/Cell_Detection_Menu.png)

Adjust the parameters until you are satisfied with the results. Below are the settings I found to work reasonably well.

*Note: this will not be perfect and that's okay!*

![Cell Detection Parameters and Results](/Tutorials/Tutorial_Imgs/Cell_Detection_Parameters.png)

## Object Classifiers
Using the same objects above, we will create two types of object classifiers to group objects as positive or negative for EGFP. 

**Important! You need measurements in order to classify objects, make sure that `Make measurements` was selected when detecting the nuclei.**

### Train an Object Classifier
Before we train the object classifier, we need to mark some examples of positive and negative cells. Add two Points annotations by clicking the points annotation tool and then clicking `Add` on the popup menu twice. These annotations will be visible under the Annotations tab.

![Adding Points Annotations](/Tutorials/Tutorial_Imgs/Points_Annotations.png)

Then set the class of one points annotation to Positive and the other to Negative.

![Setting class of annotations](/Tutorials/Tutorial_Imgs/Setting_Class_of_Annotations.png)

Using the brightness and contrast menu, turn off the DAPI and AF568 channel so that only the EGFP channel is visible. This will make finding positive and negative examples easier.

Using the Positive and Negative Points Annotations, mark examples of cells positive and negative for EGFP. Aim to have roughly equal numbers of examples.

![Positive and Negative Examples](/Tutorials/Tutorial_Imgs/PositiveNegative_Examples.png)

Open the Object classifier (Classify > Object Classification > Train Object Classifier) and then change the Feature parameters from `All Measurements` to `Selected Measurements`. Click select and search for EGFP in the new window. Select all of the EGFP related measurements and then click apply.

![Object Classifier Settings](/Tutorials/Tutorial_Imgs/Object_Classifier_Settings.png)

In the Training option, change it from `Unlocked annotations` to `Points only`. 

*Note: if you were using training data across multiple images, or a specific training image, then you would select Load training and specify which images to use for training the object classifier. In this case, **only the examples of classes from the selected images would be used**.*

Once the examples are annotated and the object classifier parameters are set, click on the Live update button to preview. You can also name and save the classier for use on other images.

![Preview of Classifier](/Tutorials/Tutorial_Imgs/Preview_Classifier.png)

The benefit of training an object classifier with a machine learning algorithm is that it is more flexible to natural variation that can be seen across samples and batches because it uses multiple sets of measurements to make decisions on how a detection should be classified.

## Creating a Single Measurement Classifier
Another approach to classifying cells is to use a hard coded threshold using a single measurement. This is less flexible to natural variation that may be seen across your data, but a great option for small and highly consistent datasets or single images. Do not set different threshold values for different images/data you plan to compare, instead train a classifier like in the section above.

Open the Single Measurement Classifier (Classify > Object classification > Create single measurement classifier). Change the Channel filter to EGFP, and set Above Threshold to Positive and Below Threshold to Negative. Then click on Live Preview. QuPath's default option is the mean intensity value of either the nucleus compartment or the cell and will make a good guess where the threshold should be. In this case, the suggested threshold does a reasonable job separating the positive and negative cells. Test out other measurement options or threshold values to get a feel for how this tool works.

![Single Measurement Classifier Preview](/Tutorials/Tutorial_Imgs/Single_Measurement_Classifier.png)

Like in Training an Object Classifier, you can save the single measurement classifier to use on other images.