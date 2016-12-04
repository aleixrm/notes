
######GIT BASH######

#Configuring git
http://git-scm.com/docs/git-config
Customize bash prompt: http://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html

###coloring diff
```
git config --global color.ui auto
```

###Configure sublime (or another editor) for file and comment edition
https://help.github.com/articles/associating-text-editors-with-git/
```
git config --global core.editor "'<sublime path>' -n -w"
```

###do git to push to the configured upstream branch
```
git config --global push.default upstream
```

###Display merge conflicts in diff3 format
```
git config --global merge.conflictstyle diff3
```


#Git basics

###git help
```
git help <topic>
```

###initialize repository
```
git init
```

###Check status of the working copy
```
git status
```

###Show change log
```
git log
```

###Show log with file changes
```
git log --stat
```

###move to another revision
NOTE: Also, we can only introduce the revision id first representative chars
```
git checkout <id_revision> 
```

###Add files to the staging area
```
git add <file_name>
```

###Add all untracked files to the staging area
```
git add --all
```

###Commit changes in the staging area
```
git commit -m "<message>"
```

###Commit and add changes from tracked files directly (without setting in the staging area)
```
git commit -a -m "<message>"
```

###Change last commit, including files in staging area and overwriting message
```
git commit --amend -m "New message"
```

###Show unstaged differences since last commit
```
git diff
```

###View staged differences (Compare files between staged area and repository)
```
git diff --staged
```

###Diff between files
```
git diff <file_1> <file_2>
```

###Remove files from the staging area
```
git reset <file_name>
```

###Add remote repository 
```
git remote add origin https://github.com/<repository_name>.git
```

###get info about remote repositories
```
git remote -v
```

###push repository to remote repository
```
git push <remote_repository_name> <branch>
#e.g.
git push -u origin master
```
Tip: Password caching: https://help.github.com/articles/set-up-git

###pull changes from remote (syncs our local repository and workspace with the remote one)
```
git pull <remote_name> <branch_name>
```

###add new remotes
```
git remote add <name> <address>
```

###remove remotes
```
git remote rm <name>
```

###clone repository
```
git clone <repository_url>
git clone <repository_url> <local_folder_name>
```

##Branching
###create branch
```
git branch <branch_label>
```

###list branches (the one with the asterisk is the one checked out)
```
git branch
```

###switch to a branch
```
git checkout <branch_label>
```

###create and checkout branch
```
git checkout -b admin
```

###merge branch with the actual checked out branch
```
git merge <branch_label>
```

###safely remove branch
```
git branch -d <branch_label>
```

###leave 'detached HEAD' state
```
git checkout master
```


##Undo changes

###Undo all changes since last commit
```
git checkout -- <file_name>
```

WARNING! Don't do the following resets after push, because we will change history locally

###Undo last commit, put changes into staging area. 'HEAD^' refers to the commit previous to HEAD
```
git reset --soft HEAD^
```

###Discards any changes in either working directory or staging area CAREFUL!!
```
git reset --hard
```

###Undo last commit and all changes
```
git reset --hard HEAD^
```

###Undo last 2 commit and all changes
```
git reset --hard HEAD^^
```


#Syncing
###Pull
1. Fetch : sync our local repository with the remote one (not updates local code)
```
git fetch
```
2. Merges origin/master branch with master
```
git merge origin/master
```

###Conflicts
1. Diff:
```
<<<<<<< HEAD
<local_version>
=======
<remote_version
>>>>>>>
```
2. Edit file and correct
3. Commit edition
```
git commit -a
```

#Others







#See visual representation of the commit history of branches
git log --graph --oneline <branches_labels>

#Call git garbage collector
git gc

#abort merge (restore files to the state before the merge)
git merge --abort

#Show diff between a commit and its parents
git show <id_commit>

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



#push repository to remote repository
git push <remote_repository_name> <branch>



##Conflicts:
#Update a branch with a remote repository copy
git fetch origin
#Merge changes with the local master branch
git merge master origin/master
#Pull do the fetch+merge at the same time
git pull origin master

#Fast forward merge -> occurs when we merge two nodes, one of which is ancestor of the other.

#Pull request-> creates a branch on the remote repository with our changes