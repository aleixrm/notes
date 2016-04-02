
######GIT BASH######

#git help
git help <topic>

#clone repository
git clone <repository_url>

#Diff between files
git diff <file_1> <file_2>

#coloring diff
git config --global color.ui auto

#Show change log
git log

#Show log with file changes
git log --stat

#move to another revision
git checkout <id_revision> 
##-> We can only introduce the revision id first representative chars

#Configurar sublime (u otro editor) para edicion de ficheros y comentarios
#https://help.github.com/articles/associating-text-editors-with-git/
git config --global core.editor "'<sublime path>' -n -w"

#do git to push to the configured upstream branch
git config --global push.default upstream

#Display merge conflicts in diff3 format
git config --global merge.conflictstyle diff3

##More info about git config: http://git-scm.com/docs/git-config


##Customize bash prompt-> http://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html


#initialize repository
git init

#Check status of the working copy
git status

#Add files to the staging area
git add <file_name>

#Remove files from the staging area
git reset <file_name>

#Commit changes in the staging area
git commit

#Compare files between staged area and repository
git diff --staged

#Discards any changes in either working directory or staging area CAREFUL!!
git reset --hard

#leave 'detached HEAD' state
git checkout master

#list branches (the one with the asterisk is the one checked out)
git branch

#create branch
git branch <branch_label>

#Switch to a branch
git checkout <branch_label>

#See visual representatio of the commit history of branches
git log --graph --oneline <branches_labels>

#Call git garbage collector
git gc

#merge branch with the actual checked out branch
git merge <branches_labels>

#abort merge (restore files to the state before the merge)
git merge --abort

#Show diff between a commit and its parents
git show <id_commit>

#delete branch
git branch -d <branch_name>

#create repository from command line
echo # reflections >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/<repository_name>.git
git push -u origin master

#push an existing repository from the command line
git remote add origin https://github.com/<repository_name>.git
git push -u origin master

#get info about remote repositories
git remote -v

#push repository to remote repository
git push <remote_repository_name> <branch>

#pull changes from remote
git pull origin <branch_name>

##Conflicts:
#Update a branch with a remote repository copy
git fetch origin
#Merge changes with the local master branch
git merge master origin/master
#Pull do the fetch+merge at the same time
git pull origin master

#Fast forward merge -> occurs when we merge two nodes, one of which is ancestor of the other.

#Pull request-> creates a branch on the remote repository with our changes