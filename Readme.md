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

