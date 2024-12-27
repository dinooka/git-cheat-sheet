# Git Commands

## Basic Git Commands

### Initializing a Repository

- `git init` : create the .git folder

### Configuration

config options for all repos

- `git config --global user.name "<name>"`
- `git config --global user.email "<email>"`
- `git config --global core.editor "<code>"` : VS Code

config options for a specific repo(local)

- `git config user.name "<name>"`

### Checking Status

- `git status`

### Viewing Commit Logs

- `git log`
- `git log --online`
- `git log main@{3.days.ago}--online`

### Staging Changes

- `git add .` : stage all files
- `git add <filename1> <filename2>` : stage only the mentioned files
- `git rm <filename>` : remove files from working dir. & staging area

### Committing Changes

- `git commit -m "commit message"`
- `git commit` : editor will open to enter the commit message
- `git commit --amend` : can redo the previous commit message - only the message
- `git commit -am "commit msg"` : stage & commit changes (**new files won't be affected**)

## Branches

### Listing Branches

- `git branch` : list all the branches
- `git branch -v` : list all the branches + last commit

### Creating a Branch

- `git branch <branchname>` : create new branch

### Switching Branches

- `git switch <branchname>` : switch to a branch
- `git switch -` : switch to the previous branch
- `git checkout <branchname>` : switch to a branch
- `git switch -c <branchname>` : create & switch to a branch

### Deleting a Branch

- `git branch -d <branchname>` : delete a branch

### Renaming a Branch

- `git branch -m <new_branchname>` : rename/move branch (**have to be inside the branch to execute this**)

### Merging Branches

- `git merge <branch2>` : merge branch2 to the branch we are in

## Viewing Differences

### Viewing Changes

- `git diff` : view only unstaged changes
- `git diff HEAD <filename>` : view ALL changes (staged & unstaged)
- `git diff --staged` : view only staged changes
- `git diff HEAD@{0} HEAD{5}` : changes between last commit to 5 commits ago

## Stashing Changes

### Saving Work Before Switching Branches

- `git stash` : save the work before navigating to a branch
- `git stash pop` : stashed work will be restored & removed, changes are removed from the stash once applied
- `git stash apply` : changes will be saved after the stash apply
- `git stash -u` : this will apply stash for unstaged files as well
- `git stash list` : view stash list
- `git stash apply stash@{0}` : insert multiple stashed changes
- `git stash push -m 'custom text'` : A custom name will be added to the stashed changes
- `git stash branch <branch-name> <stash-id>` : Create a new branch with the stashed changes

### Dropping Stashed Changes

- `git stash drop stash@{1}`

### Clearing All Stashes

- `git stash clear` : remove all the saved stashes

## Detached Head

### Switching to Detached Head State

- `git checkout <commithash>` : switch to detached head state. Can make experiments. Then we can create a new branch & commit new changes to that branch.

### Checking Out Previous Commits

- `git checkout HEAD~1` : points to previous commit
- `git checkout HEAD~8` : points to previous 8 commits

### Discarding Changes

- `git checkout HEAD <filename>` : discard changes
- `git checkout -- <filename>` : same as above
- `git restore <filename>` : same as above

## Resetting Commits

- `git reset <commithash>` : remove the commit, changes will be there
- `git reset --hard <commithash>` : remove the commit & the changes

## Reverting Changes

### Making a New Commit to Undo Changes

- `git revert <commithash>`
