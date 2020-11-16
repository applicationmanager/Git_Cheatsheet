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
move a file in the working area and also update the index. it doesn't touch the repository.


