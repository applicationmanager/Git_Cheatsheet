#Git Configuration
Git provides a robust configuration system that allows you to configure standard and custom configuration values across 
multiple levels of your installation
<br><br><br>
###Configuration levels
* Repository (local)
* UserAccount (global)
* Git installation (system)<br>
Configuration values are evaluated from the repository up. So git config will use what is in your repository and if it 
not there it will bubble up to the global setting and if it doesn't find something there it will automatically bubble up
to the system level settings.
<br><br><br>
#####Setting a Git Config Value
\# Local (repository)
```
$ git config --local user.name "Mohammad Eshker" 
```
\# Global (user directory)
```
$ git config --global user.name "Mohammad Eshker"  
```
\# System (git installation)
```
$ git config --system user.name "Mohammad Eshker"  
```
<br><br><br>
#####Common Configuration Settings
* Identity Settings<br>
Configure you name and email address
```
$ git config --local user.name "Mohammad Eshker" 
$ git config --local user.email "mhdeshker@gmail.com" 
```
* File editor<br>
set up the main editor you want to configure which editor Git should use. below are some examples for: atom, vim, sublim (MAC), sublim (windows 64bit)
```
$ git config --global core.editor "atom --wait
$ git config --global core.editor "vim"
$ git config --global core.editor "subl -n -w"   \\-n: new window   -w:wait till the app return it is closed
$ git config --global core.editor "'c:/program files/sublime text 3/sublimetext.exe' -w"
```
* Merge Tool<br>
* Terminal color output<br>
* Command aliases<br><br><br>
#####Showing Configuration
\# show all config values, and the file where they are defined
```
$ git config --list --show-origin
```
\# show the current user.name config value (sub any key)
```
$ git config user.name
```
\# Remove a specific setting for a specific level of config (ex:global)
```
$ git config --global --unset user.name
```
\# Edi a specific level of config directly by opening the file and change values
```
$ git config --global --edit
```
\# Remove a section of config for a specific level
```
$ git config --global --remove-section user
```
<br><br><br>
###Git Attributes
we have two different ways to handle working with files in git.
1. .gitignore: allows us to determine which files can be ignored within the repository.
2. .gitattributes: allows us to set a specific configuration values for how the files are handled.

Git Attributes: specific configuration settings placed on a file or collection of files within a repository that dictate how the file
is handled. In some cases, different Git hosts may offer specific functionality that laverages these attributes.<br><br>
#####Git Attributes Common Uses
* configuring line ending in files
* Specifying binary files
* Enabling large binary file to be handled by Git LFS
* Excluding files from exported version of repository 
* Specifying clean and smudge filters
```
$ git config --local filter.updateAPIKey.smudge   'sed "s/{SECURE_API_KEY}/SADF763IU4YRC87/"'
$ git config --local filter.updateAPIKey.clean   'sed "s/SADF763IU4YRC87/{SECURE_API_KEY}/"'
```