git remote -v : list all remote repos
git remote add origin <repo url> - add an existin local repo to github

\\remote - URL for hosted repo
\\origin - default remote name - we can define another name as well
git remote add novelrepo <repo url>
git remote remove origin - delete existing remote

git push <remote> <localbranch>:<remotebranch> - create the remotebranch(if not exist) in github & push the local branch
ex: git push origina bug_fix:master

git push -u <remote> <localbranch> - push local branch to the remote repo & set upstream. after that we can simply use "git push" to push the changes to the branch.

git branch -r - view remote branches
git branch -u <origin/branch name> - setting local branch to track the remote branch

git checkout origin/<branch name> - can switch to remote repos which are not in locally, & do changes locally - detached mode

git switch <origin branch name> - if a branch doesn't exist locally(exist in repo), this will create a new branch locally & setup to track the remote branch

FETCH

get changes from remote reop, but dont integrate with local repo

git fetch - by default this will get all remote changes
git fetch <remote>
git fetch origin - get all changes for all branches
git fetch origin bugfix - get only the specific bnrach changes

PULL

git pull <remote> <branch>
