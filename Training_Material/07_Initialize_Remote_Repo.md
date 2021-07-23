In order to **create a remote repository** (remember in Gitlab: *project* and *repository* are in practice *interchangeable* terms), go to yout Gitlab account and:

![Figure new project](../Figures/Git-New-Project.png)

- click on the **New project** button (click on the `+` button at the top of the page; see figure above).
- Create blank project.
- Name the project using an **underscore** and your **initials**. For example: if your name is **John Donald Smith**, then name the project: `Project_JDS`. 
- **Do not** initialize the repository with a README.
- Create project.

You have just created a *remote* repository. 

For now the *remote* repository is empty. We can sync it to our *local* `Project_X` repository.

## Adding the remote

In the Gitlab go to the project you have just created > **Project overview** > **Details** > **Clone** button. Copy the **https_key**. This is the http address you will give to your *local* `Project_X` Git repository, in order to "link" the *local* `Project_X` with the *remote* repository.

In your device, go to `Project_X`:

```
    cd ~/Desktop/Project_X
    git remote add origin https_key
``` 

Replace `https_key` by the corresponding key of the Gitlab (online) repository. `git remote` will tell Git which is the *remote* repository that should be "linked" to the *local* `Project_X` repository. We can check the remote has been correctly set up by using:

```
    git remote -v
```

Note that the *remote* repository is *locally* recognized by Git as the **origin**. In that way, Git "knows" to which *remote* **origin** (Gitlab repository) the *local* changes you make should be synced to.

We can now push the contents of our *local* `Project_X` to the **origin** by using the `git push` command:

```
    git push origin master
```

This will "copy" the contents of the (*local*) **master** `Project_X` repository to the (*remote*) **master** in the Gitlab (recognized locally by your system as the **origin**).

Let us modify the *local* `Project_X` by creating a new file and adding content to it. 

```
    git pull origin master
    touch file_C.txt
    echo "First line of file_C" > file_C.txt
    git add file_C.txt
    git commit -m "Created and added first line to file_C"
    git log --oneline
```

To update the *remote* repository with the changes we made *locally*, we can then *push* by doing:

```
    git push origin master
```

You can see now that the `file_C.txt` has appeared in the online Gitlab repository as well.

___________________________________________________

## Summarizing

When working with remotes:

- you will have a *local* Git repository, created by typing `git init` in a working directory (in your device). This creates the *local* **master** branch by default.  

- You will have a *remote* Git repository in (for example) Gitlab. This *remote* repository also has a **master** branch (created by default when the *remote* repository is created). This **master** branch is recognized by your *local* Git repository as the *remote* **origin**.  

- In order to work based on the latest updated *remote*, you will be pulling the changes from the *remote* repository to your *local* repository using:  

```
    git pull origin master
```

- You will be making changes to your files *locally*, adding them and committing them. To "synchronize" the *remote* repository with all the changes you make *locally*, you will be *pushing* the changes from the *local* repository to the *remote* repository using:  

```
    git push origin master
```

This **pushing** and **pulling** workflow becomes extremely important when you work with more branches, either by yourself (you create branches to explore testing of the code for example) or in collaboration with others (each collaborator can have its own branch for example). 

___________________________________________________

## Cloning a repository

Aside creating an empty *remote* repository and pushing things to it from your *local* repository, you can also just clone a *remote* repository. For that you only need its **https_key**. Then you can do:

```
    git clone https_key
```

Where **https_key** is the http address of the *remote* repository you want to "copy" to your local device. It is important to mention that when cloning a repository with `git clone`, Git automatically defines as **origin** the repository with the **https_key** you provided. This you can check by doing:

```
    git remote -v
```

__________________________

### Parenthesis

- If you want to make sure you have the right **origin**, you can check the **current origin** by typing `git remote –v`. If the **origin** is not the right one, then you can always change it with:

```
    git remote add origin https_key
```

- You can also remove the *remote* **origin** by using:

```
    git remote rm origin
```
_____________________________

Keep in mind **origin** is the alias with which your device refers to the *remote* (Gitlab) repository. In principle you can change this alias, but you are advised not to (especially when learning how to use Git). Having said that, you can use: 

- `git remote add name_remote https_key` : to add a new remote called `name_remote` with the https address `https_key` (this is how we have defined the **origin** before). You can use such instruction to define other *remote* repositories. For example, an **upstream** *remote* repo. 

- `git remote set-url name_remote new_https_key` :  in case a *remote* has been moved, you can change the url of the remote with alias `name_remote`, by specifying the new url of the *remote* repository in `new_https_key`.  

- `git remote rename old_name new_name`: changes the alias of the *remote* from the `old_name` to a `new_name`.  

_____________________________

[Previous  : Ignoring Files](06_Ignoring_Files.md)  

[Next      : Exercise 2](08_Exercise_02.md)


