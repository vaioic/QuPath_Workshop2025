# Using StarDist in QuPath
[StarDist](https://github.com/stardist), created by Uwe Schmidt and Martin Weigert, is a deep learning convolution neural net that excels at detecting round blob objects, like nuclei. It is also excellent at detecting these types of shapes when they are highly clustered.

Two primary models have been created and released by Schmidt and Weigert, and are available to use with QuPath's StarDist extension: dsb2018_paper(_heavy_augment) for fluorescence data and he_heavy_augment for H&E stained tissues. 

## Setup for using StarDist
You should have already installed the StarDist extension ([instructions](/Tutorials/Setup_extenstions.md))

You will also need the StarDist models located [here](/Tutorials/StarDist_Models/). I recommend saving them in the QuPath_Extension folder in a new child folder (e.g., QuPath_Extensions/StarDist_models) so it is easier to keep track of them.

After installing the extension and downloading the models, go to Extensions > StarDist. You will see four script options that are pre-written to run on the datatype specified.

<img src='/Tutorials/Tutorial_Imgs/StarDist_Scripts.png' width='347' height='237'><br>

We will test out the fluorescence and H&E models.

## Add Images
Add/open the 