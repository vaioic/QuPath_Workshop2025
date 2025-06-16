# Measurements in QuPath
While most tools and extensions in QuPath are set to collect measurements at default, there are cases where you need to add measurements in later or add in additional measurements that are not included in the standard measurement settings. Here we will cover adding in measurements and how to export them for downstream statistical analysis.

## Adding more measurements
Add or open BPAE_63x_3x4tile_Airyscan Processing_Stitch_MIP.czi to the QuPath project. Quickly get some nuclear detections with cell expansion with the following settings using [Cell Detection](/Tutorials/02_Builtin_Tools.md).

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

<img src="/Tutorials/PNGs/BPAE_Nucleus_Detection.png" width="275" height="436"><br>

You should see something like this:

<img src="/Tutorials/PNGs/BPAE_Nucleus_Detection_Results.png" width="477" height="474"><br>

Double click on any of the cell detections to view its measurements in the annotation tab.

<img src="/Tutorials/PNGs/BPAE_Cell_Measurements.png" width="488" height="429"><br>

In addition to shape descriptor measurements, there are compartment specific measurements for each channel (e.g., Nucleus, Cytoplasm, and Cell). However, the measurements listed here are not the only ones available through QuPath. Intensity measurements that capture the texture and distribution of the fluorescence can be added.

Under Analyze > Calculate Features, there are three options:
- Add smoothed features
- Add intensity features
- Add shape features

For today, we will only add Haralick features under Add intensity features. When calculating Haralick features on fluorescence images, a minimum and maximum grey value needs to be given. Use the brightness and contrast menu to determine the minimum and maximum values of the channels. In this image, the maximum values are similar, so the same minimum and maximum values can be used for all channels at 0 and 25000, respectively.

If you want to read more about how Haralick features are calculated, here is a [nice resource document](https://juliaimages.org/ImageFeatures.jl/stable/tutorials/glcm/).

<img src="/Tutorials/PNGs/Haralick_Features.png" width="293" height="443"><br>

*Note: the settings for ROIs can be ignored, this only applies to specific ROIs in use which are outside the scope of this tutorial/workshop.*

Select Cells in the popup window after clicking Run.

## Exporting measurements
QuPath has several options for exporting measurements, these are based on the hierarchy of the image and its objects.
- Image level: Gives summary of object classes and counts
- Annotation level: Gives high level information about all annotations in the image. This includes measurements, and classes and counts of detections contained within the annotation.
- Detection/Cell level: Gives detailed information about each detection including hierarchy, measurements, and class
- TMA Cores level: Similar to Annotation level, but also includes the assigned coordinate location of the TMA core.

Open the Export measurements (Measure > Export measurements) and select the image(s) to export the measurements of (use arrow keys on the window to move from left to right window), specify the measurement level, and optionally specify measurements to export. If no measurements are specified, then all measurements are exported. Additionally select where the measurements should be saved and the separator type (all options can be opened with R, Excel, or other data frame readers).

<img src="/Tutorials/PNGs/Saving_Measurements.png" width="456" height="375"><br>
