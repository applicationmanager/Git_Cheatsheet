# Git Branches Cheat sheet

Useful notes about git branches 


## Rename Branch
```
$ git branch -m <old-branch-bame> <new-branch-name>                     
```
if you didn't write the old-branch-name then git will rename the current branch

## Delete Branch
```
$ git branch -d <branch-name-to-be-deleted>                     
```
if you got commit error then you can force the delete by using -D instead of -d


## Merge Branches
```
$ git checkout <taget-branch>                     
$ git merge  <source-branch>                       
```

## Compare Branches
```
$ git doff <branch-1>  <branch-1>                      
```

<br>
<br>

## Rearranging with Rebase
```diff
- Thou shall not rebase commits that exist outside your local repository
```
if you want a help to know the sha of the commit that you want to rebase from use one of these two wasy
1. See the branch history
```
$ git log --oneline                     
```
2. Get the original base of the "branch1" branch created from master. (just to know more where the base commit)
```
$ git merge-base branch1 master                
```

### Interactive Rebase
**squash  , fixup , edit , reword ,  drop**<br>
start the rebase from the commit sha
```
$ git rebase -i <commit-sha>                    
```
<br>

#### Rebase - Squash
Squash the commits you want to combine into a single commit (keep first line as "pick" and change the other lines to "squash to squash everything in one commit)
```
pick 1285e6c starting f1                     
squash b714e68 more work in f1                     
squash 985d1e1 completed f1                      
```
then you have to choose the commit message you want to use for these three commit as one commit message
then save the changes and exit
<br>
#### Rebase - fixup
combine one commit with another but keep the commit message of one of them
```
pick 1285e6c starting f2                    
fixup b714e68 more work in f2                     
pick 985d1e1 completed f1                      
```
Note: fixup will merge the commit with the commit above it. so make sure to reorder them in the way you want before proceeding
<br>
#### Rebase - edit
we can add more changes to an already existing commit.
```
edit 1285e6c starting f2                           
pick 985d1e1 completed f1                      
```
now when you save the file, the commit will pause on SHA 1285e6c and will allow you to change anything in the code you want
when you finish editing you should follow the below steps
```
git add .                           
pick commit -amend
git rebase -continue                   
```
now the git will continue the rebase process after adding the changing to the first commit.
<br>
#### Rebase - reword
This lets you change the commit message only
```
reword 1285e6c starting f1                         
reword 985d1e1 completed f1                      
```
after saving this file, git will open a new file for every "reword" labeled commit to enter a different message.
<br>
#### Rebase - drop
This lets you delete a commit
```
drop 1285e6c starting f1                         
pick 985d1e1 completed f1                      
```
#### Rebase - Solving conflict
when rebase face conflict then it will pause until you solve that conflict.
follow these steps to solve the conflict
* find the file changed because of the conflict
```
git diff                                         
```
then go to these file and fix the conflict then stage these files again by calling
```
git add .                                         
```
then continue the rebase by calling
```
git rebase --continue                                         
```
<br>
<br>

## Cherry Pick
git cherry-pick append any commit to the current working head you are working on.
It is an advanced feature. it copies (duplicate) the commit from one branch. not moving it. (it could case confusion when merge)
it is very easy to make. just find the target commit SHA from other branch then
```
git cherry-pick <target-SHA>                                         
```
<br>

# Git Remote
pull code and setup local branch
```
git clone <remote-url>                                      
```
"Origin" is the default name for remote server. but you want to change it then user
```
git remote add <name> <remote-url>                                      
```
to see a list of the remotes the URLs
```
git remote -v                                     
```
<br>

# Git Diff
To see difference between tips of branches
```
git diff <branch-name1>  <branch-name2>
git diff feature123 master                                      
```
To see difference between tips of branches in one file 
```
git diff <branch-name1>  <branch-name2> <file-anme>
git diff feature123 master file1.txt                                      
```

<br>
to see changes in only one branch since the other branch was separated from it

```
git diff <branch-name1>...<branch-name2>
git diff feature123...master                                      
```


<br>

# Git Reset
Move the branch to different commit
```
git reset --hard                                 
```
after rebase it copy the data from the new current commit to both working area and index.

```
git reset --mixed                                 
```
after rebase it copy the data from the new current commit to the index but leaves the current area alone. this is the default one.

```
git reset --soft                                 
```
after rebase it doesn't do anything to the working area and to the index. it just move the repository branch to the target commit

Example
```
git reset --hard HEAD                            
```
call this when you want to delete all your changes in the working area and in the index and be on status as the repository.
Using the HEAD instead of <commit-SHA> will keep the repository on the same commit and not move the branch to different commit.


<br><br>
  

# Git Stash
Use it when you want to record the current state of the working directory and the index, but want to go back to a clean working directory.The command saves your local modifications away and reverts the working directory to match the HEAD commit.
```
git stash --include-untracked               
```
--include-untracked means that also stash files that are still untracked, that have never been added, files that are entirely new in the working area
```
git stash list               
```
show a list of all the stashes you have made
```
git stash apply               
```
apply the changes from the latest stash to the working area and index. you can provide the name of the stash if you don't want to unstash the lhe latest one.




