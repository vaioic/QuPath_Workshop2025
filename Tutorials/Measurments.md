# Measurements in QuPath
While most tools and extensions in QuPath are set to collect measurements at default, there are cases where you need to add measurements in later or add in additional measurements that are not included in the standard measurement settings. Here we will cover adding in measurements and how to export them for downstream statistical analysis.

## Adding more measurements
Add or open BPAE_63x_3x4tile_Airyscan Processing_Stitch_MIP.czi to the QuPath project. Quickly get some nuclear detections with cell expansion with the following settings using [Cell Detection](/Tutorials/Builtin_Tools.md).

Create a full image annotation with `Ctrl+Shift+A` to create a rectangle annotation the same dimensions of the image.

- Detection channel: ChA-T4
- Requested pixel size: 0.5
- Background radius: 150
- Median filter radius: 3
- Sigma: 1.5
- Minimum area: 100
- Maximum area: 400
- Threshold: 500
- Cell expansion: 5 um

Any parameters not mentioned are left at their default settings.

![Cell Detection Parameters](/Tutorials/Tutorial_Imgs/BPAE_Nucleus_Detection.png)

You should see something like this:

![Detection Example](/Tutorials/Tutorial_Imgs/BPAE_Nucleus_Detection_Results.png)

Double click on any of the cell detections to view its measurements in the annotation tab.

![Cell Measurements](/Tutorials/Tutorial_Imgs/BPAE_Cell_Measurements.png)

In addition to shape descriptor measurements, there are compartment specific measurements for each channel (e.g., Nucleus, Cytoplasm, and Cell). However, the measurements listed here are not the only ones available through QuPath. Intensity measurements that capture the texture and distribution of the fluorescence can be added.

Under Analyze > Calculate Features, there are three options:
- Add smoothed features
- Add intensity features
- Add shape features

For today, we will only add Haralick features under Add intensity features. When calculating Haralick features on fluorescence images, a minimum and maximum grey value needs to be given. Use the brightness and contrast menu to determine the minimum and maximum values of the channels. In this image, the maximum values are similar, so the same minimum and maximum values can be used for all channels at 0 and 25000, respectively.

If you want to read more about how Haralick features are calculated, here is a [nice resource document](https://juliaimages.org/ImageFeatures.jl/stable/tutorials/glcm/).

![Haralick Features](/Tutorials/Tutorial_Imgs/Haralick_Features.png)

*Note: the settings for ROIs can be ignored, this only applies to specific ROIs in use which are outside the scope of this tutorial/workshop.*

Select Cells in the popup window after clicking Run.

## Exporting measurements
