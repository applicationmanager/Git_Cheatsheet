#Git Submodules
##Adding submodules
connects the submodules's git repository to our current repository<br>
\# Add a submodule to the repo in the 'external/repo1' directory (Single line command)
```
$ git submodule add https://github.com/applicationmanager/crispy-succotash.git external/repo1                                             
```
then the git will create a file .gitsubmodules file directly when we add a new submodule and it will contains the information about all the submodules we have
```
[submodule "external/repo1"]
	path = external/repo1
	url = https://github.com/applicationmanager/crispy-succotash.git          
```
<br><br><br>
##Cloning a Repository with Submodules
Properly initializing the repository to pull down the referenced submodules<br>
\# Clone the repository
```
$ git clone https://github.com/applicationmanager/crispy-succotash.git                                            
```
\# Initialize submodules
```
git submodule init   
```
\# Grab the content of the submodules
```
git submodule update   
```
<br><br><br>
##Removing a Submodule from a Repository
Following the steps to remove all references to the submodule<br>
\# Temporarily remove the repository (can be initialized again)
```
$ git submodule deinit external/repo1                                          
```
\# Permanently remove the repository
```
$ git submodule deinit external/repo1    
$ git rm external/repo1   
$ git commit -m "Removed project submodule repo1" 
```


##Tip1 
To get more information to got more status when we working with submodules
```
$ git config --global status.submoduleSummary true                                        
```
<br>

##Tip2
to get summaries about submodule changes when we want to see diff in repo contains submodule
```
$ git config --global diff.submodule log                                        
```

##Tip3
To clone a repo that contains too many levels of nested submodules
```
$ git clone --recursive https://github.com/applicationmanager/crispy-succotash.git                              
```
##Tip4
To see the submodules in your rep
```
$ cat .gitmodules                              
```
To see the submodules for every nested submodules
```
$ git submodule foreach 'cat .gitmodules '                          
```

##Tip5
maybe after you pull some update on your repo from different team
```
$ git pull                             
```
they could make some changes to some of submodules and to sync your submodules state with your team submodules 
```
$ git submodule sync --recursive                             
```
if there is any new submodule and changes in old submodules configuration, then git can solve it using
```
$ git submodule update --init --recursive                           
```
##Tip6
To make the push function in your repo pushes any commit in the child submodules that have not been pushed
```
$ git config --global push.recursveSubmodules on-demand                          
```

