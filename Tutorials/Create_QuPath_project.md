# Create a QuPath Project
1. Create an empty directory (folder) in an easily accessible location on your computer or network. Name the folder something descriptive, like "Practice_QuPath_Project" (use underscores instead of spaces to make it compatible with Linux).
2. Open QuPath:

    **Option 1**: Opening QuPath through OnDemand
    [Link to video walk through](https://vanandelinstitute.sharepoint.com/:v:/s/optical/EfpUD6Mp1U1LpWS3P44X38wBOOi02MNeVR-qQpkoK-a7Cw?e=cy5SNH&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)
    
    Navigate to VAI's OnDemand site and log in with your VAI account. The OnDemand site link can be found on VAI's SharePoint.

    Using the `hpc desktop`, start a `short` partition for `4 hours` using `16 cores`.
    
    <img src="/Tutorials/Tutorial_Imgs/OnDemand_pic.png" width="500" height="200"><br>

    <img src="/Tutorials/Tutorial_Imgs/OnDemand_short_partition_pic.png" width="469" height="375"><br>
    
    Once the session starts, set the `compression to 0 (low)` and the `Image Quality to 9 (high)` and launch the virtual desktop.

    <img src="/Tutorials/Tutorial_Imgs/OnDemand_desktop_settings_pic.png" width="467" height="205"><br>

    Open the terminal

    <img src="/Tutorials/Tutorial_Imgs/Terimal_pic.png" width="575" height="387"><br>

    Use the following commands, individually, to open QuPath
    ```
    module load imaging/QuPath-0.5.1
    startQuPath
    ```
    *Tip: If you forget the command to open the software use `module help imaging/QuPath-0.5.1` to get the command.*

    <img src="/Tutorials/Tutorial_Imgs/Terimal_Commands_pic.png" width="410" height="257"><br>

    **Option 2**: If you have QuPath installed on your own device, open it as you would any other application.

    *Tip: A startup dialog will appear the first time you open QuPath, if you do not want it to pop up each time you start the software, select the option to disable it on the window.*


3. Drag and drop the empty folder into the open instance of QuPath.

    ![Creating a Project]()

4. Now you're ready to add in images! Drag and drop images you would like to add to the project into the open QuPath window.

    ![Adding Images to Project]()
    
    Select `Bio-Formats` as the image server and the type of image (e.g., fluorescent, H&E, HDAB, Other). This can be corrected if a mistake is made. You can select multiple images and add them at the same time.

[Link to the slide deck presented, covers the layout of QuPath's Graphic User Interface](https://vanandelinstitute-my.sharepoint.com/:p:/g/personal/kristin_gallik_vai_org/EW2hmxe3mDJBmM5PNXSkau4BSGk77gxMTWqw_CFqQ10eiw?e=b7hiwj)