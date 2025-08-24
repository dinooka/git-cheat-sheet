## Remote Repositories

### Listing Remote Repositories

- `git remote -v` : list all remote repos

### Adding a Remote Repository

- `git remote add origin <repo url>` : add an existing local repo to GitHub

### Remote Repository Terms

- `remote` - URL for hosted repo
- `origin` - default remote name (we can define another name as well)
  - Example: `git remote add novelrepo <repo url>`

### Use SSH for Git

- `git remote set-url origin git@github.com:USERNAME/REPO.git` : update existing repo to use SSH

### Removing a Remote Repository

- `git remote remove origin` : delete existing remote

## Pushing Changes

### Pushing to a Remote Branch

- `git push <remote> <localbranch>:<remotebranch>` : create the remote branch (if it doesn't exist) in GitHub & push the local branch
  - Example: `git push origin bug_fix:master`

### Setting Upstream Branch

- `git push -u <remote> <localbranch>` : push local branch to the remote repo & set upstream. After that, we can simply use `git push` to push the changes to the branch.

## Branch Management

### Viewing Remote Branches

- `git branch -r` : view remote branches

### Tracking a Remote Branch

- `git branch -u <origin/branch name>` : set local branch to track the remote branch

### Checking Out a Remote Branch

- `git checkout origin/<branch name>` : switch to remote branches which are not in locally, & make changes locally - detached mode

### Switching to a Remote Branch

- `git switch <origin branch name>` : if a branch doesn't exist locally (exists in the repo), this will create a new branch locally & set up to track the remote branch

## Fetching Changes

### Fetching from Remote Repository

- Get changes from remote repo but don't integrate with local repo

#### Basic Fetch

- `git fetch` : by default, this will get all remote changes

#### Fetching Specific Remote

- `git fetch <remote>`

#### Fetching from Origin

- `git fetch origin` : get all changes for all branches

#### Fetching Specific Branch

- `git fetch origin bugfix` : get only the specific branch changes

## Pulling Changes

### Pulling from Remote Repository

- `git pull <remote> <branch>`
- `git pull` : by default, this will get the latest changes from the remote repo. This will automatically track the remote branch.
  - Example: local `food` branch will track `origin/food`

## Rebase

\*never user rebase in a main branch

you have to be in another branch & merge the changes from main.
Then do the rebase so all the commits will be overwritten. merge commits will be gone & all the commit history will be linear.

- `git merge main`
- `git rebase main`
- `git rebase -i HEAD~9` : interactive rebase last 9 commits

### options for interactive rebase

- p, pick <commit> : use commit
- r, reword <commit> : use commit, but edit the commit message
- e, edit <commit> : use commit, but stop for amending
- s, squash <commit> : use commit, but meld into previous commit
- f, fixup [-C | -c] <commit> : like "squash" but keep only the previous commit's log message, unless -C is used, in which case keep only this commit's message; -c is same as -C but opens the editor
- d, drop <commit> = remove commit

## Tags

- `git tag` : list all tags
- `git tag -l "v1.9.*"` : list all tags starts with v1.9
- `git tag -l <tagname>` : Create a lightweight tag
- `git tag -a <tagname> -m "<tag msg>"` : Create an annotated tag
- `git show <tagname>` : show details of an annotated tag
- `git tag <tagname> <commithash>` : add a tag to a previous commit
- `git tag -f <tagname> <commithash>` : move a tag to a previous commit
- `git tag -d <tagname>` : delete a tag
- `git push <tagname>` : push a tag to remote repo.
- `git push --tags` : push all tags

## Reflogs

Reflogs only keep local activity
expire activity in 90 days.

- `git reflog` : list all ref logs
- `git reflog show HEAD@{3}` : ref logs for previous 3 commits
- `git reflog show -all` : ref logs for all branches

##### Timed refernces

- `git reflog main@{yesterday}` : ref logs for yesterday
- `git reflog main@{10.days.ago}`
- `git reflog main@{dd/mm/year}`
- `git reflog main@{3.minutes.ago}`

\*\*we can reset based on reflogs
