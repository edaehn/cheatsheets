# > Git 
[Download this cheatsheet in PDF](https://github.com/edaehn/cheatsheets/PDF/)

# Index

[User Name and E-mail](#User Name and E-mail)
[Initialise or Clone](#Initialise or Clone)
[Remotes](#Remotes)
[Branches and Merging](#Branches and Merging)
[Adding Files and Commits](#Adding Files and Commits)
[Updates and Publishing](#Updates and Publishing)
[History](#History)
[Merging and Rebase](#Merging and Rebase)
[Differences](#Differences)
[A Contribution Workflow](#A Contribution Workflow)
[Undo Changes](#Undo Changes)
[Stashing](#Stashing)


## User Name and E-mail

Get global default E-mail address for your commits
```
git config --global user.email
```
Get global default user name used for your commits
```
git config --global user.name
```
Set the default user email used globally
```
git config --global user.email <your@email.com>
```
Set the default user identity used globally
```
git config --global user.name "<Your name>"
```
Set the user name locally. Similarly, set user.email
```
git config user.name "<Your name>"
```
Get user e-mail used locally. Similarly, check user.name
```
git config user.email
```


## Initialise or Clone

Initialise a GIT repository in the current folder
```
git init .
```
Clone a GIT repository via SSH
```
git clone git@github.com:<user>/<repo>.git
```
Using tokens to clone a GIT repository via HTTPS
```
git clone https://<token>@github.com/<user>/<repo>
```


## Remotes

See tracked remotes
```
git remote -v
```
Add a remote under alias "origin"
```
git remote add origin git@github.com:<user>/<repo>.git
```
Inspecting remote
```
git remote show origin
```
Rename remote origin1 to new name origin2
```
git remote rename origin1 origin2
```


## Branches and Merging

List all -a branches, both remote and local
```
git branch -a
```
Create a branch
```
git branch <branch>
```
Switch to the branch
```
git checkout <branch>
```
Delete a branch with option -d
```
git branch -d <branch>
```
Delete a remote branch
```
git push <remote> --delete <branch> 
```


## Adding Files and Commits

Add a file to the staged area (for the next commit)
```
git add <filename>
```
Commit staged files with the message, use -m option
```
git commit -m "Commit message"
```
Edit the latest commit message with --amend option
(when commit is published, use "git push <remote> <branch> --force"
```
git commit --amend -m "New commit message"
```


## Updates and Publishing

Download all changes from remote without including them into HEAD
```
git fetch <remote>
```
Download remote changes and integrate into HEAD
```
git pull <remote> <branch>
```
Publish local changes to remote
```
git push <remote> <branch>
```


## History

Check the status
```
git status
```
Check the commits log (for brevity use --oneline option
```
git log
```
Who changed the file and where
```
git blame <filename>
```


## Merging and Rebase

Merge a branch into the main branch, in result including all changes
```
git merge <branch>
```
Merge main into the branch
```
git checkout <branch>; git merge main
```
Resolve merge conflicts
```
git mergetool
```
Rebase HEAD into your branch (apply your changes on top the 
latest updates of other developers)
```
git rebase <branch>
```


## Differences

See local changes that can be further added to commit
```
git diff
```
See staged changes with --staged option
```
git diff --staged
```
Differences against a base (--ours for your changes, or --theirs)
```
git diff --base <filename>
```
See differences between local and remote
```
git diff origin/master
```
See differences between two commits
```
git diff <commit_id1> <commit_id2>
```


## A Contribution Workflow

Cloning a remote (forked) repository locally with your token
```
git clone https://<token>@github.com/<user>/<repo>
```
Add upstream for your organisation
```
git remote add upstream https://github.com/<org>/<repo>
```
Working on a new branch, created with -b option
```
git checkout -b <branch>
```
Get changes from remote
```
git fetch <remote>
```
Add changed file to the staged area
```
git add <filename>
```
Commit changes
```
git commit -m "commit message"
```
Use -u for your first push of the branch to remote
```
git push -u <remote> <branch> 
```
Create a pull request
```
In your GitHub fork page press "Pull Request" button
```


## Undo Changes

Removing the last commit, --mixed (default) preserves working tree
```
git reset --mixed HEAD~
```
Undo all changes in your local directory (consider stashing)
```
git reset --hard HEAD
```
Resets commit (removes commits from the current branch and changes
commit history), useful to undo changes that are not yet published
```
git reset <commit_id>
```
Resets commit to the defined one, discards all later changes
```
git reset --hard <commit_id>
```
Reverts commit to the defined commit, adds a new commit and is
a safe operation
```
git revert <commit_id>
```
Revert file to the latest commit (effects the working directory)
```
git checkout <filename>
```
Discard changes in your local file
```
git checkout HEAD <filename>
```


## Stashing

Save the current state of your directory and the index
```
git stash
```
Show list of your stashes
```
git stash list
```
Removes the changes from your stash and re-applies them
```
git stash pop
```
Apply the changes and keep them in your stash
```
git stash apply
```
