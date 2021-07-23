# Exercise

- Create a new Git local repository called "research" in your Desktop.  
- Create a new file called `my_research.txt` containing the sentence “Science is awesome”.  
- Add and commit the change with a meaningful message.   
- Edit the file and change the text to “Science is messy”.  
- Compare what `git diff` shows versus what `git diff --staged` shows.  
- Add the change done to `my_research.txt` to Git staging area.  
- Compare again: what `git diff` shows versus what `git diff --staged` shows.  
- Commit the change with a meaningful message.  
- Recover the first version of the file using Git history tools.  
- Change the text to “Science is awesome, but hard”.  
- Add and commit the change with a meaningful message.  
- Revisit the snapshot of when `my_research.txt` said "Science is messy", but do not recover it.

_________________________________

# Solution

Create a new Git local repository called "research" in your Desktop:

    mkdir ~/Desktop/research
    cd research
    git init   

Create a new file called `my_research.txt` containing the sentence “Science is awesome”:

    touch my_research.txt
    echo “Science is awesome” > my_research.txt

Add and commit the change with a meaningful message:

    git add my_research.txt
    git commit –m “Created and added first line”

Edit the file and change the text to “Science is messy”:

    echo “Science is messy” >  my_research.txt

Compare what `git diff` shows versus what `git diff --staged` shows:

    git diff 
    git diff --staged 

Add the change done to `my_research.txt` to Git staging area:

    git add my_research.txt

Compare again: what `git diff` shows versus what `git diff --staged` shows:

    git diff 
    git diff --staged 

Commit the change with a meaningful message:

    git commit –m “Changing the line”
    cat my_research.txt

Recover the first version of the file using Git history tools:

    git log --oneline
    git checkout HEAD~1 file_A.txt  
    cat my_research.txt
    git add my_research.txt
    git commit –m “going back to XXXX” # replace XXXX with respective commit hash
    git log --oneline

Change the text to “Science is awesome, but hard”:

    echo “Science is awesome, but hard” > my_research.txt

Add and commit the change with a meaningful message:

    git add my_research.txt
    git commit –m "Changing line"
    cat my_research.txt

Revisit the snapshot of when `my_research.txt` said "Science is messy", but do not recover it;

    git log --oneline
    git show HEAD~2 my_research.txt
    git show HEAD~2:my_research.txt

_________________________________

[Previous  : Tracking Files](04_Tracking_Files.md)  

[Next      : Ignoring Files](06_Ignoring_Files.md)
