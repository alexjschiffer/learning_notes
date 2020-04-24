#Overview
* Created by Linus Torvald (creator of Linux)
* Version Control System (VCS) - allows tracking of changes to files
* Distributed/de-centralized version control that allows multiple users to work at the same time
* Have both local and remote repositories
  * local - on your computer
  * remote - github or bitbucket
* Snapshots/checkpoints of your files are created by making a **comit**

#Configuring
* Add username ``` git config --global user.name "nameToUse" ```
  * Check username ``` git config --global user.name ```
* Add email ``` git config --global user.email "emailToUse" ```

#Basic Commands
* Initialize a local repo ``` git init ```
* Add files to staging area ``` git add <file> ```
* Check status of working/staging area ``` git status ```
* Commit changes to index ``` git commit -m "Commit Reason" ```
* Push local repo to remote ``` git push ```
* Pull changes from local repo ``` git pull ```
* Copy remote repo to your computer ``` git clone ```

#Adding files
* Add all files with specific extension ``` git add *.ext ```
