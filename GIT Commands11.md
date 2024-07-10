add git username & password

--

git init (create the .git folder)
git status
git log
git log --online

git add . (stage all files)
git add <filename1> <filename2> (stage only the mentioned files)
git rm <filename> (remove files from working dir. & staging area)

git commit -m "commit message"
git commit (editor will open to enter the commit message)

git commit --amend (can redo the previous commit message - only the message)

git commit -am "commit msg" - stage & commit changes(\*\*\* new files won't affected)

Branches

git branch - list all the branches
git branch -v - list all the branches + last commit

git branch <branchname> - Create new branch

git switch <branchname> - Switch to a branch
git switch - - Switch to the previous branch
git checkout <branchname> - Switch to a branch

git switch -c <branchname> - Create & Switch to a branch

git branch -d <branchname> - Delete a branch

git branch -m <branchname> - Rename/move branch (\*\*\* have to be inside the branch to execute this)

git merge <branch2> - merge branch2 to to the branch we are in

git diff - view the only unstaged changes
git diff HEAD <filename> - view ALL changes(staged & unstaged)
git diff --staged - view only staged changes

Stash

git stash - save the work before navigating to a branch.
git stash pop - stashed work will be restored & removed, changes are removed from the stash once apply
git stash apply - changes will be saved after the stash apply

git stash -u - this will apply stash for unstaged files as well
git stash apply - after that we can apply

git stash list - view stash list
git stash apply stash@{0} - insert multiple stashed changes

**_ git stash pop removes stashes from the list, so
_** we have to use drop only if we use apply

git stash drop stash@{1}

git stash clear - remove all the saved stashes

detached head

git checkout <commithash> - switch to detached head state. can make
experiments. then we can create a new branch & commit new chages to that branch.

git checkout HEAD~1 - points to previous commit
git checkout HEAD~8 - points to previous 8 commits

git checkout HEAD <filename> - discard changes
git checkout -- <filename> - same as above
git restore <filename> - same as above

git reset <commithash> - remove the commit, changes will be there
git reset --hard <commithash> - remove the commit & the changes

revert - make a new commit & undo the changes
git revert <commithash>
