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


