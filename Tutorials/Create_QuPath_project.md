# Create a QuPath Project
1. Create an empty directory (folder) in an easily accessible location on your computer or network. Name the folder something descriptive, like "Practice_QuPath_Project" (use underscores instead of spaces to make it compatible with Linux).
2. Open QuPath:

    **Option 1**: Opening QuPath through OnDemand
    
    Nativate to VAI's OnDemand site and log in with your VAI account. The OnDemand site link can be found on VAI's SharePoint.

    Using the `hpc desktop`, start a `short` partition for `4 hours` using `16 cores`.
    ![Image of OnDemand Options](/Tutorials/Tutorial_Imgs/OnDemand_pic.png)
    ![Image of short partition settings](/Tutorials/Tutorial_Imgs/OnDemand_short_partition_pic.png)
    
    Once the session starts, set the `compression to 0 (low)` and the `Image Quality to 9 (high)` and launch the virutal desktop.
    ![Image of Virtual Desktop settings](/Tutorials/Tutorial_Imgs/OnDemand_desktop_settings_pic.png)

    Open the terminal
    ![Picture of Terminal window and app location](/Tutorials/Tutorial_Imgs/Terimal_pic.png)

    Use the following commands, individually, to open QuPath
    ```
    module load imaging/QuPath-0.5.1
    startQuPath
    ```
    *Tip: If you forget the command to open the software use `module help imaging/QuPath-0.5.1` to get the command.*

    ![Terminal Commands to Open QuPath](/Tutorials/Tutorial_Imgs/Terimal_Commands_pic.png)

    **Option 2**: If you have QuPath installed on your own device, open it as you would any other application.

    *Tip: A startup dialog will appear the first time you open QuPath, if you do not want it to pop up each time you start the software, select the option to disable it on the window.*


3. Drag and drop the empty folder into the open intance of QuPath.

    ![GIF of Creating a Project](/Tutorials/Tutorial_Imgs/Create_QuPath_Project-2.gif)

4. Now you're ready to add in images! Drag and drop images you would like to add to the project into the open QuPath window.

    ![GIF of Adding Iamges to Project]()

    
    