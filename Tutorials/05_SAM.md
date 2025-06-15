# Segment Anything Model
Segment Anything Model (SAM) was [originally created](https://arxiv.org/abs/2304.02643) by a group at Meta for segmenting natural images (i.e., pictures of people, city scapes, animals, etc.) and then repurposed by Ko Sugawara to [segment biological images](https://www.biorxiv.org/content/10.1101/2023.06.13.544786v1) and created a QuPath extension for using SAM in the software. 

SAM requires a [separate python environment](https://github.com/ksugar/samapi) in addition to the [QuPath extension](https://github.com/ksugar/qupath-extension-sam?tab=readme-ov-file). If you are using the HPC for this workshop, it is already installed and available to use.

The HPC SAMAPI server is set up for GPU acceleration and can be taken advantage of using a gpu node on the HPC. If a GPU is not available, the server will default to using CPU.

## Starting the SAMAPI server
Before using the SAM extension in QuPath, we need to start the SAMAPI server. Open a new terminal window in the HPC Desktop and use the following prompts to start the SAMAPI server. Start the server with the following commands:
```
module load imaging/SegmentAnythingModels
SegmentAnythingModels.sh
```
The server may take a new minutes to download the models and start up. It will be ready to use once the following is displayed:

<img src='/Tutorials/PNGs/SAMAPI_Start.png' width='500' height='116'><br>

In an open instance of QuPath, open/add the Kidney_3chan.czi image then open the SAM extension under Extensions > SAM

<img src='/Tutorials/PNGs/SAM_QuPath.png' width='294' height='429'><br>

Select the Rectangle Annotation button in the window and then click Live Mode. Draw a rectangle that roughly covers the full kidney, SAM will automatically create a segmentation outline that outlines the full kidney.

<img src='/Tutorials/PNGs/SAM_Outline.png' width='372' height='239'><br>

