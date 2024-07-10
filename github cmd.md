git remote -v : list all remote repos
git remote add origin <repo url> - add an existin local repo to github

\\remote - URL for hosted repo
\\origin - default remote name - we can define another name as well
git remote add novelrepo <repo url>

git push <remote> <localbranch>:<remotebranch> - create the remotebranch(if not exist) in github & push the local branch
ex: git push origina bug_fix:master
