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
$ git clone https://github.com/udacity/course-git-blog-project
```
This command:

* takes the path to an existing repository
* by default will create a directory with the same name as the repository that's being cloned
* can be given a second argument that will be used as the name of the directory
* will create the new repository inside of the current working directory


#### Git status 
The **git status**  command will display the current status of the repository.
```
$ git clone https://github.com/udacity/course-git-blog-project
```
This command:
* tell us about new files that have been created in the Working Directory that Git hasn't started tracking, yet
* files that Git is tracking that have been modified
* a whole bunch of other things that we'll be learning about throughout the rest of the course ;-)


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
* **the SHA** - display the complete SHA for every single commit. Each SHA is unique.
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



#### Git ______ 
The **____**  _____.
```
$ git ______
```
This command:
* _____
* _____

#### Git ______ 
The **____**  _____.
```
$ git ______
```
This command:
* _____
* _____
