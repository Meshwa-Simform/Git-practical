# Git basics

# What is Git?
  - Git is a tool used to track the verions in a project. in other word it keeps thet track of changes made in the code of the project.
  - It is a distributed version control system, i.e. each developer has its own server(local machine) where all the versions of the code are stored and this servers are connectd to a main server.

# Working Directory and Staging Area
  step 1- we make changes in any file in worker directory.  
  step 2- Then we perform add operation n the file, the files get added to the staging area.  
  step 3- Then we commit the staged file and push it to the repository.  

# Installation of Git
  Sudo apt-get install git-core // used to install git in the linux system.  
  enter password of the system for authentication.  

  git --version //to check the version of the git installed.

# Git setup and configure
*Git Initialization*
  git init  //with the help of this command git will get initialized and a .git file will get created.
  
*Git Configure*
  git config --global user.name 'username'  //setting username  

  git config --global user.email 'email'  //setting email

# Add file 
Add file command is used to add modified file to the staging area. some command for add are :
  - git add filename  //used to add a single file having the filename given in the command.
  - git add .   //used to add all the files which are modified.
  - git add *.html  //used to add all the file having .html as extension.

# commit file
Commit is used to add the staged file to repository. command for commit is :  
  git commit -m "comment"

# To unstage a file
used to remove an file from the staging area  
  git rm --cached filename   //removes the specific file from staged area.

# .gitignore
This file is used to ignore the file/folder, it prevents them from staging. We just have to write the name of the file or floder in the .gitignore file.

# Add repository
  - First make a repository in github.
  - git remote add origin <url_of_repository>  // by this url will be added to origin.
  - git push -u origin master   //push the commits to the repository.

# See commits in terminal
  git log  //it will provide all the details of commit you have made.

# Push and Pull 
  - Push is used to push/copy commits from the local repository to remote repository.  
       git push  
  - Pull is ussed to copy changes from the remote repository to local repository.  
       git pull  //git pull is a combination of fetch and merge.  

# Branch
 - Used to copy the master branch to the new branch and we make changes on the new branch without affecting the master branch.
 - git branch branchname  //created a new branch.
 - git branch  //lists all the brancjes in the repository.
 - git checkout newbranchname  //switches to the new branch from master.

 # Merge
  - used to mearge branch to the master branch i.e. the changes made in new brach will be added to the master branch.
  - git merge branchname  //merges with master branch.
