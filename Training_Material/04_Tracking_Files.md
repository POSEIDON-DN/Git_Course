So far we have initialized a Git local repository and we are in the local **master**. But it is so far empty.

We can check the state of a Git repository by doing:

```
    git status
```

This will show you the *tracked* and *untracked* files. The “untracked” file(s) message means that there is(are) file(s) in the directory that Git is **not keeping track of**. 

When you work on files inside the directory where Git has been initialized, you have to tell Git *"hey, keep track of this file"* and *"hey, record the changes made to this file and add this metadata to those changes"*. The first thing is calling **adding** files to Git, and the second thing is making a **commit** of changes made to a file. 
 
Let’s create a file called `file_A.txt` and add a line to it:

```
    touch file_A.txt
    echo "This is the first line of local file_A" > file_A.txt
    cat file_A.txt
```

Let us check the status of the Git repository again:

```
    git status
```

To make Git *aware* of the created files we need to add the files to Git's so-called **staging area**:

```
    git add file_A.txt 
```

We can check again the status:

```
    git status
``` 

Once we have made changes to a file that we want to record with consistent metadata, it is time to **commit** such change. To commit a change we type: 

```
    git commit -m “Created and added first line to file_A” 
```  

This will tell Git to **record such an important change** with the **descriptive message** `“Created and added first line to file_A”`. If you only type `git commit`, the editor you set by default (when configuring Git) will open so that you can write the **descriptive message**. 

**Recommendation:** always try to keep the message as short as possible. See the following [blog](https://chris.beams.io/posts/git-commit/) where you can find principles on how to write Git commit messages.

_____________________________________________

## Difference between adding and committing

*Adding* and *committing* might be a bit confusing at first. Think as if you were preparing the clothes you will take for a trip. You first put the clothes on your bed to have an overview of what you will taking to the trip. In this case, the act of *putting the clothes on the bed* would be `git add`; while the *bed* itself would the so-called **staging area**. 

Once you have *finally decided what to take* on your trip, you *put the clothes on the suitcase*. In this case, *putting the clothes on the suitcase* would be like doing a `git commit`.
_____________________________________________

Now that we have **added** and **committed** the change made to `file_A.txt`, we can check the commit by doing:

```
    git log
```

The output of `git log` is quite extensive. If we want to have the *summarized* version of this output, we can use:

```
    git log --oneline
```

In the output of `git log` we can see the identifier of each commit made. Such identifier is referred to as the **hash** of the commit. We can use these hashes to refer to the different versions of a given file.

_____________________________________________

Let's add a second line to the `file_A.txt`:

```
    echo "This is a second line of file_A" >> file_A.txt
    cat file_A.txt
```

Before staging the change we can use another command:

```
    git diff
```

This shows the changes you have done *locally* compared to the last version that was **committed**. Let's add the changes made to `file_A.txt` to the staging area:

```
    git add file_A.txt
```

We can now use the following command to show the changes we have done *locally* (compared to the last version that was **committed**), and that have been **added** (with `git add` to the *staging area*) but **not yet committed** (with `git commit`):

```
    git diff --staged
```

We can now commit the change with:

```
    git commit -m "Added second line to local file_A"
    git log --oneline
```

Let us say we did not like the change we just made, and we are thinking about going back to the previous version of the file. What we can do is to use the `git show` command to see what changes correspond to a given commit, and be sure that we want to recover such version. Let us say the hash of the commit we are interested in inspecting starts with the following characters: `9354`. 

``` 
    git show 9354 file_A.txt
    git show 9354:file_A.txt
``` 

This will show us what changes where done to the `file_A.txt` in that commit. This command does not restore the file to that version. It just shows what was the version of the file in that commit. If we really decide to go back to that version, then we can use `git checkout`:

```
    git checkout 9354 file_A.txt
```

To make this change *official* we need to add and commit it:

```
    git add file_A.txt
    git diff --staged
    git commit -m "Recovered 9354 version of file_A"
```

We can now check the history of commits:

```
    git log --oneline
```

We can also use `git diff` to compare two different versions of a file by using the respective hashes. For example: if we want to compare the last committed version (whose hash can also be referred to as `HEAD`) with the one before the last one (whose hash can also be referred to as `HEAD~1`), then we can do:

```
    git diff HEAD~1 HEAD file_A.txt
```

_____________________________________________

## Parenthesis on **git diff**

Check out [this video](https://youtu.be/Wk-IK2uJt28) where the presenter talks about `git diff` and configuring the `diff.tool` global Git configuration variable to visualize the difference between two version using the `vimdiff` tool (by using the `difftool` command). A few remarks about the video:

- The presenter in this case is working in a Linux system (that is why he uses `man` as a help command) and he is using `vim` as his default editor.  
- The presenter talks about the `HEAD` variable. Keep in mind that the `HEAD^` that he uses is the same as `HEAD~1`, which indicates *the commit before the last one*. Do you want to see more about how to refer to commits without writing their hashes but using `HEAD` instead? It can get a bit confusing! But our dear friend [Stack Overflow](https://stackoverflow.com/) has quite a few discussions on it like [this one](https://stackoverflow.com/questions/2221658/whats-the-difference-between-head-and-head-in-git).  
- The presenter often talks about the **index**. If you go to the `./git` directory, you will see an `index` file which gets constantly updated. In very rough terms the **index** helps Git "know" what is being **tracked** and what is **not being tracked but has been changed** in a Git repository. That is how Git can give you messages letting you know whenever you have made changes to a file that you have not added nor committed yet.

___________________________________

## Parenthesis on **git checkout**

**Never** do `git checkout HEAD` WITHOUT SPECIFYING THE FILE, because Git will restore all files to whichever last version that was committed (losing all changes you have recently made!).

_________________________________

## Rule of thumb: when to *add* and when to *commit*?

- Every time you make **small changes** to a file, use `git add file1` (where `file1` is the name of the file you have been working in). 

- Every time you **finalize an important task**, do a **commit**. Remember **commits** have **descriptive metadata** attached to them. Hence, try to commit significant changes and use a **descriptive message** that will allow your future self (and that of your colleagues) to understand in a few words what change you did in that **commit**. 

_________________________________

[Previous  : Initialize Local Repo](03_Initialize_Local_Repo.md)  
 
[Next      : Exercise 1](05_Exercise_01.md)



