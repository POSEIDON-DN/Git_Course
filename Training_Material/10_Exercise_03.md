# Exercise

Which of the following combos (one or more) creates a new branch and makes a commit to it? 

a)

    git branch new-branch
    git add file.txt
    git commit


b)

    git add file.txt
    git branch new-branch
    git checkout new-branch
    git commit



c)

    git checkout -b new-branch
    git add file.txt
    git commit



d)

    git checkout new-branch
    git add file.txt
    git commit


________________________________

# Solution 

Which of the following combos (one or more) creates a new branch and makes a commit to it? 

a)

    git branch new-branch
    git add file.txt
    git commit

This creates a new branch called **new_branch**, but it does not switch to that branch. So the commit is done in the current branch, and not in the **new_branch**.

b)

    git add file.txt
    git branch new-branch
    git checkout new-branch
    git commit

This adds the `file.txt` to the staging area of the current branch. It then creates a new branch, switches to it and it does there the commit. When creating the new branch, the staging area is also "copied". Thus the commit is indeed done in the **new-branch**. 

c)

    git checkout -b new-branch
    git add file.txt
    git commit

This creates a new branch called **new-branch** and it switches to it. It then stages the `file.txt` and commits it. Thus the commit is indeed done in the **new-branch**.

d)

    git checkout new-branch
    git add file.txt
    git commit

This switches to the branch called **new-branch** and stages the files and commits it there. However it does not create the **new-branch**. Thus (assuming the **new-branch** needs to be created) we would get an error from Git.

______________________________________

[Previous  : Branches](09_Branches.md)  

[Next      : Forking](11_Forking.md)
