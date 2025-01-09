# Git Exercise.
## Create a new repository with a template
- Go to your GitHub and create a new repository button. 
- Then select the template and enter all the required details.
 
 ## Initialize git-flow 
 - **Install git-flow -**  
     *command:* sudo apt-get install git-flow
- **Initialize git-flow -**  
     *command:* git flow init
	 
## Create a feature branch for project setup with the proper Zoho task ID (example: TP2-T1299_Project_Setup)
*command:* git flow feature start TP2-T1299_Project_Setup  

## Create a sub-branch from the project setup branch and perform squash, reset, rebase and cherrypick ​​​​​​​.
- **Making sub-branch -**  
    *command:* git checkout -b TP2-T1299_Project_Setup_Subbranch  
- Now performing the following operations in Sub-branch :-  
1. **Squash -** Squashing is used when you want to merge multiple commits into one.  
   *command:* git rebase -i HEAD~3  
   //Write squash for the commits you want to combine into one. Save and exit the editor.  
2. **Reset-** Resetting will undo commits or move the HEAD pointer to a specific commit.   
   *command:* git reset --hard <commit-hash>  
   //This is used when you want to discard changes made in commits.  
3. **Rebase-** Rebasing is used to move commits to another branch. It makes the project history linear.  
   *command:* git rebase TP2-T1299_Project_Setup  
4. **Cherry-pick-** Cherry-picking is used when you want to apply a specific commit from another branch to your current branch.  
   *command:* git cherry-pick <commit-hash>  
   
## Create a branch from the develop
*command:* git checkout develop  
					git checkout -b NewBranch  
	
## Add a commit message hook to the repo.
- **create a .git/hooks/commit-message file**  
	*content of file:*  
	#!/bin/bash  
	echo "I am a post commit hook"  
- **Make it executable:**  
	*command:* chmod +x commit-message  
	
## Create PR to develop.
- **Push the develop branch from local repository**  
*command:*  git push origin develop  
- **Create pull request in GitHub**  
1. ClickCompare and pull request option.  
2. Add title and desciption the create pull request.  
3. then check the detail and it every thing is perfect the merge pull request.  

## Create another branch from develop given your previous PR is still in review state 
*command:*  
git checkout develop  
git pull origin develop  
git checkout -b NewBranch  

## Now commit something in your current branch and push it
*command:*  
git add .  
git commit -m "Newbranch commit"  
git push origin NewBranch  

## Create a PR for the current branch given your branch should be up to date with develop branch
*command:*  
git checkout develop  
git pull origin develop  
git checkout NewBranch  
git rebase develop  

## For any new build release add a version tag to that specific commit to keep track of each version.
1. **Ensure Your Local Repository is Up-to-Date**  
	*command:*  
	git checkout develop  
	git pull origin develop  
2. **Create a Version Tag**  
	*command:*  
	git tag -a v1.0.0 -m "Release version 1.0.0"  
3. **Push the tag to repository**  
	*command:*  
	git push origin v1.0.0  
	
## Create 2 another branch (3rd and 4th) from develop, push read me changes to 3rd brach.
- **Create branch 3 and push readme changes**  
*command:*  
git checkout develop  
git pull origin develop  
git checkout -b Branch-3  
git add .  
git commit -m "Updated Readme file"  
- **Create branch 4**  
*command:*   
git checkout develop  
git pull origin develop  
git checkout -b Branch-4  

## Cherry pick 3rd branch's commit to 4th branch.
*command:*  
git checkout Branch-4  
git cherry-pick <commit-hash-from-3rd-branch>  

## Change commit message in 4th branch
*command:*  
git commit --amend  
Edit the commit message in the editor that opens.  

## add 3 commit to 4th branch and delete last commit.
*command:*  
git reset --hard <commit-hash>  
