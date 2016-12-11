
######GIT BASH######

#Configuring git
http://git-scm.com/docs/git-config
Customize bash prompt: http://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html

###list repo configuration
```
git config --list
```

###view configuration parameter
```
git config <parameter>
```

###configure global user name and mail
```
git config --global user.name <user_name>
git config --global user.email <user_email>
```

###configure user mail for current repo
```
git config user.email <user_mail>
```

###do git to push to the configured upstream branch
```
git config --global push.default upstream
```

###Configure default editor for interactive commands
```
git config --global core.editor <editor_command>
```
####Configure sublime (or another editor) for file and comment edition
https://help.github.com/articles/associating-text-editors-with-git/
```
git config --global core.editor "'<sublime path>' -n -w"
```

###Configure merge tool for conflig
```
git config --global merge.tool <merge_tool>
```

###Display merge conflicts in diff3 format
```
git config --global merge.conflictstyle diff3
```

###Set log colors
```
git config --global color.ui true
```

###Configure alias
```
git config --global alias.mylog \
    "log --pretty=format:'%h %ad- %s [%an]''
git config global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
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

###Remove file from local repository (and delete from file system)
```
git rm <file_name>
```

###Stop tracking a file (but not delete from local system)
```
git rm --cached <file_name>
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

###safely delete branch
```
git branch -d <branch_label>
```

###leave 'detached HEAD' state
```
git checkout master
```

###Push branch to remote
```
git checkout -b feature_branch
push origin feature_branch
```

###Retrieve new remote branches
```
git fetch
```

###List all remote branches
```
git branch -r
```

###Show remote status
```
git remote show <remote_name>
#e.g.
git remote show origin
```

###Delete remote branch (local branch will remain, must be deleted manually)
```
git push origin :<branch_name>
```

###Force local branch deletion (WARNING: deleting also pending to merge changes)
```
git branch -D <branch_name>
```

###Clean up deleted remote branches (deletes stale references)
```
git remote prune origin
```


##Tagging
###List tags
```
git tag
```

###Checkout tag
```
git checkout <tag_name>
```

###Add new tag
```
git tag -a <tag_name> -m "Tag description"
```

###Push new tag
```
git push --tags
```


##Rebase 
Alternative to merge commits.
First of all, fetch. This will get all changes from remote to local repository,
whithout merging them.

###Execute rebase
```
git rebase
```

1. Move all changes to master which are not in origin/master to a temp area
2. Run all origin/master commits to master.
3. Run all commits in the temporary area, one at a time into master.

###Rebase feature branch into master
```
git checkout <feature_branch_name>
git rebase master
git checkout master
git merge <feature_branch_name>
```

###Rebase with conflicts
```
git rebase
#solve conflicts
git add <conflict_files>
git rebase --continue   #When the problem is solved

#Other options:
git rebase --skip       #Skips the patch
git rebase --abort      #Checkouts original branch and stops rebasing (rollback)
```

###Interactive rebase (alter commits in the same branch, change order, etc)
```
git rebase -i <commit_to_replay>
```

* Change order: swap commits order on the editor.
* Edit commit message: Change 'pick' keyword to 'reword' in the editor, a second editor will appear to edit the commit message.
* Split commit: Change keyword 'pick' to 'edit'. Then do:
    ```
    git reset HEAD^
    ```
    in order to rollback last commit, leaving changes in working directory. Then stage files for the first commit and commit them, and then stage the files for the second commit and commit. Then run
    ```
    git rebase --continue
    ```
    in order to replay changes from rebase temp area.
* Squash commit: Merges a commit with its previous one. Change keyword 'pick' to 'squash'. Another editor will pop up. Put the commit message and delete the old ones.


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


##Syncing
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

##History

###Display log info inline
```
git log --pretty=oneline
```

###Configure log output format
```
git log --pretty=format:"%h %ad- %s [%an]"
```
| placeholder   | replaced with     |
| ------------- | ----------------- |
| %ad           | author date       |
| %an           | author name       |
| %h            | SHA hash          |
| %s            | subject           |
| %d            | ref names         |

###Show line changes (diff with log)
```
git log --oneline -p
```

###Show insertions and deletions
```
git log --oneline --stat
```

###Show commits and branches graph
```
git log --oneline --graph
```

###Get log output respect on time
```
git log --until=1.minute.ago
git log --since=1.day.ago
git log --since=1.hour.ago
git log --since=1.month-ago --until=2.weeks.ago
git log --since=2000-01-01 --until=2012-12-21
```

###Get earlier commits
```
git diff HEAD^          #parent of latest commit
git diff HEAD^^         #grandparent of latest commit
git diff HEAD~5         #five commits ago
git diff HEAD^..HEAD    #second most recent commit vs most recent
```

###Get abbreviated SHAs of the commits
```
git log --oneline
```

###diff between range of commits
```
git diff <sha1>..<sha2>
```

###diff between branches
```
git diff <branch1> <branch2>
```

###diff based on time ranges
```
git diff --since=1.week.ago --until=1.minute.ago
```

###show changes on each line of a file (commit hash, author, date, line #, content)
```
git blame <file_name> --date short
```

###exclude file from repo (will not appear in git status)
```
vim .git/info/exclude
>> add folder/file to exclude
#eg.
tutorial.mp4    #exclude file
*.mp4           #exclude all .mp4 files
experiments/    #excludes experiments folder
logs/*.log      #excludes .log files into experiments repository
```

###exclude files from local repository and for everybody else
```
vim .gitignore
>> add folder/file to ignore
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


##Conflicts:
#Update a branch with a remote repository copy
git fetch origin
#Merge changes with the local master branch
git merge master origin/master
#Pull do the fetch+merge at the same time
git pull origin master

#Fast forward merge -> occurs when we merge two nodes, one of which is ancestor of the other.

#Pull request-> creates a branch on the remote repository with our changes