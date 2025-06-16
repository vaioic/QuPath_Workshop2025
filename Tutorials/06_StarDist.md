# Using StarDist in QuPath
[StarDist](https://github.com/stardist), created by Uwe Schmidt and Martin Weigert, is a deep learning convolution neural net that excels at detecting round blob objects, like nuclei. It is also excellent at detecting these types of shapes when they are highly clustered.

Two primary models have been created and released by Schmidt and Weigert, and are available to use with QuPath's StarDist extension: dsb2018_paper(_heavy_augment) for fluorescence data and he_heavy_augment for H&E stained tissues. 

## Setup for using StarDist
You should have already installed the StarDist extension ([instructions](/Tutorials/Setup_extenstions.md))

You will also need the StarDist models located [here](/Tutorials/StarDist_Models/). I recommend saving them in the QuPath_Extension folder in a new child folder (e.g., QuPath_Extensions/StarDist_models) so it is easier to keep track of them.

After installing the extension and downloading the models, go to Extensions > StarDist. You will see four script options that are pre-written to run on the datatype specified.

<img src='/Tutorials/PNGs/StarDist_Scripts.png' width='347' height='237'><br>

We will test out the fluorescence and H&E models.

## Running StarDist
StarDist is run through a script. There are a few parameters available in the script to fine tune the results of the model.

- `channels('name' or index of channel)` The channel that contains blob like objects. If using index value, indexing starts a 0.
- `threshold(value between 0-1)` The higher the value the more stringent the results.
- `pixelSize(any floating point value)` Minimum value should be the pixel size of the image. Increasing the number will down sample the image prior to running STarDist, the more down sampling the less accurate the outlines.

The location of the model also needs to be provided in the variable `modelPath`.

Example of a model path = `'/path/to/location/dsb2018_paper.pb'`

Optional `cellExpansion(number in um)` can be used to create an arbitrary expansion of the specified distance around the detection.

If not already in your project, add the kidney_3chan.czi (fluorescence) and 44770.svs (H&E) images.

### Fluorescence model
Open the kidney_3chan.czi image and create a 2048x2048 rectangle using Objects > Annotations > Specify annotation

<img src='/Tutorials/PNGs/SpecifyAnnotation.png' width='279' height='272'><br>
<img src='/Tutorials/PNGs/SpecifyAnnotation2.png' width='150' height='161'><br>

Move the rectangle to somewhere you find interesting in the image. Then open `StarDist fluorescence cell detection script` under Extensions > StarDist

Change `pixelSize` to `0.345` and enter the path to the location of the dsb2018_paper.pb model in the `modelPath` variable.

Select the rectangle (should be highlighted) and then press `Run` to run StarDist. It should take approximately 1 min to run on the Short Partition.

<img src='/Tutorials/PNGs/StarDist_Results.png' width='533' height='203'>



