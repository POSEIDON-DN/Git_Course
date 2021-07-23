In this page you will find the instructions to install **Git** on your device.

## What is Git?

**Git** is a sort-of back-end machinery that performs version control of files. Services like **Github** and **Gitlab** make use of this Git machinery.

## How does version control work?

Version control systems start with a base version of a file and then **record all changes** made to it with useful metadata (e.g., information about those changes). This helps you to keep track and understand all the **history of changes** made to each tracked file. A version control system also allows you to **retrieve different versions** of each file (e.g., in case you need to recover a previous version of a file). In that sense, Git allows you to keep track of all changes made to a file as a-sort of "hidden information". So that instead of seeing a visible (most likely long) list of files in your working directory (e.g., `file_v1.py`, `file_v2_final.py` ... `file_v10_final_FINAL.py`), you have a single **hidden directory** (the hidden `.git/` directory) where all that information is stored and it is easily retrievable. 

Aside keeping track of file changes (each record of these changes is called a **commit**), a version control system also allows you to merge the changes made by different people or by different lines of development. 

The complete history of **commits** for a particular project and their metadata make up what is referred to as a **repository**. Repositories can be kept in sync across different computers, facilitating collaboration among different people. In our Gitlab instance, a repository can also be referred to as a **project**.

![phd101212s](../Figures/phd101212s.gif)

[“Piled Higher and Deeper”](http://phdcomics.com/comics/archive.php?comicid=1531) by Jorge Cham, [http://www.phdcomics.com](http://www.phdcomics.com)

Version control can become a bit complicated -especially when working in collaboration with others or following different lines of development- so it is important to learn well the basics.


## Local versus Remote repository

When doing version control with Git and using (for example) Gitlab, you will be working *locally* on the (code) files in your device. And you will have this *local* (Git) repository "synchronized" with a *remote* repository in Gitlab.

Thus in order to do version control with Git on your *local* files (and "synchronize" it with a *remote* repo), you need to **install Git** in your device (your work laptop/station).

________________________

[Next     : Install Git on Windows](07_Install_Git_on_Windows.md)  
[Next     : Install Git on MacOS](08_Install_Git_on_MacOS.md)  
[Next     : Install Git on Linux](09_Install_Git_on_Linux.md)  

[Previous : Install Bash](01_Install_Bash.md)  

[Go back  : Start Here](00_Start_Here.md)  
