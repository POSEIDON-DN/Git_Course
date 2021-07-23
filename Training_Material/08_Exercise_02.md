When pulling and doing merges, **conflicts** will surely arise. Conflicts occur:

- when there have been **changes to the same lines of the same file** (for example, two collaborators change the same lines of a file)   

- when a file has been **deleted** but it has been **edited** at the same time (for example, one collaborator deleted the file, but the other collaborator edited it) 

In general, when conflicts appear Git will show very descriptive messages of *where* the conflict is and *what a solution could be*. Whenever a conflict arises, you must **solve it**. 

_____________________________________________________

Let us exemplify how a conflict can arise and how to solve it with the following exercise.

# Exercise 

- Go to the remote (Gitlab) repository you created.  
- Change the first line of the `file_C.txt` with the following message: "Writing the first line remotely".  
- Go to the local repository in `~Desktop/Project_X` linked to the remote repository and modify the same line of `file_C.txt` to something different such as: "Writing the first line locally".  
- Add and commit the change with a meaningful message.  
- Pull the changes of the remote (Gitlab repository) to the local master. What do you see?   

_____________________________________________________

# Solution

- Go to the remote (Gitlab) repository you created.  

- Change the first line of the `file_C.txt` with the following message: "Writing the first line remotely".  

- Go to the local repository in `~Desktop/Project_X` linked to the remote repository and modify the same line of `file_C.txt` to something different such as: "Writing the first line locally".  

```
    cd ~Desktop/Project_X
    git remote -v
    cat file_C.txt
    echo "Writing the first line locally" > file_C.txt
```

- Add and commit the change with a meaningful message

```
    git add file_C.txt
    git commit -m "Update file_C locally"
```

- Pull the changes of the remote (Gitlab repository) to the local master. What do you see?

```
    git pull origin master
```

We see the CONFLICT message. When merging branches Git will **fetch** the changes, detect conflicts (if any), and if there are conflicts, it will **refuse to merge** the two copies of the repository, and the conflict(s) will be pointed out.  

We now need to solve the conflict. How can we do that?

- Edit the *local* file to solve the conflict

Notice the *local* change you made is preceded by `<<<<<<< HEAD`, and then followed by a `=======`. 
Then the changes made in the *remote* repository appears followed by a `>>>>>>>`. 
The very long string afterwards is the hash of the *remote* commit.

In order to **fix** this, you just have to **modify** the file. Let us say we want to keep both lines.

- Add and commit the change with a meaningful message

```
    git add file_C.txt
    git commit -m "Solving conflict keeping both lines"
    git log --oneline
```
- Push changes from the *local* **master** to the *remote* **master**

```
    git push origin master
```

Take a look at the `file_C.txt` in the remote Gitlab repository and its commit history.

_____________________________________________

### Interested in more Conflicts?

Take a look at [this video](https://youtu.be/xNVM5UxlFSA) to see what a conflict looks like. In this video the presenter uses [**VSCode**](https://code.visualstudio.com/download) as the editor and he is working in a terminal within **VSCode**. But you can see the Git commands he uses to solve the conflict with the `content.txt` file. 

_____________________________________________________

[Previous  : Initialize Remote Repo](07_Initialize_Remote_Repo.md)  

[Next      : Branches](09_Branches.md)












