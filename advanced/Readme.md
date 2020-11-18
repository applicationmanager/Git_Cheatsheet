# How Git work

```
$ git add 
```
Copies data from the working area to the index. it doesn't impact the repository.<br><br>
```
$ git commit 
```
Copies data from the index to the repository. And it also creates additional objects in the repository (commit object) and it moves references to the repository.<br><br>

```
$ git checkout 
```
Copies data from the repository to the index and to the working area. And it moves the HEAD reference in the repository.<br><br>

```
$ git rm 
```
Deletes files from both the working area and the index. it doesn't touch the repository at all<br><br>

```
$ git mv  
```
move a file in the working area and also update the index. it doesn't touch the repository.<br><br><br><br>

### tip 1
if you want to reset only one file from the repository to the index without changing this file in the working area.
```
$ git reset HEAD <file-name>
```
As you can see we didn't add any flag to the command so it is by default --Mixed<br>
But this command doesn't work if we want to only reset one file to the working are. --HARD is not working for one file,
instead you can use the checkout command instead 
```
$ git checkout HEAD <file-name>
```
This command will move one file from repository to both index and working area.<br><br><br><br>

### tip 2
if you want to commit only part of the file changes (not all of them) then you can use this command
```
$ git add --patch  <file-name>  
$ git add -p  <file-name>  
```
git will look into these changes in the file and divid them into sections called hunks. and give you a list of options [y,n,q,a,d,s,e,?] and if you want to see what these option are then press the ? button<br>
important options: <br>
y: stage this hunk <br>
n: don't stage this hunk <br>
s: split into smaller hunks<br><br><br><br>

### tip 3
we have two new commands already exist inside the git checkout command.
```
$ git switch
$ git restore
```
but git switch works for switching between branches and git restore works on between commits in same branch. Please read more about these two commands.
```
$ git restore --staged <file-name> 
```
also used to copy the file from the repository to the index (un-staging file)<br><br><br><br>


### tip 4 History
below command to see details about the latest commit
```
$ git show <latst-commit-SHA>
$ git show HEAD
$ git show <branch-Name>
```
below command to see details about parent commit of the current commit
```
$ git show <parent-commit-SHA>
$ git show HEAD^
$ git show HEAD~1
```
use HEAD and then add to it the number of parent level you want to check or just add "~" and number of levers <br> ex:Head^^^  or Head~3<br>
if the second parent Head~2 has two merged parents then you don't need to type HEAD^3, you will need to use HEAD~2~1 or HEAD~2~2
```
$ git show HEAD@{"1 month ago"}
```
use the above if you just want to know where this branch was one month ago