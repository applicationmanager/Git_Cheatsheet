# Git ChaetSheet

follow up with the udacity project "Version Control with GitHub" I created this repository

## Getting Started

To download Git:
go to https://git-scm.com/downloads
download the software for Windows then
install Git choosing all of the default options


## Create Course Directories
Heads up! We'll be using the following terminal commands in this lesson:
```
ls - used to list files and directories                                   
mkdir - used to create a new directory                                    
cd - used to change directories                                           
rm - used to remove files and directories     
touch - create a file                            
```

## Create Course Directories
create a directory called "project-name" <br/>
inside that, create another directory called "project-name" <br/>
use the cd command to move into the "project-name" directory

## Listing Git Commands
#### Git Init
Use the **git init** command to create a new, empty repository in the current directory.
```
$ git init
```
Running this command creates a hidden .git directory. This .git directory is the brain/storage center for the repository. It holds all of the configuration files and directories and is where all of the commits are stored.

#### Git Clone 
The **git clone** command is used to create an identical copy of an existing repository.
```
$ git clone https://github.com/applicationmanager/Git_Cheatsheet.git
```
This command:

* takes the path to an existing repository
* by default will create a directory with the same name as the repository that's being cloned
* can be given a second argument that will be used as the name of the directory
* will create the new repository inside of the current working directory


#### Git status 
The **git status**  command will display the current status of the repository.
```
$ git status
```
This command:
* tell us about new files that have been created in the Working Directory that Git hasn't started tracking, yet
* files that Git is tracking that have been modified
* a whole bunch of other things that we'll be learning about throughout the rest of the course ;-)
<br/>
<br/>
<br/>
<br/>
<br/>

#### Git log 
The **git log**  By default, this command displays:the SHA, author, date and message of every commit in the repository
```
$ git log
```

<details>
    <summary>Navigating The Log</summary>
    <p>
        <ui>to scroll down, press
           <ul><kbd>j</kbd> or <kbd>↓</kbd> to move down one line at a time</ul>
           <ul><kbd>d</kbd> to move by half the page screen</ul>
           <ul><kbd>f</kbd> to move by a whole page screen</ul>
        </ui> 
        <ui>to scroll up, press
           <ul><kbd>k</kbd> or <kbd>↑</kbd> to move _up_ one line at a time</ul>
           <ul><kbd>u</kbd> to move by half the page screen</ul>
           <ul><kbd>b</kbd> to move by a whole page screen</ul>
        </ui> 
        press <kbd>q</kbd> to quit out of the log (returns to the regular command prompt)
    </p>
</details>

This command:
* **the SHA**  - display the complete SHA for every single commit. Each SHA is unique.
* **the author** - output displays the commit author for every single commit! It could be different for other repositories that have multiple people collaborating together
* **the date** - will display the date for each commit
* **the commit message** - this is one of the most important parts of a commit message...we usually always want to see this

```
$ git log --oneline
```
This command:
* lists one commit per line
* shows the first 7 characters of the commit's SHA
* shows the commit's message

**the** <key>q</key> **key gets out of the git log view**. We're still using git log but are just passing a flag to change how the information is displayed. So the q key still works and returns the terminal to the command prompt.


```
$ git log --stat
```
This command:
* displays the file(s) that have been modified
* displays the number of lines that have been added/removed
* displays a summary line with the total number of modified files and lines that have been added/removed


```
$ git log -p
$ git log --patch
```
This command:
* displays the files that have been modified
* displays the location of the lines that have been added/removed
* displays the actual changes that have been made
* That's right! *git log -p -w* will show the patch information, but will not highlight lines where only whitespace changes have occurred.


```
$ git log -p fdf5493
$ git show
```
By supplying a SHA, the git log -p command will start at that commit! No need to scroll through everything! Keep in mind that it will also show all of the commits that were made prior to the supplied SHA
The git show command will show only one commit. So don't get alarmed when you can't find any other commits - it only shows one. The output of the git show command is exactly the same as the git log -p command.

```
$ git log --oneline  --graph --all
```
The *--graph* flag adds the bullets and lines to the leftmost part of the output. This shows the actual branching that's happening. The *--all* flag is what displays all of the branches in the repository.<br/>
<br/>
<br/>
<br/>
<br/>
#### Git Add
The **git add**  command is used to move files from the Working Directory to the Staging Index..
```
$ git add  <file1> <file2> … <fileN>
$ git add  .
```
This command:
* takes a space-separated list of file names
* alternatively, the period <kbd>.</kbd>  can be used in place of a list of files to tell Git to add the current directory (and all nested files)

#### Git Commit
The **git commit**  command takes files from the Staging Index and saves them in the repository.
```
$ git commit
$ git commit -m "add your commit message here"
```

This command:
* will open the code editor that is specified in your configuration
* if you didn't use the -m flag then the terminal will show you the changes to add the message in first line. click on keyboard on <kbd>ESC</kbd> button then <kbd>:</kbd><kbd>w</kbd><kbd>q</kbd> then click <kbd>↩</kbd> button to commit




#### Git Diff
The **git diff**  command is used to see changes that have been made but haven't been committed, yet:
```
$ git diff
```
This command:
* the files that have been modified
* the location of the lines that have been added/removed
* the actual changes that have been made



