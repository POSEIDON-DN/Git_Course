# Let us start working with Git

When working with Git on your *local* files, you can:

- **initialize** a (*local*) repository (in your work laptop/station) or,   
- **clone** a *remote* repository (so that you have a "copy" of the *remote* repository in your *local* device).

## Initialize a *local* repository

Go to the directory where you have the files you want Git to start tracking. Let's say you want to start working on **Project_X** in `~/Desktop/Project_X`. If you have not created the directory `Project_X` inside `~/Desktop`, then remember you can do that with Bash using the `mkdir` command:  
```
   cd ~/Desktop  
   mkdir Project_X  
   cd Project_X 
```
Now you can **initialize** a Git repository there by typing:  
```
    git init
```
`git init` initializes a Git repository in the directory where you have the files you want Git to start tracking. Git will create there a **hidden directory** called `.git` (you can see it by doing `ls -a`). The `.git/` directory is where the history of all (tracked) files (including the ones in sub-directories) will be stored. 

________________________________________

## Parenthesis

By deleting the `.git` directory (by doing `rm -rf .git`) you will be deleting the respective Git repository. You will not delete the files. You will only delete the recorded history of changes of the files.

Also be aware **Git does not track the creation or removal of directories**. Git **only tracks files**. It will automatically “know” *where* the files are. But it will not track the creation of empty directories.
_________________________________________

## The Master Branch

When doing `git init` in your device (work laptop/station), Git *by default* creates what is called: the **master** branch. This is the *local* **master** branch. 

What is a branch? A **branch** can be thought of as a **separate copy** of a repository where you can make changes, and those changes will stay in that branch, unless you merge that branch with another branch. In that sense, each branch allows you to follow a **different line of development** of the project. You can have several branches for the same project, and you can name each branch differently. For now, just remember that `git init` creates a *local* **master** branch by default.
________________________________________

### Important to keep in mind: do not nest Git repos!

**Do not nest Git repositories**. In other words: do not do `git init` in a sub-directory of the directory where Git has already been initialized. **This will just create conflicts!** You only initialize a repository once. 
 
________________________________________

[Previous : Setting up Git](02_Setting_Up_Git.md)  

[Next     : Tracking Files](04_Tracking_Files.md)

