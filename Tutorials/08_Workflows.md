# Workflows and batch analysis in QuPath
One of the best features of QuPath is that you can interactively create and fine tune and analysis pipeline without risk of loosing track of the perfect parameters (with some exceptions). In this tutorial, we will build out a reusable workflow to run on a small batch of images.

## The workflow tab
Most of the built in functions in QuPath are recorded in the order they occurred and with the parameters used under the workflow tab. Extensions are not recorded in the workflow tab, but can be integrated with the script generated using Create Workflow.

<img src='/Tutorials/PNGs/WorkflowTab.png' width='368' height='210'><br>
<img src='/Tutorials/PNGs/WorkflowTab_parameters.png' width='358' height='932'><br>

These commands can be copied over into a script for running on multiple images by right clicking on any command and clicking copy command.

