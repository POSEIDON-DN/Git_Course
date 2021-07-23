In order to install Bash on Windows you are encouraged to install **Git** in your work laptop/station. Follow the instructions described below and you will have both a **Git-Bash** terminal and **Git** installed in your local Windows device.

-	Download the **Git** for [**Windows installer**](https://gitforwindows.org/).
-	Run the installer:
    1.	Click on **Next** four times (two times if you've previously installed Git). 
    2.	From the dropdown menu select **Use the nano editor by default** and click on **Next**. **Nano** is a text editor. You can change this choice later to whichever editor you are used to.  
    3.  On the page that says "Adjusting the name of the initial branch in new repositories", ensure that **Let Git decide** is selected.  
    4.	Ensure that **Git from the command line and also from 3rd-party software** is selected and click **Next**.
    5.	Ensure that **Use the native Windows Secure Channel library** is selected and click **Next**.  
    6.	Ensure that **Checkout Windows-style, commit Unix-style line endings** is selected and click **Next**.  
    7.	Ensure that **Use Windows' default console window** is selected and click **Next**.  
    8.  Ensure that **Default (fast-forward or merge)** is selected and click **Next**.  
    9.	Ensure that **Git Credential Manager Core** is selected and click **Next**.   
    10. Ensure that **Enable file system caching** is selected and click **Next**.  
    11.	Click on **Install**.
    12.	Click on **Finish**.
-	If your `HOME` environment variable is not set (or you don't know what this is):
    1.	Open the Windows command prompt (open `Start Menu` on your Windows, then type `cmd` and press `Enter` key)
    2.	Type the following line into the command prompt window exactly as shown: `setx HOME "%USERPROFILE%"`
    3.	Press `Enter` key. You should see `SUCCESS: Specified value was saved`.
-	Quit the command prompt by typing `exit` and pressing the `Enter` key.


Now that you have installed Bash in your system, check out Bash fundamental commands in the [Typing Bash Commands](05_Typing_Bash_Commands.md) section. Already familiar with Bash? Then you can continue with installing Git.


___________________________

[Previous : Install Git](06_Install_Git.md)  

[Go back  : Start Here](00_Start_Here.md)  
