# Setup Extensions in QuPath
So far we have used QuPath's built in tools, but there are many powerful and useful tools made by community members. This section shows you how to set up the folder for storing extensions and adding extensions to QuPath.

## Step 1: Set up your extensions folder
Make a folder in an accessible location, such as your home directory on the HPC, lab network drive, or your own computer and name it something like "QuPath_Extensions".
Open the preferences menu (File > Preferences). Under Extensions use the folder navigation button to navigate to the QuPath_Extensions folder you just made and select it as the location to save your extensions. Then restart QuPath.

*Note: a new folder will be made within the parent folder called "extensions". This is normal.*

<img src='/Tutorials/PNGs/Extensions_Folder.png' width='495' height='368'><br>

We will add the following extensions to QuPath:
- [StarDist](https://github.com/qupath/qupath-extension-stardist)
- [CellPose](https://github.com/BIOP/qupath-extension-cellpose)*
- [Segment Anything Model (SAM)](https://github.com/ksugar/qupath-extension-sam)*

*These extensions require additional Python environments to run. If you are using the HPC, they are already accessible to you. If you are using QuPath on your own machine, you will need to set up the Python environments first before you can use the extensions (instructions in the links above).

## Step 2: Add extensions to the extension folder
I have provided the .jar and .py files needed for using the extensions we will cover. You can download them [here](/Tutorials/QuPath_Extensions/).

Drag and drop all of the files into an open instance of QuPath, they should automatically install. Then restart QuPath for them to become available. If this does not work, then copy the files into the QuPath_Extensions/extensions folder and restart QuPath. You may need to verify that the location you chose for the extensions folder is still selected in Preferences > Extensions.

Your extensions should now be available under the Extensions menu.

<img src='/Tutorials/PNGs/Installed_Extensions.png' width='224' height='228'><br>

<mark>**If you use any of the extensions for published works, please cite both QuPath and the extensions used appropriately in the Methods section.**</mark>
