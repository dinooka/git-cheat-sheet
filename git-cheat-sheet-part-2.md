## Remote Repositories

### Listing Remote Repositories

- `git remote -v` : list all remote repos

### Adding a Remote Repository

- `git remote add origin <repo url>` : add an existing local repo to GitHub

### Remote Repository Terms

- `remote` - URL for hosted repo
- `origin` - default remote name (we can define another name as well)
  - Example: `git remote add novelrepo <repo url>`

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
