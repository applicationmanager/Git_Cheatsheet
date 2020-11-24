# Git Hook
A pre-defined script that is executed in response to a specific action that has occurred within your git repository

###Client-side hook
Script that executes on the client machine on specific Git events
* Designed to improve workflow for developers using repository
* Can't enforce policies as local repository can be reconfigured 
* Often leveraged to run pre-commit checks against code
    * Linting files
    * Running tests
    * Verifying no TODO's in committed files
    * Preparing a commit message
    * Cleaning up files after specific actions


###Server-side hook
Script that executes on the Git server on specific Git events
* Can enforce team policies.
    * For rejecting pushes based on overall policies, use pre-receive 
    * For evaluation of individual branch pushes, use update
    * For notifications and hooks after the commit, use post-receive
* Some of use cases
    * Enforcing commit message format
    * Enforcing user identity information
    * Enforcing the signing of tags and commits
    * Blocking access for specific IP address
    * Blocking specific file extensions