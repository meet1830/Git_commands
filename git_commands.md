# BASIC LINUX COMMANDS

1. `ls`

2. `cd directory_name/`

3. `mkdir file_name` -> to make project folder

4. `git init` -> to start git in that folder to track all the changes, hidden .git folder is created in there

5. `ls -a` 
-> to view hidden items

6. `touch filename.extension` 
-> create new file

7. `rm filename.extension` 
-> delete a file

8. `rm -r directory_name` -> delete a directory with its contents -> can also use -R instead of -r

# GIT COMMANDS

1. `git status` 
-> to see what untracked changes are made to the project

2. `git add .` &nbsp; or &nbsp; `git add filename.extension` 
-> to save untracked changes in git repository -> the history folder where all changes are made is called a repository -> . means add all the changes made -> add takes the changes and places them in a staging area


3. `git commit -m "any message"` 
-> m means message -> takes a permanant snapshot of the image and saves it in the repo

4. `vi filename.extension` 
-> go to the file and edit using vi editor in terminal

5. `nano filename.extension` 
-> user friendly text editor

6. `cat filename.extension`
-> display file contents

7. `git restore --staged filename.extension` 
-> to restore the files added to commit -> remove files added to stage -> undo add command -> changes will not be reverted in local file just will be removed from staging area.

8. `git restore filename.extension` 
-> revert changes made to the file locally -> if file is added than will not work even locally -> restore --staged and then restore 

9. `git log` 
-> to see the history of repo -> all commits that were made

10. `git reset hash_id` 
-> if made changes, commited and now want to revert back to a particular commit then type git log, copy hash of that commit and paste in the command. all the above commits will be deleted as they are built on top of each other -> del a commit from middle not possible -> if want to del upto a particular commit -> copy hashid of commit below it and execute command -> the files reset will be in staged area now

11. `git stash` -> the changes made need to be not commited but maintained in a separate folder that can be refered after wards and does not interfere with project repo is called stash -> first add the changes to stage -> then execute command -> after then git status will show tree clean

12. `git stash pop` -> move all changes to stage from stash -> first execute add command -> then pop command -> if git stash then will see nothing there

13. `git stash clear` -> cleares the stash changes noted are deleted if not popped stash

14. `git remote add origin repo-url` -> after creating a repo on github website -> if want to link the url to the local project -> remote means working with urls -> add means adding a new url -> origin is the name of url added

15. `git remote -v` -> shows all the urls that are attached to this folder

16. `git push origin master` -> share and upload the changes to repo of url origin and to branch master

17. `git branch new_branch_name` -> never commit on the main branch -> always create a new branch and save changes there -> always create a new branch after saving changes to main branch as new branch always starts from head of main branch

18. `git checkout branch_name` -> make branch_name as active if want to switch branches -> head will now come on that branch

19. `git merge branch_name` -> if in other branch working on a thing which is now finalized and want to include it to the main project then merge the active branch and branch_name

20. fork -> not a command -> any project on github can clone into your account and changes can be made

21. `git clone url` -> downloading any project on local system 

22. `git remote add upstream repo-url` -> original url from where the project is forked is called upstream url -> can add to git remote using this command 

23. forked and cloned the project -> make changes to the files -> create a new branch -> checkout to that branch -> add and commit the changes there -> push it to that branch -> never commit changes in the main branch -> check forked project in your id -> will issue a notification and you can make a pull request -> then it can be merged after approval -> why are branches made -> we can make new pull request only through a new branch for that issue or feature and it is easy to manage

24. `git branch` -> view all branches and which branch is active
git checkout -b branch_name -> creates and checkouts to that branch

25. `git push origin branch_name -f` -> to remove a commit from history without creating another commit of reset and then pushing it. to reset to code as it was before the commit that we want to delete. -> git reset ssh -> changes will be unstaged -> git add . -> git stash -> commit deleted just push it to github forcefully because commits are linked.

26. merge branches -> can merge from github website but if want to do locally 
git merge branch-name -> merges branch-name with active branch -> git push origin main

27. `git checkout ssh-of-that-commit` -> to go to prev version of project
git checkout main -> to go back

28. `git remote set-url origin link-here` -> if want to change origin for commit

29. fetch upstream button on the website -> say our change was merged and included in the main of original project but our fork's main will not be updated because main project does not have our forks access. if we want to keep our fork updated with the main (other contributors' merge) then we can click this on our fork's homepage. but can be done manually also 
<br> -> method 2
-> checkout to main branch
-> `git fetch --all --prune` -> fetch all the updated changes -> prune means deleted will also be fetched
-> `git reset --hard upstream/main` -> reset the main branch of my origin to the main branch of upstream -> upstream url should be added in terminal client
-> check log and see that commits will be fetched -> main branch of upstream is same as fork's main
-> `git push origin main` -> push the changes to main branch of fork 
<br> -> method 3
-> `git pull upstream main` -> does the same thing as above
-> `git push origin main` -> push pulled changes to fork

30. -> squashing -> have lot of commits and want to merge them into a single commit
-> if want to merge them all then just reset to prev commit and then all changes will be in unstaged area and commit again
-> can use rebase command for that

31. merge conflicts -> if we made changes at some line and other contributor also made changes on that line then git will confused as to which change is to be kept and hence will ask for the same.

32. `git pull origin main` -> to see if there are any changes on remote repo (made changes directly from there)
