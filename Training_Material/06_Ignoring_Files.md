Within all projects there will be files you will not want Git to keep track of. Examples of files to be ignored by Git are:

- log files   
- files with (API) keys/credentials  
- files with sensitive information (especially if the project is shared with others)  
- system files like `Desktop.ini` in Windows, `.DS_Store` on macOS, etc.  
- files ending with `~` symbol  

In [gitignore.io](https://www.toptal.com/developers/gitignore) you can find other type of files that are recommended to be ignored by Git depending on your operating system, IDE or programming language.  

## How to tell Git to ignore the files?

Let us create more files in our `Project_X` local repository:

```
    touch file_B.txt 
    echo “First line to file_B” > file_B.txt
    mkdir data
    cd data/
    touch file_1.txt 
    touch file_2.txt
    cd ..
```

Now we have two files and a `data/` subdirectory. 
Let us say we want Git to ignore the changes made to `file_B.txt` and all the files in `data/`. To do this we need to create a file in the directory of the project (where Git has been initialized). The file has to be named `.gitignore` (it is a hidden file). This file will contain a list of files to ignore. 

```
    touch .gitignore
    echo "data/" > .gitignore
    echo "file_B.txt" >> .gitignore
    cat .gitignore
```

For Git to start ignoring those files, we have to add and commit the `.gitignore` file.

```
    git add .gitignore
    git commit –m “Ignore file_B and files in data/”
    git status
```

We can now make changes to `file_A.txt` and `file_B.txt` for example, and Git will only *notice* `file_A.txt` has been changed.

```
    echo “Adding second line to file_B” >> file_B.txt
    echo “Adding fourth line to file_A” >> file_A.txt
    git status 
    git add file_A.txt 
    git commit –m “Adding fourth line to file_A”
    git status
```
__________________________________

### Parenthesis on `git ignore`

- If for some reason you would like Git to track a file that is included in `.gitignore`, you can then *add* the file to the **staging area** by using the `f` flag, forcing Git to consider it:  

```
   git add -f file_to_add
```

where `file_to_add` would be the file that is in `.gitignore`, but you *now* want Git to track.  

- If you want to see what files or directories are being ignored by Git, use:

```
    git status --ignored
```

- If you want Git to ignore all files with a given extension **except one file**, you can use the `!` symbol. For example: let's say you tell Git to ignore all files with `csv` extension except for `register_total.csv`. Then `.gitignore` file should look like this:

```
   *.csv  
   !register_total.csv
```

- You can also include comments in `.gitignore` files, in case you want to provide more documentation about the files that are being ignored. The lines (in the `.gitignore` file)  starting with `#` symbol, are considered as *comments*.  

- Keep in mind Git will not ignore the file if you have already committed it. To ignore a file that has already been committed, you have to *untrack* it first by typing:

```
    git rm --cached file_to_ignore
```

where `file_to_ignore` is the name of the file that was committed at some point, but that you now want Git to ignore it.

__________________________________

[Previous  : Exercise 1](05_Exercise_01.md)  

[Next      : Initialize Remote Repo](07_Initialize_Remote_Repo.md)