#### .gitignore File
The **.gitignore**  file is used to tell Git about the files that Git should not track. This file should be placed in the same directory that the .git directory is in.<br/>
* blank lines can be used for spacing
* <kbd>#</kbd> - marks line as a comment
* <kbd>* </kbd> - matches 0 or more characters
* <kbd>?</kbd> - matches 1 character
* <kbd>[abc]</kbd> - matches a, b, _or_ c
* <kbd>**</kbd> - matches nested directories - <kbd>a/ **/z</kbd> matches<br/>
    * a/z<br/>
    * a/b/z<br/>
    * a/b/c/z<br/>

So if all of the 50 images are JPEG images in the "samples" folder, we could add the following line to .gitignore to have Git ignore all 50 images.
```
samples/*.jpg
```
<br/>
<br/>
<br/>
<br/>
<br/>

### Git Tag
The **git tag**  This will open your code editor and wait for you to supply a message for the tag. 
```
$ git tag -a v1.0
```
CAREFUL: In the command above (git tag -a v1.0) the -a flag is used. This flag tells Git to create an annotated flag. If you don't provide the flag (i.e. git tag v1.0) then it'll create what's called a lightweight tag.<br/>Annotated tags are recommended because they include a lot of extra information such as:
* the person who made the tag
* the date the tag was made
* a message for the tag

Because of this, you should always use annotated tags.<br>
A Git tag can be deleted with the -d flag (for delete!) and the name of the tag:

```
$ git tag -d v1.0
```
But what if you wanted to tag a commit that occurred farther back in the repo's history?All you have to do is provide the SHA of the commit you want to tag!

```
$ git tag -a beta a87984
```
This command will tag any commit in the entire git repository!<br>

You need to take the additional step of pushing your tags using the following command.

```
$ git push --tags <remote>
```
If you're pushing to your origin you can ignore the <remote> part.



#### Git Branch
The **git branch** command is used to interact with Git's branches:
```
$ git branch
```
This command:
* list all branch names in the repository
* create new branches
* delete branches

To create a branch, all you have to do is use git branch and provide it the name of the branch you want it to create. So if you want a branch called "sidebar" use: git branch sidebar
```
$ git branch {branch_name}
```


To create a branch with name and have it point to the commit with SHA. So if you want a branch called "sidebar" and point to commit 42a69f use: git branch sidebar 42a69f
```
$ git branch {branch_name} {commit-sha}
```



to delete the branch, you'd use the -d flag. The command below includes the -d flag which tells Git to delete the provided branch
```
$ git branch -d {branch_name}
$ git branch -D {branch_name}   //campital D To force deletion
```


if you created the branch locally and you want to upload it to github
```
git push --set-upstream origin sidebar
```





#### Git Checkout {branch_name}
The **git checkout {branch_name}**  go into the repository and pull out all of the files and directories of the commit that the branch points to
```
$ git checkout {branch_name}
```
This command:
* will remove all of the files that are referenced by commits in the master branch
* will replace them with the files that are referenced by the commits in the sidebar branch

```
$ git checkout -b {branch_name}
$ git checkout -b {branch_name} {parent_branch_name}
```
the git checkout command can actually create a new branch, too? If you provide the -b flag, you can create a branch and switch to it all in one command.


#### Git Merge
The **git merge {name_of_branch_to_merge_in}** command is used to combine Git branches:
```
$ git merge {name_of_branch_to_merge_in}
```
When a merge happens, Git will:
* look at the branches that it's going to merge
* look back along the branch's history to find a single commit that both branches have in their commit history
* combine the lines of code that were changed on the separate branches together
* makes a commit to record the merge

There are two types of merges:
* Fast-forward merge – the branch being merged in must be ahead of the checked out branch. The checked out branch's pointer will just be moved forward to point to the same commit as the other branch.
* the regular type of merge
    * two divergent branches are combined
    * a merge commit is created


#### Merge Conflict Recap
A merge conflict happens when the same line or lines have been changed on different branches that are being merged. Git will pause mid-merge telling you that there is a conflict and will tell you in what file or files the conflict occurred. To resolve the conflict in a file:

* locate and remove all lines with merge conflict indicators
* determine what to keep
* save the file(s)
* stage the file(s)
* make a commit

Be careful that a file might have merge conflicts in multiple parts of the file, so make sure you check the entire file for merge conflict indicators - a quick search for <<< should help you locate all of them.


<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

# Undoing Changes

#### Git commit --amend
The **____**  _____.
```
$ git ______
```
This command:
* _____
* _____



#### Git ______
The **git commit --amend**  will let you include files (or changes to files) you might've forgotten to include. Let's say you've updated the color of all navigation links across your entire website. You committed that change and thought you were done. But then you discovered that a special nav link buried deep on a page doesn't have the new color. You could just make a new commit that updates the color for that one link, but that would have two back-to-back commits that do practically the exact same thing (change link colors).<br>
Instead, you can amend the last commit (the one that updated the color of all of the other links) to include this forgotten one. To do get the forgotten link included, just:
* edit the file(s)
* save the file(s)
* stage the file(s)
* and run git commit --amend
```
$ git commit --amend
```
This command:
* _____
* _____


if you make a merge on the wrong branch, use this command to undo the merge:
```
$ git reset --hard HEAD^
```
(Make sure to include the ^ character! It's a known as a "Relative Commit Reference" and indicates "the parent commit". We'll look at Relative Commit References in the next lesson.)



test
